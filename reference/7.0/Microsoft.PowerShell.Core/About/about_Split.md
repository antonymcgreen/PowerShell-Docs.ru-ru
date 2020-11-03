---
description: Объясняет, как использовать оператор Split для разделения одной или нескольких строк на подстроки.
keywords: powershell,командлет
Locale: en-US
ms.date: 03/24/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_split?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Split
ms.openlocfilehash: ed57cec30577fbd02f7aa317460bf1a73b006685
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93230934"
---
# <a name="about-split"></a><span data-ttu-id="b72f4-104">Сведения о разбиении</span><span class="sxs-lookup"><span data-stu-id="b72f4-104">About Split</span></span>

## <a name="short-description"></a><span data-ttu-id="b72f4-105">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="b72f4-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="b72f4-106">Объясняет, как использовать оператор Split для разделения одной или нескольких строк на подстроки.</span><span class="sxs-lookup"><span data-stu-id="b72f4-106">Explains how to use the Split operator to split one or more strings into substrings.</span></span>

## <a name="long-description"></a><span data-ttu-id="b72f4-107">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="b72f4-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="b72f4-108">Оператор Split разделяет одну или несколько строк на подстроки.</span><span class="sxs-lookup"><span data-stu-id="b72f4-108">The Split operator splits one or more strings into substrings.</span></span> <span data-ttu-id="b72f4-109">Вы можете изменить следующие элементы операции разбиения:</span><span class="sxs-lookup"><span data-stu-id="b72f4-109">You can change the following elements of the Split operation:</span></span>

- <span data-ttu-id="b72f4-110">Разделитель.</span><span class="sxs-lookup"><span data-stu-id="b72f4-110">Delimiter.</span></span> <span data-ttu-id="b72f4-111">По умолчанию используется пробел, но можно указать символы, строки, шаблоны или блоки скриптов, указывающие разделитель.</span><span class="sxs-lookup"><span data-stu-id="b72f4-111">The default is whitespace, but you can specify characters, strings, patterns, or script blocks that specify the delimiter.</span></span> <span data-ttu-id="b72f4-112">Оператор Split в PowerShell использует регулярное выражение в разделителе, а не простой символ.</span><span class="sxs-lookup"><span data-stu-id="b72f4-112">The Split operator in PowerShell uses a regular expression in the delimiter, rather than a simple character.</span></span>
- <span data-ttu-id="b72f4-113">Максимальное число подстрок.</span><span class="sxs-lookup"><span data-stu-id="b72f4-113">Maximum number of substrings.</span></span> <span data-ttu-id="b72f4-114">По умолчанию возвращаются все подстроки.</span><span class="sxs-lookup"><span data-stu-id="b72f4-114">The default is to return all substrings.</span></span> <span data-ttu-id="b72f4-115">Если указать число, меньшее числа подстрок, оставшиеся подстроки объединяются в последнюю подстроку.</span><span class="sxs-lookup"><span data-stu-id="b72f4-115">If you specify a number less than the number of substrings, the remaining substrings are concatenated in the last substring.</span></span>
- <span data-ttu-id="b72f4-116">Параметры, определяющие условия, при которых будет сопоставляться разделитель, например SimpleMatch и Multiline.</span><span class="sxs-lookup"><span data-stu-id="b72f4-116">Options that specify the conditions under which the delimiter is matched, such as SimpleMatch and Multiline.</span></span>

## <a name="syntax"></a><span data-ttu-id="b72f4-117">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b72f4-117">SYNTAX</span></span>

<span data-ttu-id="b72f4-118">На следующей схеме показан синтаксис оператора-split.</span><span class="sxs-lookup"><span data-stu-id="b72f4-118">The following diagram shows the syntax for the -split operator.</span></span>

<span data-ttu-id="b72f4-119">Имена параметров не отображаются в команде.</span><span class="sxs-lookup"><span data-stu-id="b72f4-119">The parameter names do not appear in the command.</span></span> <span data-ttu-id="b72f4-120">Включайте только значения параметров.</span><span class="sxs-lookup"><span data-stu-id="b72f4-120">Include only the parameter values.</span></span> <span data-ttu-id="b72f4-121">Значения должны присутствовать в порядке, указанном в схеме синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="b72f4-121">The values must appear in the order specified in the syntax diagram.</span></span>

