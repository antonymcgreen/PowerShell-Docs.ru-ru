---
description: Объясняет, как использовать оператор Split для разделения одной или нескольких строк на подстроки.
keywords: powershell,командлет
Locale: en-US
ms.date: 12/20/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_split?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Split
ms.openlocfilehash: 520aac1fd1aae4f1f0f4a12a10bc4f5c7f258731
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231229"
---
# <a name="about-split"></a><span data-ttu-id="33ae6-104">Сведения о разбиении</span><span class="sxs-lookup"><span data-stu-id="33ae6-104">About Split</span></span>

## <a name="short-description"></a><span data-ttu-id="33ae6-105">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="33ae6-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="33ae6-106">Объясняет, как использовать оператор Split для разделения одной или нескольких строк на подстроки.</span><span class="sxs-lookup"><span data-stu-id="33ae6-106">Explains how to use the Split operator to split one or more strings into substrings.</span></span>

## <a name="long-description"></a><span data-ttu-id="33ae6-107">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="33ae6-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="33ae6-108">Оператор Split разделяет одну или несколько строк на подстроки.</span><span class="sxs-lookup"><span data-stu-id="33ae6-108">The Split operator splits one or more strings into substrings.</span></span> <span data-ttu-id="33ae6-109">Вы можете изменить следующие элементы операции разбиения:</span><span class="sxs-lookup"><span data-stu-id="33ae6-109">You can change the following elements of the Split operation:</span></span>

- <span data-ttu-id="33ae6-110">Разделитель.</span><span class="sxs-lookup"><span data-stu-id="33ae6-110">Delimiter.</span></span> <span data-ttu-id="33ae6-111">По умолчанию используется пробел, но можно указать символы, строки, шаблоны или блоки скриптов, указывающие разделитель.</span><span class="sxs-lookup"><span data-stu-id="33ae6-111">The default is whitespace, but you can specify characters, strings, patterns, or script blocks that specify the delimiter.</span></span> <span data-ttu-id="33ae6-112">Оператор Split в PowerShell использует регулярное выражение в разделителе, а не простой символ.</span><span class="sxs-lookup"><span data-stu-id="33ae6-112">The Split operator in PowerShell uses a regular expression in the delimiter, rather than a simple character.</span></span>
- <span data-ttu-id="33ae6-113">Максимальное число подстрок.</span><span class="sxs-lookup"><span data-stu-id="33ae6-113">Maximum number of substrings.</span></span> <span data-ttu-id="33ae6-114">По умолчанию возвращаются все подстроки.</span><span class="sxs-lookup"><span data-stu-id="33ae6-114">The default is to return all substrings.</span></span> <span data-ttu-id="33ae6-115">Если указать число, меньшее числа подстрок, оставшиеся подстроки объединяются в последнюю подстроку.</span><span class="sxs-lookup"><span data-stu-id="33ae6-115">If you specify a number less than the number of substrings, the remaining substrings are concatenated in the last substring.</span></span>
- <span data-ttu-id="33ae6-116">Параметры, определяющие условия, при которых будет сопоставляться разделитель, например SimpleMatch и Multiline.</span><span class="sxs-lookup"><span data-stu-id="33ae6-116">Options that specify the conditions under which the delimiter is matched, such as SimpleMatch and Multiline.</span></span>

## <a name="syntax"></a><span data-ttu-id="33ae6-117">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="33ae6-117">SYNTAX</span></span>

<span data-ttu-id="33ae6-118">На следующей схеме показан синтаксис оператора-split.</span><span class="sxs-lookup"><span data-stu-id="33ae6-118">The following diagram shows the syntax for the -split operator.</span></span>

<span data-ttu-id="33ae6-119">Имена параметров не отображаются в команде.</span><span class="sxs-lookup"><span data-stu-id="33ae6-119">The parameter names do not appear in the command.</span></span> <span data-ttu-id="33ae6-120">Включайте только значения параметров.</span><span class="sxs-lookup"><span data-stu-id="33ae6-120">Include only the parameter values.</span></span> <span data-ttu-id="33ae6-121">Значения должны присутствовать в порядке, указанном в схеме синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="33ae6-121">The values must appear in the order specified in the syntax diagram.</span></span>

