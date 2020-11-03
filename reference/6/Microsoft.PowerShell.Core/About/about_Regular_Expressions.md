---
description: Описание регулярных выражений в PowerShell.
keywords: powershell,командлет
Locale: en-US
ms.date: 03/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_regular_expressions?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Regular_Expressions
ms.openlocfilehash: 6112c63b6d0c1018b56df85ec6ae919a0285ffc3
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231318"
---
# <a name="about-regular-expressions"></a><span data-ttu-id="327b3-104">О регулярных выражениях</span><span class="sxs-lookup"><span data-stu-id="327b3-104">About Regular Expressions</span></span>

## <a name="short-description"></a><span data-ttu-id="327b3-105">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="327b3-105">Short description</span></span>
<span data-ttu-id="327b3-106">Описание регулярных выражений в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="327b3-106">Describes regular expressions in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="327b3-107">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="327b3-107">Long description</span></span>

> [!NOTE]
> <span data-ttu-id="327b3-108">В этой статье мы покажем синтаксис и методы использования регулярных выражений в PowerShell, но не все описанные выше синтаксисы.</span><span class="sxs-lookup"><span data-stu-id="327b3-108">This article will show you the syntax and methods for using regular expressions in PowerShell, not all syntax is discussed.</span></span> <span data-ttu-id="327b3-109">Более полный справочник см. в разделе [Справочник по языку регулярных выражений](/dotnet/standard/base-types/regular-expression-language-quick-reference).</span><span class="sxs-lookup"><span data-stu-id="327b3-109">For a more complete reference, see the [Regular Expression Language - Quick Reference](/dotnet/standard/base-types/regular-expression-language-quick-reference).</span></span>

<span data-ttu-id="327b3-110">Регулярное выражение — это шаблон, используемый для сопоставления текста.</span><span class="sxs-lookup"><span data-stu-id="327b3-110">A regular expression is a pattern used to match text.</span></span> <span data-ttu-id="327b3-111">Он может состоять из литеральных символов, операторов и других конструкций.</span><span class="sxs-lookup"><span data-stu-id="327b3-111">It can be made up of literal characters, operators, and other constructs.</span></span>

<span data-ttu-id="327b3-112">В этой статье демонстрируется синтаксис регулярных выражений в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="327b3-112">This article demonstrates regular expression syntax in PowerShell.</span></span> <span data-ttu-id="327b3-113">PowerShell имеет несколько операторов и командлетов, использующих регулярные выражения.</span><span class="sxs-lookup"><span data-stu-id="327b3-113">PowerShell has several operators and cmdlets that use regular expressions.</span></span> <span data-ttu-id="327b3-114">Дополнительные сведения о синтаксисе и использовании см. по ссылкам ниже.</span><span class="sxs-lookup"><span data-stu-id="327b3-114">You can read more about their syntax and usage at the links below.</span></span>

- [<span data-ttu-id="327b3-115">Select-String</span><span class="sxs-lookup"><span data-stu-id="327b3-115">Select-String</span></span>](xref:Microsoft.PowerShell.Utility.Select-String)
- [<span data-ttu-id="327b3-116">операторы match и-Replace</span><span class="sxs-lookup"><span data-stu-id="327b3-116">-match and -replace operators</span></span>](about_Comparison_Operators.md)
- [<span data-ttu-id="327b3-117">-Split</span><span class="sxs-lookup"><span data-stu-id="327b3-117">-split</span></span>](about_Split.md)
- [<span data-ttu-id="327b3-118">Оператор Switch с параметром-Regex</span><span class="sxs-lookup"><span data-stu-id="327b3-118">switch statement with -regex option</span></span>](about_Switch.md)

<span data-ttu-id="327b3-119">По умолчанию регулярные выражения PowerShell не учитывают регистр.</span><span class="sxs-lookup"><span data-stu-id="327b3-119">PowerShell regular expressions are case-insensitive by default.</span></span> <span data-ttu-id="327b3-120">Каждый приведенный выше метод имеет другой способ принудительного учета регистра.</span><span class="sxs-lookup"><span data-stu-id="327b3-120">Each method shown above has a different way to force case sensitivity.</span></span>