```
-Split <String>
-Split (<String[]>)
<String> -Split <Delimiter>[,<Max-substrings>[,"<Options>"]]
<String> -Split {<ScriptBlock>} [,<Max-substrings>]
```

<span data-ttu-id="b72f4-122">Можно заменить `-iSplit` или `-cSplit` для `-split` в любой инструкции двоичного разделения (оператор разбиения, включающий разделитель или блок сценария).</span><span class="sxs-lookup"><span data-stu-id="b72f4-122">You can substitute `-iSplit` or `-cSplit` for `-split` in any binary Split statement (a Split statement that includes a delimiter or script block).</span></span> <span data-ttu-id="b72f4-123">В `-iSplit` `-split` операторах и регистр не учитывается.</span><span class="sxs-lookup"><span data-stu-id="b72f4-123">The `-iSplit` and `-split` operators are case-insensitive.</span></span> <span data-ttu-id="b72f4-124">В `-cSplit` операторе учитывается регистр, что означает, что при применении правил разделителей учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="b72f4-124">The `-cSplit` operator is case-sensitive, meaning that case is considered when the delimiter rules are applied.</span></span>

## <a name="parameters"></a><span data-ttu-id="b72f4-125">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b72f4-125">PARAMETERS</span></span>

### <a name="string-or-string"></a><span data-ttu-id="b72f4-126">\<String\> или \<String[]\></span><span class="sxs-lookup"><span data-stu-id="b72f4-126">\<String\> or \<String[]\></span></span>

<span data-ttu-id="b72f4-127">Указывает одну или несколько строк для разбиения.</span><span class="sxs-lookup"><span data-stu-id="b72f4-127">Specifies one or more strings to be split.</span></span> <span data-ttu-id="b72f4-128">При отправке нескольких строк все строки разбиваются с помощью одних и тех же правил разделителей.</span><span class="sxs-lookup"><span data-stu-id="b72f4-128">If you submit multiple strings, all the strings are split using the same delimiter rules.</span></span>

<span data-ttu-id="b72f4-129">Пример</span><span class="sxs-lookup"><span data-stu-id="b72f4-129">Example:</span></span>

```
-split "red yellow blue green"
red
yellow
blue
green
```

### \<Delimiter\>