```
-Split <String>
-Split (<String[]>)
<String> -Split <Delimiter>[,<Max-substrings>[,"<Options>"]]
<String> -Split {<ScriptBlock>} [,<Max-substrings>]
```

<span data-ttu-id="33ae6-122">Можно заменить `-iSplit` или `-cSplit` для `-split` в любой инструкции двоичного разделения (оператор разбиения, включающий разделитель или блок сценария).</span><span class="sxs-lookup"><span data-stu-id="33ae6-122">You can substitute `-iSplit` or `-cSplit` for `-split` in any binary Split statement (a Split statement that includes a delimiter or script block).</span></span> <span data-ttu-id="33ae6-123">В `-iSplit` `-split` операторах и регистр не учитывается.</span><span class="sxs-lookup"><span data-stu-id="33ae6-123">The `-iSplit` and `-split` operators are case-insensitive.</span></span> <span data-ttu-id="33ae6-124">В `-cSplit` операторе учитывается регистр, что означает, что при применении правил разделителей учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="33ae6-124">The `-cSplit` operator is case-sensitive, meaning that case is considered when the delimiter rules are applied.</span></span>

## <a name="parameters"></a><span data-ttu-id="33ae6-125">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="33ae6-125">PARAMETERS</span></span>

### <a name="string-or-string"></a><span data-ttu-id="33ae6-126">\<String\> или \<String[]\></span><span class="sxs-lookup"><span data-stu-id="33ae6-126">\<String\> or \<String[]\></span></span>

<span data-ttu-id="33ae6-127">Указывает одну или несколько строк для разбиения.</span><span class="sxs-lookup"><span data-stu-id="33ae6-127">Specifies one or more strings to be split.</span></span> <span data-ttu-id="33ae6-128">При отправке нескольких строк все строки разбиваются с помощью одних и тех же правил разделителей.</span><span class="sxs-lookup"><span data-stu-id="33ae6-128">If you submit multiple strings, all the strings are split using the same delimiter rules.</span></span>

<span data-ttu-id="33ae6-129">Пример</span><span class="sxs-lookup"><span data-stu-id="33ae6-129">Example:</span></span>

```
-split "red yellow blue green"
red
yellow
blue
green
```

### \<Delimiter\>