|       <span data-ttu-id="327b3-121">Метод</span><span class="sxs-lookup"><span data-stu-id="327b3-121">Method</span></span>       |                      <span data-ttu-id="327b3-122">Чувствительность к регистру</span><span class="sxs-lookup"><span data-stu-id="327b3-122">Case Sensitivity</span></span>                      |
| ------------------ | ---------------------------------------------------------- |
| `Select-String`    | <span data-ttu-id="327b3-123">использовать `-CaseSensitive` параметр</span><span class="sxs-lookup"><span data-stu-id="327b3-123">use `-CaseSensitive` switch</span></span>                                |
| <span data-ttu-id="327b3-124">инструкция `switch`</span><span class="sxs-lookup"><span data-stu-id="327b3-124">`switch` statement</span></span> | <span data-ttu-id="327b3-125">Используйте `-casesensitive` параметр</span><span class="sxs-lookup"><span data-stu-id="327b3-125">use the `-casesensitive` option</span></span>                            |
| <span data-ttu-id="327b3-126">операторы</span><span class="sxs-lookup"><span data-stu-id="327b3-126">operators</span></span>          | <span data-ttu-id="327b3-127">Добавить префикс с **"c"** ( `-cmatch` , `-csplit` или `-creplace` )</span><span class="sxs-lookup"><span data-stu-id="327b3-127">prefix with **'c'** (`-cmatch`, `-csplit`, or `-creplace`)</span></span> |

### <a name="character-literals"></a><span data-ttu-id="327b3-128">Символьные литералы</span><span class="sxs-lookup"><span data-stu-id="327b3-128">Character literals</span></span>

<span data-ttu-id="327b3-129">Регулярное выражение может быть литеральным символом или строкой.</span><span class="sxs-lookup"><span data-stu-id="327b3-129">A regular expression can be a literal character or a string.</span></span> <span data-ttu-id="327b3-130">Выражение приводит к тому, что подсистема сопоставляет текст, указанный в точности.</span><span class="sxs-lookup"><span data-stu-id="327b3-130">The expression causes the engine to match the text specified exactly.</span></span>

```powershell
# This statement returns true because book contains the string "oo"
'book' -match 'oo'
```

### <a name="character-classes"></a><span data-ttu-id="327b3-131">Категории знаков</span><span class="sxs-lookup"><span data-stu-id="327b3-131">Character classes</span></span>

<span data-ttu-id="327b3-132">Хотя символьные литералы работают, если вам известно точное шаблон, классы символов позволяют быть менее конкретными.</span><span class="sxs-lookup"><span data-stu-id="327b3-132">While character literals work if you know the exact pattern, character classes allow you to be less specific.</span></span>

#### <a name="character-groups"></a><span data-ttu-id="327b3-133">Группы символов</span><span class="sxs-lookup"><span data-stu-id="327b3-133">Character groups</span></span>

<span data-ttu-id="327b3-134">`[character group]` позволяет сопоставить любое число символов один раз, в то время как `[^character group]` только символы, не находящиеся в группе.</span><span class="sxs-lookup"><span data-stu-id="327b3-134">`[character group]` allows you to match any number of characters one time, while `[^character group]` only matches characters NOT in the group.</span></span>

```powershell
# This expression returns true if the pattern matches big, bog, or bug.
'big' -match 'b[iou]g'
```

<span data-ttu-id="327b3-135">Если список символов для сопоставления содержит символ дефиса ( `-` ), он должен находиться в начале или в конце списка, чтобы отличать его от выражения диапазона символов.</span><span class="sxs-lookup"><span data-stu-id="327b3-135">If your list of characters to match includes the hyphen character (`-`), it must be at the beginning or end of the list to distinguish it from a character range expression.</span></span>

#### <a name="character-ranges"></a><span data-ttu-id="327b3-136">Диапазоны символов</span><span class="sxs-lookup"><span data-stu-id="327b3-136">Character ranges</span></span>

<span data-ttu-id="327b3-137">Шаблон также может быть диапазоном символов.</span><span class="sxs-lookup"><span data-stu-id="327b3-137">A pattern can also be a range of characters.</span></span> <span data-ttu-id="327b3-138">Символы могут быть алфавитными `[A-Z]` , числовыми `[0-9]` или даже основанными на ASCII `[ -~]` (все печатные символы).</span><span class="sxs-lookup"><span data-stu-id="327b3-138">The characters can be alphabetic `[A-Z]`, numeric `[0-9]`, or even ASCII-based `[ -~]` (all printable characters).</span></span>

```powershell
# This expression returns true if the pattern matches any 2 digit number.
42 -match '[0-9][0-9]'
```

#### <a name="numbers"></a><span data-ttu-id="327b3-139">Числа</span><span class="sxs-lookup"><span data-stu-id="327b3-139">Numbers</span></span>

<span data-ttu-id="327b3-140">`\d`Класс символов будет соответствовать любой десятичной цифре.</span><span class="sxs-lookup"><span data-stu-id="327b3-140">The `\d` character class will match any decimal digit.</span></span> <span data-ttu-id="327b3-141">И наоборот, `\D` будет соответствовать любой цифре, отличной от десятичной.</span><span class="sxs-lookup"><span data-stu-id="327b3-141">Conversely, `\D` will match any non-decimal digit.</span></span>

```powershell
# This expression returns true if it matches a server name.
# (Server-01 - Server-99).
'Server-01' -match 'Server-\d\d'
```

