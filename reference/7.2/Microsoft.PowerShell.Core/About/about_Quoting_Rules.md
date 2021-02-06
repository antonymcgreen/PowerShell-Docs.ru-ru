---
description: Описывает правила использования одинарных и двойных кавычек в PowerShell.
Locale: en-US
ms.date: 12/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_quoting_rules?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Quoting_Rules
ms.openlocfilehash: ba4111937245939961689935181be5d547c8e112
ms.sourcegitcommit: 9a86cac80402d8193147058d4ba50e07b26059dd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/15/2020
ms.locfileid: "99599806"
---
# <a name="about-quoting-rules"></a><span data-ttu-id="11a81-103">О правилах заключения в кавычки</span><span class="sxs-lookup"><span data-stu-id="11a81-103">About Quoting Rules</span></span>

## <a name="short-description"></a><span data-ttu-id="11a81-104">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="11a81-104">Short description</span></span>
<span data-ttu-id="11a81-105">Описывает правила использования одинарных и двойных кавычек в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="11a81-105">Describes rules for using single and double quotation marks in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="11a81-106">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="11a81-106">Long description</span></span>

<span data-ttu-id="11a81-107">Кавычки используются для указания литеральной строки.</span><span class="sxs-lookup"><span data-stu-id="11a81-107">Quotation marks are used to specify a literal string.</span></span> <span data-ttu-id="11a81-108">Строку можно заключать в одинарные кавычки ( `'` ) или двойные кавычки ( `"` ).</span><span class="sxs-lookup"><span data-stu-id="11a81-108">You can enclose a string in single quotation marks (`'`) or double quotation marks (`"`).</span></span>

<span data-ttu-id="11a81-109">Кавычки также используются для создания _строки String_.</span><span class="sxs-lookup"><span data-stu-id="11a81-109">Quotation marks are also used to create a _here-string_.</span></span> <span data-ttu-id="11a81-110">Строка Here — это строка, заключенная в одинарные кавычки или двойные кавычки, в которой кавычки обрабатываются буквально.</span><span class="sxs-lookup"><span data-stu-id="11a81-110">A here-string is a single-quoted or double-quoted string in which quotation marks are interpreted literally.</span></span> <span data-ttu-id="11a81-111">Строка here может охватывать несколько строк.</span><span class="sxs-lookup"><span data-stu-id="11a81-111">A here-string can span multiple lines.</span></span> <span data-ttu-id="11a81-112">Все строки в этой строке считаются строками, даже если они не заключены в кавычки.</span><span class="sxs-lookup"><span data-stu-id="11a81-112">All the lines in a here-string are interpreted as strings, even though they are not enclosed in quotation marks.</span></span>

<span data-ttu-id="11a81-113">В командах к удаленным компьютерам кавычки определяют части команды, выполняемые на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="11a81-113">In commands to remote computers, quotation marks define the parts of the command that are run on the remote computer.</span></span> <span data-ttu-id="11a81-114">В удаленном сеансе кавычки также определяют, будут ли переменные в команде интерпретироваться первыми на локальном компьютере или на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="11a81-114">In a remote session, quotation marks also determine whether the variables in a command are interpreted first on the local computer or on the remote computer.</span></span>

## <a name="single-and-double-quoted-strings"></a><span data-ttu-id="11a81-115">Строки с одинарными и двойными кавычками</span><span class="sxs-lookup"><span data-stu-id="11a81-115">Single and double-quoted strings</span></span>

<span data-ttu-id="11a81-116">Строка, заключенная в двойные кавычки, является _расширяемой_ строкой.</span><span class="sxs-lookup"><span data-stu-id="11a81-116">A string enclosed in double quotation marks is an _expandable_ string.</span></span> <span data-ttu-id="11a81-117">Имена переменных, начинающиеся со знака доллара ( `$` ), заменяются значением переменной перед передачей строки в команду для обработки.</span><span class="sxs-lookup"><span data-stu-id="11a81-117">Variable names preceded by a dollar sign (`$`) are replaced with the variable's value before the string is passed to the command for processing.</span></span>

<span data-ttu-id="11a81-118">Пример:</span><span class="sxs-lookup"><span data-stu-id="11a81-118">For example:</span></span>

```powershell
$i = 5
"The value of $i is $i."
```

<span data-ttu-id="11a81-119">Выходные данные этой команды:</span><span class="sxs-lookup"><span data-stu-id="11a81-119">The output of this command is:</span></span>