<span data-ttu-id="33ae6-130">Символы, которые обозначают конец подстроки.</span><span class="sxs-lookup"><span data-stu-id="33ae6-130">The characters that identify the end of a substring.</span></span> <span data-ttu-id="33ae6-131">По умолчанию разделителем являются пробелы, включая пробелы и непечатаемые символы, например символ новой строки ( \` n) и знак табуляции ( \` t).</span><span class="sxs-lookup"><span data-stu-id="33ae6-131">The default delimiter is whitespace, including spaces and non-printable characters, such as newline (\`n) and tab (\`t).</span></span> <span data-ttu-id="33ae6-132">При разбиении строк разделитель опускается из всех подстрок.</span><span class="sxs-lookup"><span data-stu-id="33ae6-132">When the strings are split, the delimiter is omitted from all the substrings.</span></span> <span data-ttu-id="33ae6-133">Пример</span><span class="sxs-lookup"><span data-stu-id="33ae6-133">Example:</span></span>

```
"Lastname:FirstName:Address" -split ":"
Lastname
FirstName
Address
```

<span data-ttu-id="33ae6-134">По умолчанию разделитель в результатах опускается.</span><span class="sxs-lookup"><span data-stu-id="33ae6-134">By default, the delimiter is omitted from the results.</span></span> <span data-ttu-id="33ae6-135">Чтобы сохранить все или часть разделителя, заключите в круглые скобки часть, которую необходимо сохранить.</span><span class="sxs-lookup"><span data-stu-id="33ae6-135">To preserve all or part of the delimiter, enclose in parentheses the part that you want to preserve.</span></span>
<span data-ttu-id="33ae6-136">Если \<Max-substrings\> параметр добавлен, это имеет приоритет, если команда разделяет коллекцию.</span><span class="sxs-lookup"><span data-stu-id="33ae6-136">If the \<Max-substrings\> parameter is added, this takes precedence when your command splits up the collection.</span></span> <span data-ttu-id="33ae6-137">Если включить разделитель как часть выходных данных, команда возвращает разделитель в составе выходных данных. Однако разделение строки для возврата разделителя в качестве части выходных данных не учитывается в качестве разбиения.</span><span class="sxs-lookup"><span data-stu-id="33ae6-137">If you opt to include a delimiter as part of the output, the command returns the delimiter as part of the output; however, splitting the string to return the delimiter as part of output does not count as a split.</span></span>

<span data-ttu-id="33ae6-138">Примеры:</span><span class="sxs-lookup"><span data-stu-id="33ae6-138">Examples:</span></span>

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

<span data-ttu-id="33ae6-139">В следующем примере \<Max-substrings\> значение равно 3.</span><span class="sxs-lookup"><span data-stu-id="33ae6-139">In the following example, \<Max-substrings\> is set to 3.</span></span> <span data-ttu-id="33ae6-140">Это приводит к трем разбиениям строковых значений, но всего за пять строк в результирующем выводе; разделитель включается после разбиения до тех пор, пока не будет достигнуто максимально допустимое число из трех подстрок.</span><span class="sxs-lookup"><span data-stu-id="33ae6-140">This results in three splits of the string values, but a total of five strings in the resulting output; the delimiter is included after the splits, until the maximum of three substrings is reached.</span></span> <span data-ttu-id="33ae6-141">Дополнительные разделители в конечной подстроке становятся частью подстроки.</span><span class="sxs-lookup"><span data-stu-id="33ae6-141">Additional delimiters in the final substring become part of the substring.</span></span>

```powershell
'Chocolate-Vanilla-Strawberry-Blueberry' -split '(-)', 3
```

```output
Chocolate
-
Vanilla
-
Strawberry-Blueberry
```

### \<Max-substrings\>

<span data-ttu-id="33ae6-142">Указывает максимальное число разбиений строки.</span><span class="sxs-lookup"><span data-stu-id="33ae6-142">Specifies the maximum number of times that a string is split.</span></span> <span data-ttu-id="33ae6-143">По умолчанию используются все подстроки, разделенные разделителем.</span><span class="sxs-lookup"><span data-stu-id="33ae6-143">The default is all the substrings split by the delimiter.</span></span> <span data-ttu-id="33ae6-144">Если подстроки больше, они объединяются с конечной подстрокой.</span><span class="sxs-lookup"><span data-stu-id="33ae6-144">If there are more substrings, they are concatenated to the final substring.</span></span> <span data-ttu-id="33ae6-145">Если число подстрок меньше, возвращаются все подстроки.</span><span class="sxs-lookup"><span data-stu-id="33ae6-145">If there are fewer substrings, all the substrings are returned.</span></span> <span data-ttu-id="33ae6-146">Значение 0 и отрицательные значения возвращают все подстроки.</span><span class="sxs-lookup"><span data-stu-id="33ae6-146">A value of 0 and negative values return all the substrings.</span></span>

<span data-ttu-id="33ae6-147">Параметр max-substring не задает максимальное число возвращаемых объектов. его значение равно максимальному количеству разделений строки.</span><span class="sxs-lookup"><span data-stu-id="33ae6-147">Max-substrings does not specify the maximum number of objects that are returned; its value equals the maximum number of times that a string is split.</span></span>
<span data-ttu-id="33ae6-148">При отправке в оператор Split более одной строки (массива строк) ограничение Max-substring применяется к каждой строке отдельно.</span><span class="sxs-lookup"><span data-stu-id="33ae6-148">If you submit more than one string (an array of strings) to the Split operator , the Max-substrings limit is applied to each string separately.</span></span>

<span data-ttu-id="33ae6-149">Пример</span><span class="sxs-lookup"><span data-stu-id="33ae6-149">Example:</span></span>

```powershell
$c = "Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,Neptune"
$c -split ",", 5
```

```output
Mercury
Venus
Earth
Mars
Jupiter,Saturn,Uranus,Neptune
```

### \<ScriptBlock\>

<span data-ttu-id="33ae6-150">Выражение, задающее правила для применения разделителя.</span><span class="sxs-lookup"><span data-stu-id="33ae6-150">An expression that specifies rules for applying the delimiter.</span></span> <span data-ttu-id="33ae6-151">Выражение должно иметь значение $true или $false.</span><span class="sxs-lookup"><span data-stu-id="33ae6-151">The expression must evaluate to $true or $false.</span></span> <span data-ttu-id="33ae6-152">Заключите блок скрипта в фигурные скобки.</span><span class="sxs-lookup"><span data-stu-id="33ae6-152">Enclose the script block in braces.</span></span>

<span data-ttu-id="33ae6-153">Пример</span><span class="sxs-lookup"><span data-stu-id="33ae6-153">Example:</span></span>

```powershell
$c = "Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,Neptune"
$c -split {$_ -eq "e" -or $_ -eq "p"}
```

```output
M
rcury,V
nus,
arth,Mars,Ju
it
r,Saturn,Uranus,N

tun
```

### \<Options\>

<span data-ttu-id="33ae6-154">Заключите имя параметра в кавычки.</span><span class="sxs-lookup"><span data-stu-id="33ae6-154">Enclose the option name in quotation marks.</span></span> <span data-ttu-id="33ae6-155">Параметры допустимы только в том случае, если \<Max-substrings\> параметр используется в инструкции.</span><span class="sxs-lookup"><span data-stu-id="33ae6-155">Options are valid only when the \<Max-substrings\> parameter is used in the statement.</span></span>

<span data-ttu-id="33ae6-156">Для параметра options используется следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="33ae6-156">The syntax for the Options parameter is:</span></span>

```
"SimpleMatch [,IgnoreCase]"

"[RegexMatch] [,IgnoreCase] [,CultureInvariant]
[,IgnorePatternWhitespace] [,ExplicitCapture]
[,Singleline | ,Multiline]"
```

<span data-ttu-id="33ae6-157">Параметры SimpleMatch:</span><span class="sxs-lookup"><span data-stu-id="33ae6-157">The SimpleMatch options are:</span></span>

- <span data-ttu-id="33ae6-158">**SimpleMatch** : Используйте простое сравнение строк при вычислении разделителя.</span><span class="sxs-lookup"><span data-stu-id="33ae6-158">**SimpleMatch** : Use simple string comparison when evaluating the delimiter.</span></span> <span data-ttu-id="33ae6-159">Не может использоваться с Режексматч.</span><span class="sxs-lookup"><span data-stu-id="33ae6-159">Cannot be used with RegexMatch.</span></span>
- <span data-ttu-id="33ae6-160">**IgnoreCase** : принудительное сопоставление без учета регистра, даже если указан оператор-ксплит.</span><span class="sxs-lookup"><span data-stu-id="33ae6-160">**IgnoreCase** : Forces case-insensitive matching, even if the -cSplit operator is specified.</span></span>

<span data-ttu-id="33ae6-161">Параметры Режексматч:</span><span class="sxs-lookup"><span data-stu-id="33ae6-161">The RegexMatch options are:</span></span>

- <span data-ttu-id="33ae6-162">**Режексматч** : используйте сопоставление регулярных выражений для вычисления разделителя.</span><span class="sxs-lookup"><span data-stu-id="33ae6-162">**RegexMatch** : Use regular expression matching to evaluate the delimiter.</span></span> <span data-ttu-id="33ae6-163">Это поведение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="33ae6-163">This is the default behavior.</span></span> <span data-ttu-id="33ae6-164">Не может использоваться с SimpleMatch.</span><span class="sxs-lookup"><span data-stu-id="33ae6-164">Cannot be used with SimpleMatch.</span></span>
- <span data-ttu-id="33ae6-165">**IgnoreCase** : принудительное сопоставление без учета регистра, даже если указан оператор-ксплит.</span><span class="sxs-lookup"><span data-stu-id="33ae6-165">**IgnoreCase** : Forces case-insensitive matching, even if the -cSplit operator is specified.</span></span>
- <span data-ttu-id="33ae6-166">**CultureInvariant** : игнорирует культурные различия в языке, если оценка разделитель.</span><span class="sxs-lookup"><span data-stu-id="33ae6-166">**CultureInvariant** : Ignores cultural differences in language when evaluting the delimiter.</span></span> <span data-ttu-id="33ae6-167">Допустимо только с Режексматч.</span><span class="sxs-lookup"><span data-stu-id="33ae6-167">Valid only with RegexMatch.</span></span>
- <span data-ttu-id="33ae6-168">**IgnorePatternWhitespace** : игнорирует неэкранированные пробелы и комментарии, помеченные знаком решетки (#).</span><span class="sxs-lookup"><span data-stu-id="33ae6-168">**IgnorePatternWhitespace** : Ignores unescaped whitespace and comments marked with the number sign (#).</span></span> <span data-ttu-id="33ae6-169">Допустимо только с Режексматч.</span><span class="sxs-lookup"><span data-stu-id="33ae6-169">Valid only with RegexMatch.</span></span>
- <span data-ttu-id="33ae6-170">**Многострочный** : многострочный режим заставляет `^` и `$` сопоставлять начальную конец каждой строки, а не начало и конец входной строки.</span><span class="sxs-lookup"><span data-stu-id="33ae6-170">**Multiline** : Multiline mode forces `^` and `$` to match the beginning end of every line instead of the beginning and end of the input string.</span></span>
- <span data-ttu-id="33ae6-171">**SingleLine** : режим SingleLine обрабатывает входную строку как *SingleLine* .</span><span class="sxs-lookup"><span data-stu-id="33ae6-171">**Singleline** : Singleline mode treats the input string as a *SingleLine* .</span></span>
  <span data-ttu-id="33ae6-172">Он заставляет `.` символ соответствовать каждому символу (включая символы новой строки) вместо того, чтобы сопоставлять каждый символ, кроме символа новой строки `\n` .</span><span class="sxs-lookup"><span data-stu-id="33ae6-172">It forces the `.` character to match every character (including newlines), instead of matching every character EXCEPT the newline `\n`.</span></span>
- <span data-ttu-id="33ae6-173">**ExplicitCapture** : игнорирует неименованные группы соответствия, чтобы в списке результатов возвращались только явные группы записи.</span><span class="sxs-lookup"><span data-stu-id="33ae6-173">**ExplicitCapture** : Ignores non-named match groups so that only explicit capture groups are returned in the result list.</span></span> <span data-ttu-id="33ae6-174">Допустимо только с Режексматч.</span><span class="sxs-lookup"><span data-stu-id="33ae6-174">Valid only with RegexMatch.</span></span>

## <a name="unary-and-binary-split-operators"></a><span data-ttu-id="33ae6-175">ОПЕРАТОРЫ УНАРного и БИНАРного разделения</span><span class="sxs-lookup"><span data-stu-id="33ae6-175">UNARY and BINARY SPLIT OPERATORS</span></span>

<span data-ttu-id="33ae6-176">Оператор унарного разбиения ( `-split <string>` ) имеет более высокий приоритет, чем запятая.</span><span class="sxs-lookup"><span data-stu-id="33ae6-176">The unary split operator (`-split <string>`) has higher precedence than a comma.</span></span> <span data-ttu-id="33ae6-177">В результате, если отправить разделенный запятыми список строк в оператор унарного разбиения, то разбиение выполняется только на первую строку (перед первой запятой).</span><span class="sxs-lookup"><span data-stu-id="33ae6-177">As a result, if you submit a comma-separated list of strings to the unary split operator, only the first string (before the first comma) is split.</span></span>

<span data-ttu-id="33ae6-178">Чтобы разделить более одной строки, используйте один из следующих шаблонов:</span><span class="sxs-lookup"><span data-stu-id="33ae6-178">Use one of the following patterns to split more than one string:</span></span>

- <span data-ttu-id="33ae6-179">Использование оператора двоичного разделения ( \<string[]\> -Split \<delimiter\> )</span><span class="sxs-lookup"><span data-stu-id="33ae6-179">Use the binary split operator (\<string[]\> -split \<delimiter\>)</span></span>
- <span data-ttu-id="33ae6-180">Заключите все строки в круглые скобки</span><span class="sxs-lookup"><span data-stu-id="33ae6-180">Enclose all the strings in parentheses</span></span>
- <span data-ttu-id="33ae6-181">Сохранить строки в переменной, а затем отправить переменную оператору Split</span><span class="sxs-lookup"><span data-stu-id="33ae6-181">Store the strings in a variable then submit the variable to the split operator</span></span>

<span data-ttu-id="33ae6-182">Рассмотрим следующий пример.</span><span class="sxs-lookup"><span data-stu-id="33ae6-182">Consider the following example:</span></span>

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

## <a name="examples"></a><span data-ttu-id="33ae6-183">Примеры</span><span class="sxs-lookup"><span data-stu-id="33ae6-183">EXAMPLES</span></span>

<span data-ttu-id="33ae6-184">Следующая инструкция разделяет строку на пробел.</span><span class="sxs-lookup"><span data-stu-id="33ae6-184">The following statement splits the string at whitespace.</span></span>

```powershell
-split "Windows PowerShell 2.0`nWindows PowerShell with remoting"
```

```output

Windows
PowerShell
2.0
Windows
PowerShell
with
remoting
```

<span data-ttu-id="33ae6-185">Следующая инструкция разделяет строку на любую запятую.</span><span class="sxs-lookup"><span data-stu-id="33ae6-185">The following statement splits the string at any comma.</span></span>

```powershell
"Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,Neptune" -split ','
```

```output
Mercury
Venus
Earth
Mars
Jupiter
Saturn
Uranus
Neptune
```

<span data-ttu-id="33ae6-186">Следующая инструкция разделяет строку на шаблоне "ER".</span><span class="sxs-lookup"><span data-stu-id="33ae6-186">The following statement splits the string at the pattern "er".</span></span>

```powershell
"Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,Neptune" -split 'er'
```

```output
M
cury,Venus,Earth,Mars,Jupit
,Saturn,Uranus,Neptune
```

<span data-ttu-id="33ae6-187">Следующая инструкция выполняет разбиение с учетом регистра по букве "N".</span><span class="sxs-lookup"><span data-stu-id="33ae6-187">The following statement performs a case-sensitive split at the letter "N".</span></span>

```powershell
"Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,Neptune" -cSplit 'N'
```

```output
Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,
eptune
```

<span data-ttu-id="33ae6-188">Следующая инструкция разделяет строку на "e" и "t".</span><span class="sxs-lookup"><span data-stu-id="33ae6-188">The following statement splits the string at "e" and "t".</span></span>

```powershell
"Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,Neptune" -split '[et]'
```

```output
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

<span data-ttu-id="33ae6-189">Следующая инструкция разделяет строку на "e" и "r", но ограничивает результирующие подстроки до шести подстрок.</span><span class="sxs-lookup"><span data-stu-id="33ae6-189">The following statement splits the string at "e" and "r", but limits the resulting substrings to six substrings.</span></span>

```powershell
"Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,Neptune" -split '[er]', 6
```

```output
M

cu
y,V
nus,
arth,Mars,Jupiter,Saturn,Uranus,Neptune
```

<span data-ttu-id="33ae6-190">Следующая инструкция разделяет строку на три подстроки.</span><span class="sxs-lookup"><span data-stu-id="33ae6-190">The following statement splits a string into three substrings.</span></span>

```powershell
"a,b,c,d,e,f,g,h" -split ",", 3
```

```output
a
b
c,d,e,f,g,h
```

<span data-ttu-id="33ae6-191">Следующая инструкция разделяет две строки на три подстроки.</span><span class="sxs-lookup"><span data-stu-id="33ae6-191">The following statement splits two strings into three substrings.</span></span>
<span data-ttu-id="33ae6-192">(Ограничение применяется к каждой строке независимо друг от друга.)</span><span class="sxs-lookup"><span data-stu-id="33ae6-192">(The limit is applied to each string independently.)</span></span>

```powershell
"a,b,c,d", "e,f,g,h" -split ",", 3
```

```output
a
b
c,d
e
f
g,h
```

<span data-ttu-id="33ae6-193">Следующая инструкция разделяет каждую строку в строке Here в первой цифре.</span><span class="sxs-lookup"><span data-stu-id="33ae6-193">The following statement splits each line in the here-string at the first digit.</span></span> <span data-ttu-id="33ae6-194">Он использует многострочный параметр для распознавания начала каждой строки и строки.</span><span class="sxs-lookup"><span data-stu-id="33ae6-194">It uses the Multiline option to recognize the beginning of each line and string.</span></span>

<span data-ttu-id="33ae6-195">0 представляет значение "вернуть все" для параметра max-substring.</span><span class="sxs-lookup"><span data-stu-id="33ae6-195">The 0 represents the "return all" value of the Max-substrings parameter.</span></span> <span data-ttu-id="33ae6-196">Параметры, например Multiline, можно использовать, только если указано значение Max-substring.</span><span class="sxs-lookup"><span data-stu-id="33ae6-196">You can use options, such as Multiline, only when the Max-substrings value is specified.</span></span>

```powershell
$a = @'
1The first line.
2The second line.
3The third of three lines.
'@
$a -split "^\d", 0, "multiline"
```

```output

The first line.

The second line.

The third of three lines.
```

<span data-ttu-id="33ae6-197">Следующая инструкция использует символ обратной косой черты для экранирования разделителя с точкой (.).</span><span class="sxs-lookup"><span data-stu-id="33ae6-197">The following statement uses the backslash character to escape the dot (.) delimiter.</span></span>

<span data-ttu-id="33ae6-198">При использовании значения по умолчанию Режексматч точка, заключенная в кавычки ("."), интерпретируется так, чтобы соответствовать любому символу, кроме символа новой строки.</span><span class="sxs-lookup"><span data-stu-id="33ae6-198">With the default, RegexMatch, the dot enclosed in quotation marks (".") is interpreted to match any character except for a newline character.</span></span> <span data-ttu-id="33ae6-199">В результате инструкция Split возвращает пустую строку для каждого символа, кроме новой строки.</span><span class="sxs-lookup"><span data-stu-id="33ae6-199">As a result, the Split statement returns a blank line for every character except newline.</span></span>

```powershell
"This.is.a.test" -split "\."
```

```output
This
is
a
test
```

<span data-ttu-id="33ae6-200">В следующей инструкции используется параметр SimpleMatch для направления оператора-split на интерпретацию разделителя с точкой (.) буквально.</span><span class="sxs-lookup"><span data-stu-id="33ae6-200">The following statement uses the SimpleMatch option to direct the -split operator to interpret the dot (.) delimiter literally.</span></span>

<span data-ttu-id="33ae6-201">0 представляет значение "вернуть все" для параметра max-substring.</span><span class="sxs-lookup"><span data-stu-id="33ae6-201">The 0 represents the "return all" value of the Max-substrings parameter.</span></span> <span data-ttu-id="33ae6-202">Параметры, такие как SimpleMatch, можно использовать, только если указано значение Max-substring.</span><span class="sxs-lookup"><span data-stu-id="33ae6-202">You can use options, such as SimpleMatch, only when the Max-substrings value is specified.</span></span>

```powershell
"This.is.a.test" -split ".", 0, "simplematch"
```

```output
This
is
a
test
```

<span data-ttu-id="33ae6-203">Следующая инструкция разделяет строку на один из двух разделителей в зависимости от значения переменной.</span><span class="sxs-lookup"><span data-stu-id="33ae6-203">The following statement splits the string at one of two delimiters, depending on the value of a variable.</span></span>

```powershell
$i = 1
$c = "LastName, FirstName; Address, City, State, Zip"
$c -split $(if ($i -lt 1) {","} else {";"})
```

```output
LastName, FirstName
 Address, City, State, Zip
```

## <a name="see-also"></a><span data-ttu-id="33ae6-204">СМ. ТАКЖЕ</span><span class="sxs-lookup"><span data-stu-id="33ae6-204">SEE ALSO</span></span>

[<span data-ttu-id="33ae6-205">Split-Path</span><span class="sxs-lookup"><span data-stu-id="33ae6-205">Split-Path</span></span>](xref:Microsoft.PowerShell.Management.Split-Path)

[<span data-ttu-id="33ae6-206">about_Operators</span><span class="sxs-lookup"><span data-stu-id="33ae6-206">about_Operators</span></span>](about_Operators.md)

[<span data-ttu-id="33ae6-207">about_Comparison_Operators</span><span class="sxs-lookup"><span data-stu-id="33ae6-207">about_Comparison_Operators</span></span>](about_Comparison_Operators.md)

[<span data-ttu-id="33ae6-208">about_Join</span><span class="sxs-lookup"><span data-stu-id="33ae6-208">about_Join</span></span>](about_Join.md)