<span data-ttu-id="b72f4-130">Символы, которые обозначают конец подстроки.</span><span class="sxs-lookup"><span data-stu-id="b72f4-130">The characters that identify the end of a substring.</span></span> <span data-ttu-id="b72f4-131">По умолчанию разделителем являются пробелы, включая пробелы и непечатаемые символы, например символ новой строки ( \` n) и знак табуляции ( \` t).</span><span class="sxs-lookup"><span data-stu-id="b72f4-131">The default delimiter is whitespace, including spaces and non-printable characters, such as newline (\`n) and tab (\`t).</span></span> <span data-ttu-id="b72f4-132">При разбиении строк разделитель опускается из всех подстрок.</span><span class="sxs-lookup"><span data-stu-id="b72f4-132">When the strings are split, the delimiter is omitted from all the substrings.</span></span> <span data-ttu-id="b72f4-133">Пример</span><span class="sxs-lookup"><span data-stu-id="b72f4-133">Example:</span></span>

```
"Lastname:FirstName:Address" -split ":"
Lastname
FirstName
Address
```

<span data-ttu-id="b72f4-134">По умолчанию разделитель в результатах опускается.</span><span class="sxs-lookup"><span data-stu-id="b72f4-134">By default, the delimiter is omitted from the results.</span></span> <span data-ttu-id="b72f4-135">Чтобы сохранить все или часть разделителя, заключите в круглые скобки часть, которую необходимо сохранить.</span><span class="sxs-lookup"><span data-stu-id="b72f4-135">To preserve all or part of the delimiter, enclose in parentheses the part that you want to preserve.</span></span>
<span data-ttu-id="b72f4-136">Если \<Max-substrings\> параметр добавлен, это имеет приоритет, если команда разделяет коллекцию.</span><span class="sxs-lookup"><span data-stu-id="b72f4-136">If the \<Max-substrings\> parameter is added, this takes precedence when your command splits up the collection.</span></span> <span data-ttu-id="b72f4-137">Если включить разделитель как часть выходных данных, команда возвращает разделитель в составе выходных данных. Однако разделение строки для возврата разделителя в качестве части выходных данных не учитывается в качестве разбиения.</span><span class="sxs-lookup"><span data-stu-id="b72f4-137">If you opt to include a delimiter as part of the output, the command returns the delimiter as part of the output; however, splitting the string to return the delimiter as part of output does not count as a split.</span></span>

<span data-ttu-id="b72f4-138">Примеры:</span><span class="sxs-lookup"><span data-stu-id="b72f4-138">Examples:</span></span>

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

<span data-ttu-id="b72f4-139">В следующем примере \<Max-substrings\> значение равно 3.</span><span class="sxs-lookup"><span data-stu-id="b72f4-139">In the following example, \<Max-substrings\> is set to 3.</span></span> <span data-ttu-id="b72f4-140">Это приводит к трем разбиениям строковых значений, но всего за пять строк в результирующем выводе; разделитель включается после разбиения до тех пор, пока не будет достигнуто максимально допустимое число из трех подстрок.</span><span class="sxs-lookup"><span data-stu-id="b72f4-140">This results in three splits of the string values, but a total of five strings in the resulting output; the delimiter is included after the splits, until the maximum of three substrings is reached.</span></span> <span data-ttu-id="b72f4-141">Дополнительные разделители в конечной подстроке становятся частью подстроки.</span><span class="sxs-lookup"><span data-stu-id="b72f4-141">Additional delimiters in the final substring become part of the substring.</span></span>

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

<span data-ttu-id="b72f4-142">Указывает максимальное число разбиений строки.</span><span class="sxs-lookup"><span data-stu-id="b72f4-142">Specifies the maximum number of times that a string is split.</span></span> <span data-ttu-id="b72f4-143">По умолчанию используются все подстроки, разделенные разделителем.</span><span class="sxs-lookup"><span data-stu-id="b72f4-143">The default is all the substrings split by the delimiter.</span></span> <span data-ttu-id="b72f4-144">Если подстроки больше, они объединяются с конечной подстрокой.</span><span class="sxs-lookup"><span data-stu-id="b72f4-144">If there are more substrings, they are concatenated to the final substring.</span></span> <span data-ttu-id="b72f4-145">Если число подстрок меньше, возвращаются все подстроки.</span><span class="sxs-lookup"><span data-stu-id="b72f4-145">If there are fewer substrings, all the substrings are returned.</span></span> <span data-ttu-id="b72f4-146">Значение 0 возвращает все подстроки.</span><span class="sxs-lookup"><span data-stu-id="b72f4-146">A value of 0 returns all the substrings.</span></span> <span data-ttu-id="b72f4-147">Отрицательные значения возвращают количество подстрок, запрошенных начиная с конца входной строки.</span><span class="sxs-lookup"><span data-stu-id="b72f4-147">Negative values return the amount of substrings requested starting from the end of the input string.</span></span>

> [!NOTE]
> <span data-ttu-id="b72f4-148">В PowerShell 7 добавлена поддержка отрицательных значений.</span><span class="sxs-lookup"><span data-stu-id="b72f4-148">Support for negative values was added in PowerShell 7.</span></span>

<span data-ttu-id="b72f4-149">**Max-substring** не задает максимальное количество возвращаемых объектов.</span><span class="sxs-lookup"><span data-stu-id="b72f4-149">**Max-substrings** does not specify the maximum number of objects that are returned.</span></span> <span data-ttu-id="b72f4-150">Его значение равно максимальному количеству разделений строки.</span><span class="sxs-lookup"><span data-stu-id="b72f4-150">Its value equals the maximum number of times that a string is split.</span></span>
<span data-ttu-id="b72f4-151">Если в оператор отправляется более одной строки (массив строк) `-split` , то ограничение **Max-substring** применяется к каждой строке отдельно.</span><span class="sxs-lookup"><span data-stu-id="b72f4-151">If you submit more than one string (an array of strings) to the `-split` operator, the **Max-substrings** limit is applied to each string separately.</span></span>

<span data-ttu-id="b72f4-152">Пример</span><span class="sxs-lookup"><span data-stu-id="b72f4-152">Example:</span></span>

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

<span data-ttu-id="b72f4-153">Выражение, задающее правила для применения разделителя.</span><span class="sxs-lookup"><span data-stu-id="b72f4-153">An expression that specifies rules for applying the delimiter.</span></span> <span data-ttu-id="b72f4-154">Выражение должно иметь значение $true или $false.</span><span class="sxs-lookup"><span data-stu-id="b72f4-154">The expression must evaluate to $true or $false.</span></span> <span data-ttu-id="b72f4-155">Заключите блок скрипта в фигурные скобки.</span><span class="sxs-lookup"><span data-stu-id="b72f4-155">Enclose the script block in braces.</span></span>

<span data-ttu-id="b72f4-156">Пример</span><span class="sxs-lookup"><span data-stu-id="b72f4-156">Example:</span></span>

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

<span data-ttu-id="b72f4-157">Заключите имя параметра в кавычки.</span><span class="sxs-lookup"><span data-stu-id="b72f4-157">Enclose the option name in quotation marks.</span></span> <span data-ttu-id="b72f4-158">Параметры допустимы только в том случае, если \<Max-substrings\> параметр используется в инструкции.</span><span class="sxs-lookup"><span data-stu-id="b72f4-158">Options are valid only when the \<Max-substrings\> parameter is used in the statement.</span></span>

<span data-ttu-id="b72f4-159">Для параметра options используется следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="b72f4-159">The syntax for the Options parameter is:</span></span>

```
"SimpleMatch [,IgnoreCase]"

"[RegexMatch] [,IgnoreCase] [,CultureInvariant]
[,IgnorePatternWhitespace] [,ExplicitCapture]
[,Singleline | ,Multiline]"
```

<span data-ttu-id="b72f4-160">Параметры SimpleMatch:</span><span class="sxs-lookup"><span data-stu-id="b72f4-160">The SimpleMatch options are:</span></span>

- <span data-ttu-id="b72f4-161">**SimpleMatch** : Используйте простое сравнение строк при вычислении разделителя.</span><span class="sxs-lookup"><span data-stu-id="b72f4-161">**SimpleMatch** : Use simple string comparison when evaluating the delimiter.</span></span> <span data-ttu-id="b72f4-162">Не может использоваться с Режексматч.</span><span class="sxs-lookup"><span data-stu-id="b72f4-162">Cannot be used with RegexMatch.</span></span>
- <span data-ttu-id="b72f4-163">**IgnoreCase** : принудительное сопоставление без учета регистра, даже если указан оператор-ксплит.</span><span class="sxs-lookup"><span data-stu-id="b72f4-163">**IgnoreCase** : Forces case-insensitive matching, even if the -cSplit operator is specified.</span></span>

<span data-ttu-id="b72f4-164">Параметры Режексматч:</span><span class="sxs-lookup"><span data-stu-id="b72f4-164">The RegexMatch options are:</span></span>

- <span data-ttu-id="b72f4-165">**Режексматч** : используйте сопоставление регулярных выражений для вычисления разделителя.</span><span class="sxs-lookup"><span data-stu-id="b72f4-165">**RegexMatch** : Use regular expression matching to evaluate the delimiter.</span></span> <span data-ttu-id="b72f4-166">Это поведение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b72f4-166">This is the default behavior.</span></span> <span data-ttu-id="b72f4-167">Не может использоваться с SimpleMatch.</span><span class="sxs-lookup"><span data-stu-id="b72f4-167">Cannot be used with SimpleMatch.</span></span>
- <span data-ttu-id="b72f4-168">**IgnoreCase** : принудительное сопоставление без учета регистра, даже если указан оператор-ксплит.</span><span class="sxs-lookup"><span data-stu-id="b72f4-168">**IgnoreCase** : Forces case-insensitive matching, even if the -cSplit operator is specified.</span></span>
- <span data-ttu-id="b72f4-169">**CultureInvariant** : игнорирует культурные различия в языке, если оценка разделитель.</span><span class="sxs-lookup"><span data-stu-id="b72f4-169">**CultureInvariant** : Ignores cultural differences in language when evaluting the delimiter.</span></span> <span data-ttu-id="b72f4-170">Допустимо только с Режексматч.</span><span class="sxs-lookup"><span data-stu-id="b72f4-170">Valid only with RegexMatch.</span></span>
- <span data-ttu-id="b72f4-171">**IgnorePatternWhitespace** : игнорирует неэкранированные пробелы и комментарии, помеченные знаком решетки (#).</span><span class="sxs-lookup"><span data-stu-id="b72f4-171">**IgnorePatternWhitespace** : Ignores unescaped whitespace and comments marked with the number sign (#).</span></span> <span data-ttu-id="b72f4-172">Допустимо только с Режексматч.</span><span class="sxs-lookup"><span data-stu-id="b72f4-172">Valid only with RegexMatch.</span></span>
- <span data-ttu-id="b72f4-173">**Многострочный** : многострочный режим заставляет `^` и `$` сопоставлять начальную конец каждой строки, а не начало и конец входной строки.</span><span class="sxs-lookup"><span data-stu-id="b72f4-173">**Multiline** : Multiline mode forces `^` and `$` to match the beginning end of every line instead of the beginning and end of the input string.</span></span>
- <span data-ttu-id="b72f4-174">**SingleLine** : режим SingleLine обрабатывает входную строку как *SingleLine*.</span><span class="sxs-lookup"><span data-stu-id="b72f4-174">**Singleline** : Singleline mode treats the input string as a *SingleLine*.</span></span>
  <span data-ttu-id="b72f4-175">Он заставляет `.` символ соответствовать каждому символу (включая символы новой строки) вместо того, чтобы сопоставлять каждый символ, кроме символа новой строки `\n` .</span><span class="sxs-lookup"><span data-stu-id="b72f4-175">It forces the `.` character to match every character (including newlines), instead of matching every character EXCEPT the newline `\n`.</span></span>
- <span data-ttu-id="b72f4-176">**ExplicitCapture** : игнорирует неименованные группы соответствия, чтобы в списке результатов возвращались только явные группы записи.</span><span class="sxs-lookup"><span data-stu-id="b72f4-176">**ExplicitCapture** : Ignores non-named match groups so that only explicit capture groups are returned in the result list.</span></span> <span data-ttu-id="b72f4-177">Допустимо только с Режексматч.</span><span class="sxs-lookup"><span data-stu-id="b72f4-177">Valid only with RegexMatch.</span></span>

## <a name="unary-and-binary-split-operators"></a><span data-ttu-id="b72f4-178">ОПЕРАТОРЫ УНАРного и БИНАРного разделения</span><span class="sxs-lookup"><span data-stu-id="b72f4-178">UNARY and BINARY SPLIT OPERATORS</span></span>

<span data-ttu-id="b72f4-179">Оператор унарного разбиения ( `-split <string>` ) имеет более высокий приоритет, чем запятая.</span><span class="sxs-lookup"><span data-stu-id="b72f4-179">The unary split operator (`-split <string>`) has higher precedence than a comma.</span></span> <span data-ttu-id="b72f4-180">В результате, если отправить разделенный запятыми список строк в оператор унарного разбиения, то разбиение выполняется только на первую строку (перед первой запятой).</span><span class="sxs-lookup"><span data-stu-id="b72f4-180">As a result, if you submit a comma-separated list of strings to the unary split operator, only the first string (before the first comma) is split.</span></span>

<span data-ttu-id="b72f4-181">Чтобы разделить более одной строки, используйте один из следующих шаблонов:</span><span class="sxs-lookup"><span data-stu-id="b72f4-181">Use one of the following patterns to split more than one string:</span></span>

- <span data-ttu-id="b72f4-182">Использование оператора двоичного разделения ( \<string[]\> -Split \<delimiter\> )</span><span class="sxs-lookup"><span data-stu-id="b72f4-182">Use the binary split operator (\<string[]\> -split \<delimiter\>)</span></span>
- <span data-ttu-id="b72f4-183">Заключите все строки в круглые скобки</span><span class="sxs-lookup"><span data-stu-id="b72f4-183">Enclose all the strings in parentheses</span></span>
- <span data-ttu-id="b72f4-184">Сохранить строки в переменной, а затем отправить переменную оператору Split</span><span class="sxs-lookup"><span data-stu-id="b72f4-184">Store the strings in a variable then submit the variable to the split operator</span></span>

<span data-ttu-id="b72f4-185">Рассмотрим следующий пример.</span><span class="sxs-lookup"><span data-stu-id="b72f4-185">Consider the following example:</span></span>

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

## <a name="examples"></a><span data-ttu-id="b72f4-186">Примеры</span><span class="sxs-lookup"><span data-stu-id="b72f4-186">EXAMPLES</span></span>

<span data-ttu-id="b72f4-187">Следующая инструкция разделяет строку на пробел.</span><span class="sxs-lookup"><span data-stu-id="b72f4-187">The following statement splits the string at whitespace.</span></span>

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

<span data-ttu-id="b72f4-188">Следующая инструкция разделяет строку на любую запятую.</span><span class="sxs-lookup"><span data-stu-id="b72f4-188">The following statement splits the string at any comma.</span></span>

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

<span data-ttu-id="b72f4-189">Следующая инструкция разделяет строку на шаблоне "ER".</span><span class="sxs-lookup"><span data-stu-id="b72f4-189">The following statement splits the string at the pattern "er".</span></span>

```powershell
"Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,Neptune" -split 'er'
```

```Output
M
cury,Venus,Earth,Mars,Jupit
,Saturn,Uranus,Neptune
```

<span data-ttu-id="b72f4-190">Следующая инструкция выполняет разбиение с учетом регистра по букве "N".</span><span class="sxs-lookup"><span data-stu-id="b72f4-190">The following statement performs a case-sensitive split at the letter "N".</span></span>

```powershell
"Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,Neptune" -cSplit 'N'
```

```Output
Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,
eptune
```

<span data-ttu-id="b72f4-191">Следующая инструкция разделяет строку на "e" и "t".</span><span class="sxs-lookup"><span data-stu-id="b72f4-191">The following statement splits the string at "e" and "t".</span></span>

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

<span data-ttu-id="b72f4-192">Следующая инструкция разделяет строку на "e" и "r", но ограничивает результирующие подстроки до шести подстрок.</span><span class="sxs-lookup"><span data-stu-id="b72f4-192">The following statement splits the string at "e" and "r", but limits the resulting substrings to six substrings.</span></span>

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

<span data-ttu-id="b72f4-193">Следующая инструкция разделяет строку на три подстроки.</span><span class="sxs-lookup"><span data-stu-id="b72f4-193">The following statement splits a string into three substrings.</span></span>

```powershell
"a,b,c,d,e,f,g,h" -split ",", 3
```

```Output
a
b
c,d,e,f,g,h
```

<span data-ttu-id="b72f4-194">Следующая инструкция разделяет строку на три подстроки, начиная с конца строки.</span><span class="sxs-lookup"><span data-stu-id="b72f4-194">The following statement splits a string into three substrings starting from the end of the string.</span></span>

```powershell
"a,b,c,d,e,f,g,h" -split ",", -3
```

```Output
a,b,c,d,e,f
g
h
```

<span data-ttu-id="b72f4-195">Следующая инструкция разделяет две строки на три подстроки.</span><span class="sxs-lookup"><span data-stu-id="b72f4-195">The following statement splits two strings into three substrings.</span></span>
<span data-ttu-id="b72f4-196">(Ограничение применяется к каждой строке независимо друг от друга.)</span><span class="sxs-lookup"><span data-stu-id="b72f4-196">(The limit is applied to each string independently.)</span></span>

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

<span data-ttu-id="b72f4-197">Следующая инструкция разделяет каждую строку в строке Here в первой цифре.</span><span class="sxs-lookup"><span data-stu-id="b72f4-197">The following statement splits each line in the here-string at the first digit.</span></span> <span data-ttu-id="b72f4-198">Он использует многострочный параметр для распознавания начала каждой строки и строки.</span><span class="sxs-lookup"><span data-stu-id="b72f4-198">It uses the Multiline option to recognize the beginning of each line and string.</span></span>

<span data-ttu-id="b72f4-199">0 представляет значение "вернуть все" для параметра max-substring.</span><span class="sxs-lookup"><span data-stu-id="b72f4-199">The 0 represents the "return all" value of the Max-substrings parameter.</span></span> <span data-ttu-id="b72f4-200">Параметры, например Multiline, можно использовать, только если указано значение Max-substring.</span><span class="sxs-lookup"><span data-stu-id="b72f4-200">You can use options, such as Multiline, only when the Max-substrings value is specified.</span></span>

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

<span data-ttu-id="b72f4-201">Следующая инструкция использует символ обратной косой черты для экранирования разделителя с точкой (.).</span><span class="sxs-lookup"><span data-stu-id="b72f4-201">The following statement uses the backslash character to escape the dot (.) delimiter.</span></span>

<span data-ttu-id="b72f4-202">При использовании значения по умолчанию Режексматч точка, заключенная в кавычки ("."), интерпретируется так, чтобы соответствовать любому символу, кроме символа новой строки.</span><span class="sxs-lookup"><span data-stu-id="b72f4-202">With the default, RegexMatch, the dot enclosed in quotation marks (".") is interpreted to match any character except for a newline character.</span></span> <span data-ttu-id="b72f4-203">В результате инструкция Split возвращает пустую строку для каждого символа, кроме новой строки.</span><span class="sxs-lookup"><span data-stu-id="b72f4-203">As a result, the Split statement returns a blank line for every character except newline.</span></span>

```powershell
"This.is.a.test" -split "\."
```

```Output
This
is
a
test
```

<span data-ttu-id="b72f4-204">В следующей инструкции используется параметр SimpleMatch для направления оператора-split на интерпретацию разделителя с точкой (.) буквально.</span><span class="sxs-lookup"><span data-stu-id="b72f4-204">The following statement uses the SimpleMatch option to direct the -split operator to interpret the dot (.) delimiter literally.</span></span>

<span data-ttu-id="b72f4-205">0 представляет значение "вернуть все" для параметра max-substring.</span><span class="sxs-lookup"><span data-stu-id="b72f4-205">The 0 represents the "return all" value of the Max-substrings parameter.</span></span> <span data-ttu-id="b72f4-206">Параметры, такие как SimpleMatch, можно использовать, только если указано значение Max-substring.</span><span class="sxs-lookup"><span data-stu-id="b72f4-206">You can use options, such as SimpleMatch, only when the Max-substrings value is specified.</span></span>

```powershell
"This.is.a.test" -split ".", 0, "simplematch"
```

```Output
This
is
a
test
```

<span data-ttu-id="b72f4-207">Следующая инструкция разделяет строку на один из двух разделителей в зависимости от значения переменной.</span><span class="sxs-lookup"><span data-stu-id="b72f4-207">The following statement splits the string at one of two delimiters, depending on the value of a variable.</span></span>

```powershell
$i = 1
$c = "LastName, FirstName; Address, City, State, Zip"
$c -split $(if ($i -lt 1) {","} else {";"})
```

```Output
LastName, FirstName
 Address, City, State, Zip
```

## <a name="see-also"></a><span data-ttu-id="b72f4-208">СМ. ТАКЖЕ</span><span class="sxs-lookup"><span data-stu-id="b72f4-208">SEE ALSO</span></span>

[<span data-ttu-id="b72f4-209">Split-Path</span><span class="sxs-lookup"><span data-stu-id="b72f4-209">Split-Path</span></span>](xref:Microsoft.PowerShell.Management.Split-Path)

[<span data-ttu-id="b72f4-210">about_Operators</span><span class="sxs-lookup"><span data-stu-id="b72f4-210">about_Operators</span></span>](about_Operators.md)

[<span data-ttu-id="b72f4-211">about_Comparison_Operators</span><span class="sxs-lookup"><span data-stu-id="b72f4-211">about_Comparison_Operators</span></span>](about_Comparison_Operators.md)

[<span data-ttu-id="b72f4-212">about_Join</span><span class="sxs-lookup"><span data-stu-id="b72f4-212">about_Join</span></span>](about_Join.md)