#### <a name="word-characters"></a><span data-ttu-id="327b3-142">Символы слов</span><span class="sxs-lookup"><span data-stu-id="327b3-142">Word characters</span></span>

<span data-ttu-id="327b3-143">`\w`Класс символов будет соответствовать любому символу слова `[a-zA-Z_0-9]` .</span><span class="sxs-lookup"><span data-stu-id="327b3-143">The `\w` character class will match any word character `[a-zA-Z_0-9]`.</span></span> <span data-ttu-id="327b3-144">Для соответствия любому символу, не являющемуся буквой, используйте `\W` .</span><span class="sxs-lookup"><span data-stu-id="327b3-144">To match any non-word character, use `\W`.</span></span>

```powershell
# This expression returns true.
# The pattern matches the first word character 'B'.
'Book' -match '\w'
```

#### <a name="wildcards"></a><span data-ttu-id="327b3-145">подстановочные знаки;</span><span class="sxs-lookup"><span data-stu-id="327b3-145">Wildcards</span></span>

<span data-ttu-id="327b3-146">Точка ( `.` ) является символом-шаблоном в регулярных выражениях.</span><span class="sxs-lookup"><span data-stu-id="327b3-146">The period (`.`) is a wildcard character in regular expressions.</span></span> <span data-ttu-id="327b3-147">Он будет соответствовать любому символу, кроме новой строки ( `\n` ).</span><span class="sxs-lookup"><span data-stu-id="327b3-147">It will match any character except a newline (`\n`).</span></span>

```powershell
# This expression returns true.
# The pattern matches any 4 characters except the newline.
'a1\ ' -match '....'
```

#### <a name="whitespace"></a><span data-ttu-id="327b3-148">Пробелы</span><span class="sxs-lookup"><span data-stu-id="327b3-148">Whitespace</span></span>

<span data-ttu-id="327b3-149">Пробелы сопоставляются с помощью `\s` класса символов.</span><span class="sxs-lookup"><span data-stu-id="327b3-149">Whitespace is matched using the `\s` character class.</span></span> <span data-ttu-id="327b3-150">Все символы, отличные от пробельных, сопоставляются с помощью `\S` .</span><span class="sxs-lookup"><span data-stu-id="327b3-150">Any non-whitespace character is matched using `\S`.</span></span> <span data-ttu-id="327b3-151">Также можно использовать символы пространства литерала `' '` .</span><span class="sxs-lookup"><span data-stu-id="327b3-151">Literal space characters `' '` can also be used.</span></span>

```powershell
# This expression returns true.
# The pattern uses both methods to match the space.
' - ' -match '\s- '
```

### <a name="quantifiers"></a><span data-ttu-id="327b3-152">Квантификаторы</span><span class="sxs-lookup"><span data-stu-id="327b3-152">Quantifiers</span></span>

<span data-ttu-id="327b3-153">Кванторы контролируют, сколько экземпляров каждого элемента должно присутствовать во входной строке.</span><span class="sxs-lookup"><span data-stu-id="327b3-153">Quantifiers control how many instances of each element should be present in the input string.</span></span>

<span data-ttu-id="327b3-154">Ниже перечислены некоторые кванторы, доступные в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="327b3-154">The following are a few of the quantifiers available in PowerShell:</span></span>

| <span data-ttu-id="327b3-155">Квантификатор</span><span class="sxs-lookup"><span data-stu-id="327b3-155">Quantifier</span></span> |                <span data-ttu-id="327b3-156">Описание</span><span class="sxs-lookup"><span data-stu-id="327b3-156">Description</span></span>                |
| ---------- | ----------------------------------------- |
| `*`        | <span data-ttu-id="327b3-157">Ноль или более раз.</span><span class="sxs-lookup"><span data-stu-id="327b3-157">Zero or more times.</span></span>                       |
| `+`        | <span data-ttu-id="327b3-158">Один или несколько раз.</span><span class="sxs-lookup"><span data-stu-id="327b3-158">One or more times.</span></span>                        |
| `?`        | <span data-ttu-id="327b3-159">Ноль или один раз.</span><span class="sxs-lookup"><span data-stu-id="327b3-159">Zero or one time.</span></span>                         |
| `{n,m}`    | <span data-ttu-id="327b3-160">Как минимум `n` , но не более `m` раз.</span><span class="sxs-lookup"><span data-stu-id="327b3-160">At least `n`, but no more than `m` times.</span></span> |

<span data-ttu-id="327b3-161">Звездочка ( `*` ) соответствует предыдущему элементу ноль или более раз.</span><span class="sxs-lookup"><span data-stu-id="327b3-161">The asterisk (`*`) matches the previous element zero or more times.</span></span> <span data-ttu-id="327b3-162">Результатом является то, что даже входная строка без элемента будет совпадать.</span><span class="sxs-lookup"><span data-stu-id="327b3-162">The result is that even an input string without the element would be a match.</span></span>