```Output
The value of 5 is 5.
```

<span data-ttu-id="11a81-120">Кроме того, в строке с двойными кавычками вычисляются выражения, а результат вставляется в строку.</span><span class="sxs-lookup"><span data-stu-id="11a81-120">Also, in a double-quoted string, expressions are evaluated, and the result is inserted in the string.</span></span> <span data-ttu-id="11a81-121">Пример:</span><span class="sxs-lookup"><span data-stu-id="11a81-121">For example:</span></span>

```powershell
"The value of $(2+3) is 5."
```

<span data-ttu-id="11a81-122">Выходные данные этой команды:</span><span class="sxs-lookup"><span data-stu-id="11a81-122">The output of this command is:</span></span>

```Output
The value of 5 is 5.
```

<span data-ttu-id="11a81-123">Строка, заключенная в одинарные кавычки, представляет собой _буквальную_ строку.</span><span class="sxs-lookup"><span data-stu-id="11a81-123">A string enclosed in single-quotation marks is a _verbatim_ string.</span></span> <span data-ttu-id="11a81-124">Строка передается в команду точно так же, как при ее вводе.</span><span class="sxs-lookup"><span data-stu-id="11a81-124">The string is passed to the command exactly as you type it.</span></span> <span data-ttu-id="11a81-125">Подстановка не выполняется.</span><span class="sxs-lookup"><span data-stu-id="11a81-125">No substitution is performed.</span></span>
<span data-ttu-id="11a81-126">Пример:</span><span class="sxs-lookup"><span data-stu-id="11a81-126">For example:</span></span>

```powershell
$i = 5
'The value of $i is $i.'
```

<span data-ttu-id="11a81-127">Выходные данные этой команды:</span><span class="sxs-lookup"><span data-stu-id="11a81-127">The output of this command is:</span></span>

```Output
The value $i is $i.
```

<span data-ttu-id="11a81-128">Аналогичным образом выражения в строках с одинарными кавычками не оцениваются.</span><span class="sxs-lookup"><span data-stu-id="11a81-128">Similarly, expressions in single-quoted strings are not evaluated.</span></span> <span data-ttu-id="11a81-129">Они обрабатываются как литералы.</span><span class="sxs-lookup"><span data-stu-id="11a81-129">They are interpreted as literals.</span></span> <span data-ttu-id="11a81-130">Пример:</span><span class="sxs-lookup"><span data-stu-id="11a81-130">For example:</span></span>

```powershell
'The value of $(2+3) is 5.'
```

<span data-ttu-id="11a81-131">Выходные данные этой команды:</span><span class="sxs-lookup"><span data-stu-id="11a81-131">The output of this command is:</span></span>

```Output
The value of $(2+3) is 5.
```

<span data-ttu-id="11a81-132">Чтобы предотвратить замену значения переменной в строке двойных кавычек, используйте символ обратной кавычки ( `` ` `` ) (ASCII 96), который является escape-символом PowerShell.</span><span class="sxs-lookup"><span data-stu-id="11a81-132">To prevent the substitution of a variable value in a double-quoted string, use the backtick character (`` ` ``)(ASCII 96), which is the PowerShell escape character.</span></span>

<span data-ttu-id="11a81-133">В следующем примере символ обратной кавычки, предшествующий первой переменной, `$i` не доставит PowerShell заменить имя переменной значением.</span><span class="sxs-lookup"><span data-stu-id="11a81-133">In the following example, the backtick character that precedes the first `$i` variable prevents PowerShell from replacing the variable name with its value.</span></span>
<span data-ttu-id="11a81-134">Пример:</span><span class="sxs-lookup"><span data-stu-id="11a81-134">For example:</span></span>