```powershell
# This returns true for all account name strings even if the name is absent.
'ACCOUNT NAME:    Administrator' -match 'ACCOUNT NAME:\s*\w*'
```

<span data-ttu-id="327b3-163">Знак "плюс" ( `+` ) соответствует предыдущему элементу один или более раз.</span><span class="sxs-lookup"><span data-stu-id="327b3-163">The plus sign (`+`) matches the previous element one or more times.</span></span>

```powershell
# This returns true if it matches any server name.
'DC-01' -match '[A-Z]+-\d\d'
```

<span data-ttu-id="327b3-164">Вопросительный знак `?` соответствует предыдущему элементу ноль или один раз.</span><span class="sxs-lookup"><span data-stu-id="327b3-164">The question mark `?` matches the previous element zero or one time.</span></span> <span data-ttu-id="327b3-165">Как и звездочка `*` , она даже будет сопоставлять строки, в которых отсутствует элемент.</span><span class="sxs-lookup"><span data-stu-id="327b3-165">Like asterisk `*`, it will even match strings where the element is absent.</span></span>

```powershell
# This returns true for any server name, even server names without dashes.
'SERVER01' -match '[A-Z]+-?\d\d'
```

<span data-ttu-id="327b3-166">`{n, m}`Квантификатор можно использовать несколькими различными способами, чтобы обеспечить детальный контроль над квантификатором.</span><span class="sxs-lookup"><span data-stu-id="327b3-166">The `{n, m}` quantifier can be used several different ways to allow granular control over the quantifier.</span></span> <span data-ttu-id="327b3-167">Второй элемент `m` и запятая `,` являются необязательными.</span><span class="sxs-lookup"><span data-stu-id="327b3-167">The second element `m` and the comma `,` are optional.</span></span>

| <span data-ttu-id="327b3-168">Квантификатор</span><span class="sxs-lookup"><span data-stu-id="327b3-168">Quantifier</span></span> |                <span data-ttu-id="327b3-169">Описание</span><span class="sxs-lookup"><span data-stu-id="327b3-169">Description</span></span>                 |
| ---------- | ------------------------------------------ |
| `{n}`      | <span data-ttu-id="327b3-170">Совпадение ровно `n` число раз.</span><span class="sxs-lookup"><span data-stu-id="327b3-170">Match EXACTLY `n` number of times.</span></span>         |
| `{n,}`     | <span data-ttu-id="327b3-171">Совпадение по КРАЙНЕй мере с `n` числом раз.</span><span class="sxs-lookup"><span data-stu-id="327b3-171">Match at LEAST `n` number of times.</span></span>        |
| `{n,m}`    | <span data-ttu-id="327b3-172">Совпадение между `n` и `m` числом раз.</span><span class="sxs-lookup"><span data-stu-id="327b3-172">Match between `n` and `m` number of times.</span></span> |

```powershell
# This returns true if it matches any phone number.
'111-222-3333' -match '\d{3}-\d{3}-\d{4}'
```

### <a name="anchors"></a><span data-ttu-id="327b3-173">Привязки</span><span class="sxs-lookup"><span data-stu-id="327b3-173">Anchors</span></span>

<span data-ttu-id="327b3-174">Привязки позволяют вызвать успешное или неудачное выполнение соответствия в зависимости от того, где находится строка во входной строке.</span><span class="sxs-lookup"><span data-stu-id="327b3-174">Anchors allow you to cause a match to succeed or fail based on the matches position within the input string.</span></span>

<span data-ttu-id="327b3-175">Двумя часто используемыми привязками являются `^` и `$` .</span><span class="sxs-lookup"><span data-stu-id="327b3-175">The two commonly used anchors are `^` and `$`.</span></span> <span data-ttu-id="327b3-176">Курсор `^` соответствует началу строки и `$` , который соответствует концу строки.</span><span class="sxs-lookup"><span data-stu-id="327b3-176">The caret `^` matches the start of a string, and `$`, which matches the end of a string.</span></span> <span data-ttu-id="327b3-177">Привязки позволяют сопоставлять текст в определенной позиции, одновременно удаляя ненужные символы.</span><span class="sxs-lookup"><span data-stu-id="327b3-177">The anchors allow you to match your text at a specific position while also discarding unwanted characters.</span></span>

```powershell
# The pattern expects the string 'fish' to be the only thing on the line.
# This returns FALSE.
'fishing' -match '^fish$'
```

> [!NOTE]
> <span data-ttu-id="327b3-178">При определении регулярного выражения `$` , содержащего привязку, обязательно заключите регулярное выражение в одинарные кавычки ( `'` ) вместо двойных кавычек ( `"` ) или PowerShell развернет выражение как переменную.</span><span class="sxs-lookup"><span data-stu-id="327b3-178">When defining a regex containing an `$` anchor, be sure to enclose the regex using single quotes (`'`) instead of double quotes (`"`) or PowerShell will expand the expression as a variable.</span></span>

<span data-ttu-id="327b3-179">При использовании привязок в PowerShell следует понимать разницу между параметрами **SingleLine** и **многострочных** регулярных выражений.</span><span class="sxs-lookup"><span data-stu-id="327b3-179">When using anchors in PowerShell, you should understand the difference between **Singleline** and **Multiline** regular expression options.</span></span>

- <span data-ttu-id="327b3-180">**Многострочный** : многострочный режим заставляет `^` и `$` сопоставлять НАЧАЛЬную конец каждой строки, а не начало и конец входной строки.</span><span class="sxs-lookup"><span data-stu-id="327b3-180">**Multiline** : Multiline mode forces `^` and `$` to match the beginning end of every LINE instead of the beginning and end of the input string.</span></span>
- <span data-ttu-id="327b3-181">**SingleLine** : режим SingleLine обрабатывает входную строку как **SingleLine** .</span><span class="sxs-lookup"><span data-stu-id="327b3-181">**Singleline** : Singleline mode treats the input string as a **SingleLine** .</span></span>
  <span data-ttu-id="327b3-182">Он заставляет `.` символ соответствовать каждому символу (включая символы новой строки) вместо того, чтобы сопоставлять каждый символ, кроме символа новой строки `\n` .</span><span class="sxs-lookup"><span data-stu-id="327b3-182">It forces the `.` character to match every character (including newlines), instead of matching every character EXCEPT the newline `\n`.</span></span>

<span data-ttu-id="327b3-183">Дополнительные сведения об этих параметрах и способах их использования см. в статье [Язык регулярных выражений — краткий справочник](/dotnet/standard/base-types/regular-expression-language-quick-reference).</span><span class="sxs-lookup"><span data-stu-id="327b3-183">To read more about these options and how to use them, visit the [Regular Expression Language - Quick Reference](/dotnet/standard/base-types/regular-expression-language-quick-reference).</span></span>

### <a name="escaping-characters"></a><span data-ttu-id="327b3-184">Экранирование символов</span><span class="sxs-lookup"><span data-stu-id="327b3-184">Escaping characters</span></span>