```powershell
$i = 5
"The value of `$i is $i."
```

<span data-ttu-id="11a81-135">Выходные данные этой команды:</span><span class="sxs-lookup"><span data-stu-id="11a81-135">The output of this command is:</span></span>

```Output
The value $i is 5.
```

<span data-ttu-id="11a81-136">Чтобы в строке отображались двойные кавычки, заключите всю строку в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="11a81-136">To make double-quotation marks appear in a string, enclose the entire string in single quotation marks.</span></span> <span data-ttu-id="11a81-137">Пример:</span><span class="sxs-lookup"><span data-stu-id="11a81-137">For example:</span></span>

```powershell
'As they say, "live and learn."'
```

<span data-ttu-id="11a81-138">Выходные данные этой команды:</span><span class="sxs-lookup"><span data-stu-id="11a81-138">The output of this command is:</span></span>

```Output
As they say, "live and learn."
```

<span data-ttu-id="11a81-139">Можно также заключить строку, заключенную в одинарные кавычки, в строку в двойных кавычках.</span><span class="sxs-lookup"><span data-stu-id="11a81-139">You can also enclose a single-quoted string in a double-quoted string.</span></span> <span data-ttu-id="11a81-140">Пример:</span><span class="sxs-lookup"><span data-stu-id="11a81-140">For example:</span></span>

```powershell
"As they say, 'live and learn.'"
```

<span data-ttu-id="11a81-141">Выходные данные этой команды:</span><span class="sxs-lookup"><span data-stu-id="11a81-141">The output of this command is:</span></span>

```Output
As they say, 'live and learn.'
```

<span data-ttu-id="11a81-142">Или двойные кавычки вокруг двойных кавычек.</span><span class="sxs-lookup"><span data-stu-id="11a81-142">Or, double the quotation marks around a double-quoted phrase.</span></span> <span data-ttu-id="11a81-143">Пример:</span><span class="sxs-lookup"><span data-stu-id="11a81-143">For example:</span></span>

```powershell
"As they say, ""live and learn."""
```

<span data-ttu-id="11a81-144">Выходные данные этой команды:</span><span class="sxs-lookup"><span data-stu-id="11a81-144">The output of this command is:</span></span>

```Output
As they say, "live and learn."
```

<span data-ttu-id="11a81-145">Чтобы включить одинарную кавычку в строку с одинарной кавычкой, используйте вторую последовательную одинарную кавычку.</span><span class="sxs-lookup"><span data-stu-id="11a81-145">To include a single quotation mark in a single-quoted string, use a second consecutive single quote.</span></span> <span data-ttu-id="11a81-146">Пример:</span><span class="sxs-lookup"><span data-stu-id="11a81-146">For example:</span></span>

```powershell
'don''t'
```

<span data-ttu-id="11a81-147">Выходные данные этой команды:</span><span class="sxs-lookup"><span data-stu-id="11a81-147">The output of this command is:</span></span>

```Output
don't
```

<span data-ttu-id="11a81-148">Чтобы заставить PowerShell интерпретировать двойные кавычки буквально, используйте символ обратной черты.</span><span class="sxs-lookup"><span data-stu-id="11a81-148">To force PowerShell to interpret a double quotation mark literally, use a backtick character.</span></span> <span data-ttu-id="11a81-149">Это предотвращает интерпретацию кавычек в PowerShell как строкового разделителя.</span><span class="sxs-lookup"><span data-stu-id="11a81-149">This prevents PowerShell from interpreting the quotation mark as a string delimiter.</span></span> <span data-ttu-id="11a81-150">Пример:</span><span class="sxs-lookup"><span data-stu-id="11a81-150">For example:</span></span>

```powershell
PS> "Use a quotation mark (`") to begin a string."
Use a quotation mark (") to begin a string.
PS> 'Use a quotation mark (`") to begin a string.'
Use a quotation mark (`") to begin a string.
```

<span data-ttu-id="11a81-151">Поскольку содержимое строк с одинарной кавычкой интерпретируется буквально, то символ обратной косой черты рассматривается как литеральный символ и отображается в выходных данных.</span><span class="sxs-lookup"><span data-stu-id="11a81-151">Because the contents of single-quoted strings are interpreted literally, you the backtick character is treated as a literal character and displayed in the output.</span></span>

## <a name="here-strings"></a><span data-ttu-id="11a81-152">Строки</span><span class="sxs-lookup"><span data-stu-id="11a81-152">Here-strings</span></span>

<span data-ttu-id="11a81-153">Правила предложения для этой строки немного отличаются.</span><span class="sxs-lookup"><span data-stu-id="11a81-153">The quotation rules for here-strings are slightly different.</span></span>

<span data-ttu-id="11a81-154">Строка Here — это строка, заключенная в одинарные кавычки или двойные кавычки, в которой кавычки обрабатываются буквально.</span><span class="sxs-lookup"><span data-stu-id="11a81-154">A here-string is a single-quoted or double-quoted string in which quotation marks are interpreted literally.</span></span> <span data-ttu-id="11a81-155">Строка here может охватывать несколько строк.</span><span class="sxs-lookup"><span data-stu-id="11a81-155">A here-string can span multiple lines.</span></span> <span data-ttu-id="11a81-156">Все строки в этой строке считаются строками, даже если они не заключены в кавычки.</span><span class="sxs-lookup"><span data-stu-id="11a81-156">All the lines in a here-string are interpreted as strings even though they are not enclosed in quotation marks.</span></span>

<span data-ttu-id="11a81-157">Как и обычные строки, переменные заменяются значениями в строках, заключенных в двойные кавычки.</span><span class="sxs-lookup"><span data-stu-id="11a81-157">Like regular strings, variables are replaced by their values in double-quoted here-strings.</span></span> <span data-ttu-id="11a81-158">В строках с одинарной кавычкой (String) переменные не заменяются значениями.</span><span class="sxs-lookup"><span data-stu-id="11a81-158">In single-quoted here-strings, variables are not replaced by their values.</span></span>

<span data-ttu-id="11a81-159">Здесь можно использовать текстовые строки для любого текста, но они особенно полезны для следующих типов текста:</span><span class="sxs-lookup"><span data-stu-id="11a81-159">You can use here-strings for any text, but they are particularly useful for the following kinds of text:</span></span>

- <span data-ttu-id="11a81-160">Текст, содержащий литеральные кавычки</span><span class="sxs-lookup"><span data-stu-id="11a81-160">Text that contains literal quotation marks</span></span>
- <span data-ttu-id="11a81-161">Несколько строк текста, например текст в HTML или XML</span><span class="sxs-lookup"><span data-stu-id="11a81-161">Multiple lines of text, such as the text in an HTML or XML</span></span>
- <span data-ttu-id="11a81-162">Текст справки для скрипта или документа функции</span><span class="sxs-lookup"><span data-stu-id="11a81-162">The Help text for a script or function document</span></span>

<span data-ttu-id="11a81-163">Строка в строке может иметь любой из следующих форматов, где `<Enter>` представляет скрытый символ перевода строки или перехода на новую строку, который добавляется при нажатии клавиши <kbd>Ввод</kbd> .</span><span class="sxs-lookup"><span data-stu-id="11a81-163">A here-string can have either of the following formats, where `<Enter>` represents the linefeed or newline hidden character that is added when you press the <kbd>ENTER</kbd> key.</span></span>

<span data-ttu-id="11a81-164">Двойные кавычки:</span><span class="sxs-lookup"><span data-stu-id="11a81-164">Double-quotes:</span></span>

```
@"<Enter>
<string> [string] ...<Enter>
"@
```

<span data-ttu-id="11a81-165">Одинарные кавычки:</span><span class="sxs-lookup"><span data-stu-id="11a81-165">Single-quotes:</span></span>

```
@'<Enter>
<string> [string] ...<Enter>
'@
```

<span data-ttu-id="11a81-166">В любом формате закрывающие кавычки должны быть первыми символами в строке.</span><span class="sxs-lookup"><span data-stu-id="11a81-166">In either format, the closing quotation mark must be the first character in the line.</span></span>

<span data-ttu-id="11a81-167">Строка here содержит весь текст между двумя скрытыми символами.</span><span class="sxs-lookup"><span data-stu-id="11a81-167">A here-string contains all the text between the two hidden characters.</span></span> <span data-ttu-id="11a81-168">В этой строке все кавычки обрабатываются буквально.</span><span class="sxs-lookup"><span data-stu-id="11a81-168">In the here-string, all quotation marks are interpreted literally.</span></span> <span data-ttu-id="11a81-169">Пример:</span><span class="sxs-lookup"><span data-stu-id="11a81-169">For example:</span></span>

```powershell
@"
For help, type "get-help"
"@
```

<span data-ttu-id="11a81-170">Выходные данные этой команды:</span><span class="sxs-lookup"><span data-stu-id="11a81-170">The output of this command is:</span></span>

```Output
For help, type "get-help"
```

<span data-ttu-id="11a81-171">Использование строки "строка" может упростить, используя строку в команде.</span><span class="sxs-lookup"><span data-stu-id="11a81-171">Using a here-string can simplify using a string in a command.</span></span> <span data-ttu-id="11a81-172">Пример:</span><span class="sxs-lookup"><span data-stu-id="11a81-172">For example:</span></span>

```powershell
@"
Use a quotation mark (') to begin a string.
"@
```

<span data-ttu-id="11a81-173">Выходные данные этой команды:</span><span class="sxs-lookup"><span data-stu-id="11a81-173">The output of this command is:</span></span>

```Output
Use a quotation mark (') to begin a string.
```

<span data-ttu-id="11a81-174">В строках с одинарными кавычками (строки) переменные обрабатываются буквально и воспроизводится точно.</span><span class="sxs-lookup"><span data-stu-id="11a81-174">In single-quoted here-strings, variables are interpreted literally and reproduced exactly.</span></span> <span data-ttu-id="11a81-175">Пример:</span><span class="sxs-lookup"><span data-stu-id="11a81-175">For example:</span></span>

```powershell
@'
The $profile variable contains the path
of your PowerShell profile.
'@
```

<span data-ttu-id="11a81-176">Выходные данные этой команды:</span><span class="sxs-lookup"><span data-stu-id="11a81-176">The output of this command is:</span></span>

```Output
The $profile variable contains the path
of your PowerShell profile.
```

<span data-ttu-id="11a81-177">В строках, заключенных в двойные кавычки, переменные заменяются значениями.</span><span class="sxs-lookup"><span data-stu-id="11a81-177">In double-quoted here-strings, variables are replaced by their values.</span></span> <span data-ttu-id="11a81-178">Пример:</span><span class="sxs-lookup"><span data-stu-id="11a81-178">For example:</span></span>

```powershell
@"
Even if you have not created a profile,
the path of the profile file is:
$profile.
"@
```

<span data-ttu-id="11a81-179">Выходные данные этой команды:</span><span class="sxs-lookup"><span data-stu-id="11a81-179">The output of this command is:</span></span>

```Output
Even if you have not created a profile,
the path of the profile file is:
C:\Users\User1\Documents\WindowsPowerShell\Microsoft.PowerShell_profile.ps1.
```

<span data-ttu-id="11a81-180">Здесь строки обычно используются для назначения нескольких строк переменной.</span><span class="sxs-lookup"><span data-stu-id="11a81-180">Here-strings are typically used to assign multiple lines to a variable.</span></span> <span data-ttu-id="11a81-181">Например, следующая строка here присваивает $page переменной страницу XML.</span><span class="sxs-lookup"><span data-stu-id="11a81-181">For example, the following here-string assigns a page of XML to the $page variable.</span></span>

```powershell
$page = [XML] @"
<command:command xmlns:maml="http://schemas.microsoft.com/maml/2004/10"
xmlns:command="http://schemas.microsoft.com/maml/dev/command/2004/10"
xmlns:dev="http://schemas.microsoft.com/maml/dev/2004/10">
<command:details>
        <command:name>
               Format-Table
        </command:name>
        <maml:description>
            <maml:para>Formats the output as a table.</maml:para>
        </maml:description>
        <command:verb>format</command:verb>
        <command:noun>table</command:noun>
        <dev:version></dev:version>
</command:details>
...
</command:command>
"@
```

<span data-ttu-id="11a81-182">Здесь также удобно использовать для ввода `ConvertFrom-StringData` командлет, который преобразует строки в хэш-таблицы в виде строк.</span><span class="sxs-lookup"><span data-stu-id="11a81-182">Here-strings are also a convenient format for input to the `ConvertFrom-StringData` cmdlet, which converts here-strings to hash tables.</span></span>
<span data-ttu-id="11a81-183">Для получения дополнительной информации см. `ConvertFrom-StringData`.</span><span class="sxs-lookup"><span data-stu-id="11a81-183">For more information, see `ConvertFrom-StringData`.</span></span>

## <a name="see-also"></a><span data-ttu-id="11a81-184">См. также</span><span class="sxs-lookup"><span data-stu-id="11a81-184">See also</span></span>

[<span data-ttu-id="11a81-185">about_Special_Characters</span><span class="sxs-lookup"><span data-stu-id="11a81-185">about_Special_Characters</span></span>](about_Special_Characters.md)

[<span data-ttu-id="11a81-186">ConvertFrom-StringData</span><span class="sxs-lookup"><span data-stu-id="11a81-186">ConvertFrom-StringData</span></span>](xref:Microsoft.PowerShell.Utility.ConvertFrom-StringData)