<span data-ttu-id="327b3-185">Обратная косая черта ( `\` ) используется для экранирования символов, поэтому они не анализируются обработчиком регулярных выражений.</span><span class="sxs-lookup"><span data-stu-id="327b3-185">The backslash (`\`) is used to escape characters so they aren't parsed by the regular expression engine.</span></span>

<span data-ttu-id="327b3-186">Зарезервированы следующие символы: `[]().\^$|?*+{}` .</span><span class="sxs-lookup"><span data-stu-id="327b3-186">The following characters are reserved: `[]().\^$|?*+{}`.</span></span>

<span data-ttu-id="327b3-187">Эти символы в шаблонах необходимо экранировановать, чтобы они совпадали с ними во входных строках.</span><span class="sxs-lookup"><span data-stu-id="327b3-187">You'll need to escape these characters in your patterns to match them in your input strings.</span></span>

```powershell
# This returns true and matches numbers with at least 2 digits of precision.
# The decimal point is escaped using the backslash.
'3.141' -match '3\.\d{2,}'
```

<span data-ttu-id="327b3-188">Существует статический метод класса Regex, который может поэкранировать текст.</span><span class="sxs-lookup"><span data-stu-id="327b3-188">There\`s a static method of the regex class that can escape text for you.</span></span>

```powershell
[regex]::escape('3.\d{2,}')
```

```Output
3\.\\d\{2,}
```

> [!NOTE]
> <span data-ttu-id="327b3-189">Это приводит к экранированию всех зарезервированных символов регулярного выражения, включая существующие обратные косые черты, используемые в классах символов.</span><span class="sxs-lookup"><span data-stu-id="327b3-189">This escapes all reserved regular expression characters, including existing backslashes used in character classes.</span></span> <span data-ttu-id="327b3-190">Обязательно используйте его только в той части шаблона, которая необходима для экранирования.</span><span class="sxs-lookup"><span data-stu-id="327b3-190">Be sure to only use it on the portion of your pattern that you need to escape.</span></span>

#### <a name="other-character-escapes"></a><span data-ttu-id="327b3-191">Другие escape-символы</span><span class="sxs-lookup"><span data-stu-id="327b3-191">Other character escapes</span></span>

<span data-ttu-id="327b3-192">Существуют также зарезервированные escape-символы, которые можно использовать для сопоставления специальных символьных типов.</span><span class="sxs-lookup"><span data-stu-id="327b3-192">There are also reserved character escapes that you can use to match special character types.</span></span>

<span data-ttu-id="327b3-193">Ниже приведены несколько часто используемых escape-символов:</span><span class="sxs-lookup"><span data-stu-id="327b3-193">The following are a few commonly used character escapes:</span></span>

|<span data-ttu-id="327b3-194">Escape-последовательность символов</span><span class="sxs-lookup"><span data-stu-id="327b3-194">Character Escape</span></span>  |<span data-ttu-id="327b3-195">Описание</span><span class="sxs-lookup"><span data-stu-id="327b3-195">Description</span></span>  |
|---------|---------|
|`\t`|<span data-ttu-id="327b3-196">Соответствует символу табуляции</span><span class="sxs-lookup"><span data-stu-id="327b3-196">Matches a tab</span></span>|
|`\n`|<span data-ttu-id="327b3-197">Соответствует символу новой строки</span><span class="sxs-lookup"><span data-stu-id="327b3-197">Matches a newline</span></span>|
|`\r`|<span data-ttu-id="327b3-198">Соответствует символу возврата каретки</span><span class="sxs-lookup"><span data-stu-id="327b3-198">Matches a carriage return</span></span>|

### <a name="groups-captures-and-substitutions"></a><span data-ttu-id="327b3-199">Группы, записи и подстановки</span><span class="sxs-lookup"><span data-stu-id="327b3-199">Groups, Captures, and Substitutions</span></span>

<span data-ttu-id="327b3-200">Конструкции группирования разделяют входную строку на подстроки, которые можно записывать или игнорировать.</span><span class="sxs-lookup"><span data-stu-id="327b3-200">Grouping constructs separate an input string into substrings that can be captured or ignored.</span></span> <span data-ttu-id="327b3-201">Сгруппированные подстроки называются частью выражения.</span><span class="sxs-lookup"><span data-stu-id="327b3-201">Grouped substrings are called subexpressions.</span></span> <span data-ttu-id="327b3-202">По умолчанию части выражения фиксируются в нумерованных группах, но также можно назначать им имена.</span><span class="sxs-lookup"><span data-stu-id="327b3-202">By default subexpressions are captured in numbered groups, though you can assign names to them as well.</span></span>

<span data-ttu-id="327b3-203">Конструкция группирования — это регулярное выражение, заключенное в круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="327b3-203">A grouping construct is a regular expression surrounded by parentheses.</span></span> <span data-ttu-id="327b3-204">Захватывается любой текст, совпадающий с вложенным регулярным выражением.</span><span class="sxs-lookup"><span data-stu-id="327b3-204">Any text matched by the enclosed regular expression is captured.</span></span> <span data-ttu-id="327b3-205">В следующем примере входной текст будет разбиваться на две группы записи.</span><span class="sxs-lookup"><span data-stu-id="327b3-205">The following example will break the input text into two capturing groups.</span></span>

```powershell
'The last logged on user was CONTOSO\jsmith' -match '(.+was )(.+)'
```

```Output
True
```

<span data-ttu-id="327b3-206">Используйте `$Matches` автоматическую переменную **Hashtable** для получения захваченного текста.</span><span class="sxs-lookup"><span data-stu-id="327b3-206">Use the `$Matches` **Hashtable** automatic variable to retrieve captured text.</span></span>
<span data-ttu-id="327b3-207">Текст, представляющий полное совпадение, хранится в разделе Key `0` .</span><span class="sxs-lookup"><span data-stu-id="327b3-207">The text representing the entire match is stored at key `0`.</span></span>

```powershell
$Matches.0
```

```Output
The last logged on user was CONTOSO\jsmith
```

<span data-ttu-id="327b3-208">Записи хранятся в числовых **целочисленных** ключах, которые увеличиваются слева направо.</span><span class="sxs-lookup"><span data-stu-id="327b3-208">Captures are stored in numeric **Integer** keys that increase from left to right.</span></span> <span data-ttu-id="327b3-209">Запись `1` содержит весь текст до имени пользователя, а запись `2` содержит только имя пользователя.</span><span class="sxs-lookup"><span data-stu-id="327b3-209">Capture `1` contains all the text until the username, capture `2` contains just the username.</span></span>

```powershell
$Matches
```

```Output
Name                           Value
----                           -----
2                              CONTOSO\jsmith
1                              The last logged on user was
0                              The last logged on user was CONTOSO\jsmith
```

> [!IMPORTANT]
> <span data-ttu-id="327b3-210">`0`Ключ является **целым числом** .</span><span class="sxs-lookup"><span data-stu-id="327b3-210">The `0` key is an **Integer** .</span></span> <span data-ttu-id="327b3-211">Для доступа к сохраненному значению можно использовать любой метод **Hashtable** .</span><span class="sxs-lookup"><span data-stu-id="327b3-211">You can use any **Hashtable** method to access the value stored.</span></span>
>
> ```
> PS> 'Good Dog' -match 'Dog'
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

#### <a name="named-captures"></a><span data-ttu-id="327b3-212">Именованные записи</span><span class="sxs-lookup"><span data-stu-id="327b3-212">Named Captures</span></span>

<span data-ttu-id="327b3-213">По умолчанию записи хранятся в возрастающем числовом порядке, слева направо.</span><span class="sxs-lookup"><span data-stu-id="327b3-213">By default, captures are stored in ascending numeric order, from left to right.</span></span>
<span data-ttu-id="327b3-214">Можно также присвоить **имя** захваченной группе.</span><span class="sxs-lookup"><span data-stu-id="327b3-214">You can also assign a **name** to a capturing group.</span></span> <span data-ttu-id="327b3-215">Это **имя** станет ключом в `$Matches` автоматической переменной **Hashtable** .</span><span class="sxs-lookup"><span data-stu-id="327b3-215">This **name** becomes a key on the `$Matches` **Hashtable** automatic variable.</span></span>

<span data-ttu-id="327b3-216">Внутри захваченной группы используйте `?<keyname>` для хранения захваченных данных с именованным ключом.</span><span class="sxs-lookup"><span data-stu-id="327b3-216">Inside a capturing group, use `?<keyname>` to store captured data under a named key.</span></span>

```
PS> $string = 'The last logged on user was CONTOSO\jsmith'
PS> $string -match 'was (?<domain>.+)\\(?<user>.+)'
True

PS> $Matches

Name                           Value
----                           -----
domain                         CONTOSO
user                           jsmith
0                              was CONTOSO\jsmith

PS> $Matches.domain
CONTOSO

PS> $Matches.user
jsmith
```

<span data-ttu-id="327b3-217">В следующем примере сохраняется самая новая запись в журнале безопасности Windows.</span><span class="sxs-lookup"><span data-stu-id="327b3-217">The following example stores the newest log entry in the Windows Security Log.</span></span>
<span data-ttu-id="327b3-218">Указанное регулярное выражение извлекает имя пользователя и домен из сообщения и сохраняет их в ключах: **N** для Name и **D** для domain.</span><span class="sxs-lookup"><span data-stu-id="327b3-218">The provided regular expression extracts the username and domain from the message and stores them under the keys: **N** for name and **D** for domain.</span></span>

```powershell
$log = (Get-WinEvent -LogName Security -MaxEvents 1).message
$r = '(?s).*Account Name:\s*(?<N>.*).*Account Domain:\s*(?<D>[A-Z,0-9]*)'
$log -match $r
```

```Output
True
```

```powershell
$Matches
```

```Output
Name                           Value
----                           -----
D                              CONTOSO
N                              jsmith
0                              A process has exited....
```

<span data-ttu-id="327b3-219">Дополнительные сведения см. [в разделе конструкции группирования в регулярных выражениях](/dotnet/standard/base-types/grouping-constructs-in-regular-expressions).</span><span class="sxs-lookup"><span data-stu-id="327b3-219">For more information, see [Grouping Constructs in Regular Expressions](/dotnet/standard/base-types/grouping-constructs-in-regular-expressions).</span></span>

#### <a name="substitutions-in-regular-expressions"></a><span data-ttu-id="327b3-220">Подстановки в регулярных выражениях</span><span class="sxs-lookup"><span data-stu-id="327b3-220">Substitutions in Regular Expressions</span></span>

<span data-ttu-id="327b3-221">Использование регулярных выражений с `-replace` оператором позволяет динамически заменять текст с помощью захваченного текста.</span><span class="sxs-lookup"><span data-stu-id="327b3-221">Using the regular expressions with the `-replace` operator allows you to dynamically replace text using captured text.</span></span>

`<input> -replace <original>, <substitute>`

- <span data-ttu-id="327b3-222">`<input>`: Искомая строка</span><span class="sxs-lookup"><span data-stu-id="327b3-222">`<input>`: The string to be searched</span></span>
- <span data-ttu-id="327b3-223">`<original>`: Регулярное выражение, используемое для поиска во входной строке</span><span class="sxs-lookup"><span data-stu-id="327b3-223">`<original>`: A regular expression used to search the input string</span></span>
- <span data-ttu-id="327b3-224">`<substitute>`: Выражение подстановки регулярного выражения для замены совпадений, обнаруженных во входной строке.</span><span class="sxs-lookup"><span data-stu-id="327b3-224">`<substitute>`: A regular expression substitution expression to replace matches found in the input string.</span></span>

> [!NOTE]
> <span data-ttu-id="327b3-225">`<original>` `<substitute>` Операнды и подчиняются правилам обработчика регулярных выражений, таких как Экранирование символов.</span><span class="sxs-lookup"><span data-stu-id="327b3-225">The `<original>` and `<substitute>` operands are subject to rules of the regular expression engine such as character escaping.</span></span>

<span data-ttu-id="327b3-226">В строке можно ссылаться на захваченные группы `<substitute>` .</span><span class="sxs-lookup"><span data-stu-id="327b3-226">Capturing groups can be referenced in the `<substitute>` string.</span></span> <span data-ttu-id="327b3-227">Подстановка выполняется с помощью `$` символа перед идентификатором группы.</span><span class="sxs-lookup"><span data-stu-id="327b3-227">The substitution is done by using the `$` character before the group identifier.</span></span>

<span data-ttu-id="327b3-228">Существуют два способа ссылки на группы записи по **числу** и **имени** .</span><span class="sxs-lookup"><span data-stu-id="327b3-228">Two ways to reference capturing groups are by **Number** and by **Name** .</span></span>

- <span data-ttu-id="327b3-229">По **числу** групп записи нумеруются слева направо.</span><span class="sxs-lookup"><span data-stu-id="327b3-229">By **Number** - Capturing Groups are numbered from left to right.</span></span>

  ```powershell
  'John D. Smith' -replace '(\w+) (\w+)\. (\w+)', '$1.$2.$3@contoso.com'
  ```

  ```Output
  John.D.Smith@contoso.com
  ```

- <span data-ttu-id="327b3-230">По именам групп также можно ссылаться **по имени.**</span><span class="sxs-lookup"><span data-stu-id="327b3-230">By **Name** - Capturing Groups can also be referenced by name.</span></span>

  ```powershell
  'CONTOSO\Administrator' -replace '\w+\\(?<user>\w+)', 'FABRIKAM\${user}'
  ```

  ```Output
  FABRIKAM\Administrator
  ```

<span data-ttu-id="327b3-231">`$&`Выражение представляет весь текст, соответствующий.</span><span class="sxs-lookup"><span data-stu-id="327b3-231">The `$&` expression represents all the text matched.</span></span>

```powershell
'Gobble' -replace 'Gobble', '$& $&'
```

```Output
Gobble Gobble
```

> [!WARNING]
> <span data-ttu-id="327b3-232">Поскольку `$` символ используется в расширении строки, необходимо использовать литеральные строки с подстановкой или Escape- `$` символ при использовании двойных кавычек.</span><span class="sxs-lookup"><span data-stu-id="327b3-232">Since the `$` character is used in string expansion, you'll need to use literal strings with substitution, or escape the `$` character when using double quotes.</span></span>
>
> ```powershell
> 'Hello World' -replace '(\w+) \w+', '$1 Universe'
> "Hello World" -replace "(\w+) \w+", "`$1 Universe"
> ```
>
> ```Output
> Hello Universe
> Hello Universe
> ```
>
> <span data-ttu-id="327b3-233">Кроме того, если требуется `$` использовать в качестве литерального символа, используйте `$$` вместо обычных escape-символов.</span><span class="sxs-lookup"><span data-stu-id="327b3-233">Additionally, if you want to have the `$` as a literal character, use `$$` instead of the normal escape characters.</span></span> <span data-ttu-id="327b3-234">При использовании двойных кавычек все экземпляры во `$` избежание неправильной замены.</span><span class="sxs-lookup"><span data-stu-id="327b3-234">When using double quotes, still escape all instances of `$` to avoid incorrect substitution.</span></span>
>
> ```powershell
> '5.72' -replace '(.+)', '$$$1'
> "5.72" -replace "(.+)", "`$`$`$1"
> ```
>
> ```Output
> $5.72
> $5.72
> ```

<span data-ttu-id="327b3-235">Дополнительные сведения см. [в разделе подстановки в регулярных выражениях](/dotnet/standard/base-types/substitutions-in-regular-expressions).</span><span class="sxs-lookup"><span data-stu-id="327b3-235">For more information, see [Substitutions in Regular Expressions](/dotnet/standard/base-types/substitutions-in-regular-expressions).</span></span>

## <a name="see-also"></a><span data-ttu-id="327b3-236">См. также статью</span><span class="sxs-lookup"><span data-stu-id="327b3-236">See also</span></span>

[<span data-ttu-id="327b3-237">about_Comparison_Operators</span><span class="sxs-lookup"><span data-stu-id="327b3-237">about_Comparison_Operators</span></span>](about_Comparison_Operators.md)

[<span data-ttu-id="327b3-238">about_Operators</span><span class="sxs-lookup"><span data-stu-id="327b3-238">about_Operators</span></span>](about_Operators.md)
