---
description: Описывает правила использования одинарных и двойных кавычек в PowerShell.
keywords: powershell,командлет
Locale: en-US
ms.date: 10/05/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_quoting_rules?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Quoting_Rules
ms.openlocfilehash: 3a858039a9128235d1b920223ca0fcc3d0b0f6c0
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231974"
---
# <a name="about-quoting-rules"></a><span data-ttu-id="8a497-104">О правилах заключения в кавычки</span><span class="sxs-lookup"><span data-stu-id="8a497-104">About Quoting Rules</span></span>

## <a name="short-description"></a><span data-ttu-id="8a497-105">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="8a497-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="8a497-106">Описывает правила использования одинарных и двойных кавычек в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8a497-106">Describes rules for using single and double quotation marks in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="8a497-107">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="8a497-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="8a497-108">Кавычки используются для указания литеральной строки.</span><span class="sxs-lookup"><span data-stu-id="8a497-108">Quotation marks are used to specify a literal string.</span></span> <span data-ttu-id="8a497-109">Строку можно заключать в одинарные кавычки ( `'` ) или двойные кавычки ( `"` ).</span><span class="sxs-lookup"><span data-stu-id="8a497-109">You can enclose a string in single quotation marks (`'`) or double quotation marks (`"`).</span></span>

<span data-ttu-id="8a497-110">Кавычки также используются для создания строки String.</span><span class="sxs-lookup"><span data-stu-id="8a497-110">Quotation marks are also used to create a here-string.</span></span> <span data-ttu-id="8a497-111">Строка Here — это строка, заключенная в одинарные кавычки или двойные кавычки, в которой кавычки обрабатываются буквально.</span><span class="sxs-lookup"><span data-stu-id="8a497-111">A here-string is a single-quoted or double-quoted string in which quotation marks are interpreted literally.</span></span> <span data-ttu-id="8a497-112">Строка here может охватывать несколько строк.</span><span class="sxs-lookup"><span data-stu-id="8a497-112">A here-string can span multiple lines.</span></span> <span data-ttu-id="8a497-113">Все строки в этой строке считаются строками, даже если они не заключены в кавычки.</span><span class="sxs-lookup"><span data-stu-id="8a497-113">All the lines in a here-string are interpreted as strings, even though they are not enclosed in quotation marks.</span></span>

<span data-ttu-id="8a497-114">В командах к удаленным компьютерам кавычки определяют части команды, выполняемые на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="8a497-114">In commands to remote computers, quotation marks define the parts of the command that are run on the remote computer.</span></span> <span data-ttu-id="8a497-115">В удаленном сеансе кавычки также определяют, будут ли переменные в команде интерпретироваться первыми на локальном компьютере или на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="8a497-115">In a remote session, quotation marks also determine whether the variables in a command are interpreted first on the local computer or on the remote computer.</span></span>

### <a name="single-and-double-quoted-strings"></a><span data-ttu-id="8a497-116">СТРОКИ С ОДИНАРНЫМИ И ДВОЙНЫМИ КАВЫЧКАМИ</span><span class="sxs-lookup"><span data-stu-id="8a497-116">SINGLE AND DOUBLE-QUOTED STRINGS</span></span>

<span data-ttu-id="8a497-117">При заключении строки в двойные кавычки (строка, заключенная в двойные кавычки) имена переменных, которым предшествует знак доллара ( `$` ), заменяются значением переменной перед передачей строки в команду для обработки.</span><span class="sxs-lookup"><span data-stu-id="8a497-117">When you enclose a string in double quotation marks (a double-quoted string), variable names that are preceded by a dollar sign (`$`) are replaced with the variable's value before the string is passed to the command for processing.</span></span>

<span data-ttu-id="8a497-118">Пример:</span><span class="sxs-lookup"><span data-stu-id="8a497-118">For example:</span></span>

```powershell
$i = 5
"The value of $i is $i."
```

<span data-ttu-id="8a497-119">Выходные данные этой команды:</span><span class="sxs-lookup"><span data-stu-id="8a497-119">The output of this command is:</span></span>

```Output
The value of 5 is 5.
```

<span data-ttu-id="8a497-120">Кроме того, в строке с двойными кавычками вычисляются выражения, а результат вставляется в строку.</span><span class="sxs-lookup"><span data-stu-id="8a497-120">Also, in a double-quoted string, expressions are evaluated, and the result is inserted in the string.</span></span> <span data-ttu-id="8a497-121">Пример:</span><span class="sxs-lookup"><span data-stu-id="8a497-121">For example:</span></span>

```powershell
"The value of $(2+3) is 5."
```

<span data-ttu-id="8a497-122">Выходные данные этой команды:</span><span class="sxs-lookup"><span data-stu-id="8a497-122">The output of this command is:</span></span>

```Output
The value of 5 is 5.
```

<span data-ttu-id="8a497-123">При заключении строки в одинарные кавычки (строка, состоящих из одной кавычки) строка передается в команду точно так же, как при ее вводе.</span><span class="sxs-lookup"><span data-stu-id="8a497-123">When you enclose a string in single-quotation marks (a single-quoted string), the string is passed to the command exactly as you type it.</span></span> <span data-ttu-id="8a497-124">Подстановка не выполняется.</span><span class="sxs-lookup"><span data-stu-id="8a497-124">No substitution is performed.</span></span> <span data-ttu-id="8a497-125">Пример:</span><span class="sxs-lookup"><span data-stu-id="8a497-125">For example:</span></span>

```powershell
$i = 5
'The value of $i is $i.'
```

<span data-ttu-id="8a497-126">Выходные данные этой команды:</span><span class="sxs-lookup"><span data-stu-id="8a497-126">The output of this command is:</span></span>

```Output
The value $i is $i.
```

<span data-ttu-id="8a497-127">Аналогичным образом выражения в строках с одинарными кавычками не оцениваются.</span><span class="sxs-lookup"><span data-stu-id="8a497-127">Similarly, expressions in single-quoted strings are not evaluated.</span></span> <span data-ttu-id="8a497-128">Они обрабатываются как литералы.</span><span class="sxs-lookup"><span data-stu-id="8a497-128">They are interpreted as literals.</span></span> <span data-ttu-id="8a497-129">Пример:</span><span class="sxs-lookup"><span data-stu-id="8a497-129">For example:</span></span>

```powershell
'The value of $(2+3) is 5.'
```

<span data-ttu-id="8a497-130">Выходные данные этой команды:</span><span class="sxs-lookup"><span data-stu-id="8a497-130">The output of this command is:</span></span>

```Output
The value of $(2+3) is 5.
```

<span data-ttu-id="8a497-131">Чтобы предотвратить замену значения переменной в строке двойных кавычек, используйте символ обратной кавычки ( `` ` `` ) (ASCII 96), который является escape-символом PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8a497-131">To prevent the substitution of a variable value in a double-quoted string, use the backtick character (`` ` ``)(ASCII 96), which is the PowerShell escape character.</span></span>

<span data-ttu-id="8a497-132">В следующем примере символ обратной кавычки, предшествующий первой переменной $i, не доставит PowerShell заменить имя переменной значением.</span><span class="sxs-lookup"><span data-stu-id="8a497-132">In the following example, the backtick character that precedes the first $i variable prevents PowerShell from replacing the variable name with its value.</span></span>
<span data-ttu-id="8a497-133">Пример:</span><span class="sxs-lookup"><span data-stu-id="8a497-133">For example:</span></span>

```powershell
$i = 5
"The value of `$i is $i."
```

<span data-ttu-id="8a497-134">Выходные данные этой команды:</span><span class="sxs-lookup"><span data-stu-id="8a497-134">The output of this command is:</span></span>

```Output
The value $i is 5.
```

<span data-ttu-id="8a497-135">Чтобы в строке отображались двойные кавычки, заключите всю строку в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="8a497-135">To make double-quotation marks appear in a string, enclose the entire string in single quotation marks.</span></span> <span data-ttu-id="8a497-136">Пример:</span><span class="sxs-lookup"><span data-stu-id="8a497-136">For example:</span></span>

```powershell
'As they say, "live and learn."'
```

<span data-ttu-id="8a497-137">Выходные данные этой команды:</span><span class="sxs-lookup"><span data-stu-id="8a497-137">The output of this command is:</span></span>

```Output
As they say, "live and learn."
```

<span data-ttu-id="8a497-138">Можно также заключить строку, заключенную в одинарные кавычки, в строку в двойных кавычках.</span><span class="sxs-lookup"><span data-stu-id="8a497-138">You can also enclose a single-quoted string in a double-quoted string.</span></span> <span data-ttu-id="8a497-139">Пример:</span><span class="sxs-lookup"><span data-stu-id="8a497-139">For example:</span></span>

```powershell
"As they say, 'live and learn.'"
```

<span data-ttu-id="8a497-140">Выходные данные этой команды:</span><span class="sxs-lookup"><span data-stu-id="8a497-140">The output of this command is:</span></span>

```Output
As they say, 'live and learn.'
```

<span data-ttu-id="8a497-141">Или двойные кавычки вокруг двойных кавычек.</span><span class="sxs-lookup"><span data-stu-id="8a497-141">Or, double the quotation marks around a double-quoted phrase.</span></span> <span data-ttu-id="8a497-142">Пример:</span><span class="sxs-lookup"><span data-stu-id="8a497-142">For example:</span></span>

```powershell
"As they say, ""live and learn."""
```

<span data-ttu-id="8a497-143">Выходные данные этой команды:</span><span class="sxs-lookup"><span data-stu-id="8a497-143">The output of this command is:</span></span>

```Output
As they say, "live and learn."
```

<span data-ttu-id="8a497-144">Чтобы включить одинарную кавычку в строку с одинарной кавычкой, используйте вторую последовательную одинарную кавычку.</span><span class="sxs-lookup"><span data-stu-id="8a497-144">To include a single quotation mark in a single-quoted string, use a second consecutive single quote.</span></span> <span data-ttu-id="8a497-145">Пример:</span><span class="sxs-lookup"><span data-stu-id="8a497-145">For example:</span></span>

```powershell
'don''t'
```

<span data-ttu-id="8a497-146">Выходные данные этой команды:</span><span class="sxs-lookup"><span data-stu-id="8a497-146">The output of this command is:</span></span>

```Output
don't
```

<span data-ttu-id="8a497-147">Чтобы заставить PowerShell интерпретировать двойные кавычки буквально, используйте символ обратной черты.</span><span class="sxs-lookup"><span data-stu-id="8a497-147">To force PowerShell to interpret a double quotation mark literally, use a backtick character.</span></span> <span data-ttu-id="8a497-148">Это предотвращает интерпретацию кавычек в PowerShell как строкового разделителя.</span><span class="sxs-lookup"><span data-stu-id="8a497-148">This prevents PowerShell from interpreting the quotation mark as a string delimiter.</span></span> <span data-ttu-id="8a497-149">Пример:</span><span class="sxs-lookup"><span data-stu-id="8a497-149">For example:</span></span>

```powershell
PS> "Use a quotation mark (`") to begin a string."
Use a quotation mark (") to begin a string.
PS> 'Use a quotation mark (`") to begin a string.'
Use a quotation mark (`") to begin a string.
```

<span data-ttu-id="8a497-150">Поскольку содержимое строк с одинарной кавычкой интерпретируется буквально, то символ обратной косой черты рассматривается как литеральный символ и отображается в выходных данных.</span><span class="sxs-lookup"><span data-stu-id="8a497-150">Because the contents of single-quoted strings are interpreted literally, you the backtick character is treated as a literal character and displayed in the output.</span></span>

### <a name="here-strings"></a><span data-ttu-id="8a497-151">СТРОКИ</span><span class="sxs-lookup"><span data-stu-id="8a497-151">HERE-STRINGS</span></span>

<span data-ttu-id="8a497-152">Правила предложения для этой строки немного отличаются.</span><span class="sxs-lookup"><span data-stu-id="8a497-152">The quotation rules for here-strings are slightly different.</span></span>

<span data-ttu-id="8a497-153">Строка Here — это строка, заключенная в одинарные кавычки или двойные кавычки, в которой кавычки обрабатываются буквально.</span><span class="sxs-lookup"><span data-stu-id="8a497-153">A here-string is a single-quoted or double-quoted string in which quotation marks are interpreted literally.</span></span> <span data-ttu-id="8a497-154">Строка here может охватывать несколько строк.</span><span class="sxs-lookup"><span data-stu-id="8a497-154">A here-string can span multiple lines.</span></span> <span data-ttu-id="8a497-155">Все строки в этой строке считаются строками, даже если они не заключены в кавычки.</span><span class="sxs-lookup"><span data-stu-id="8a497-155">All the lines in a here-string are interpreted as strings even though they are not enclosed in quotation marks.</span></span>

<span data-ttu-id="8a497-156">Как и обычные строки, переменные заменяются значениями в строках, заключенных в двойные кавычки.</span><span class="sxs-lookup"><span data-stu-id="8a497-156">Like regular strings, variables are replaced by their values in double-quoted here-strings.</span></span> <span data-ttu-id="8a497-157">В строках с одинарной кавычкой (String) переменные не заменяются значениями.</span><span class="sxs-lookup"><span data-stu-id="8a497-157">In single-quoted here-strings, variables are not replaced by their values.</span></span>

<span data-ttu-id="8a497-158">Здесь можно использовать текстовые строки для любого текста, но они особенно полезны для следующих типов текста:</span><span class="sxs-lookup"><span data-stu-id="8a497-158">You can use here-strings for any text, but they are particularly useful for the following kinds of text:</span></span>

- <span data-ttu-id="8a497-159">Текст, содержащий литеральные кавычки</span><span class="sxs-lookup"><span data-stu-id="8a497-159">Text that contains literal quotation marks</span></span>
- <span data-ttu-id="8a497-160">Несколько строк текста, например текст в HTML или XML</span><span class="sxs-lookup"><span data-stu-id="8a497-160">Multiple lines of text, such as the text in an HTML or XML</span></span>
- <span data-ttu-id="8a497-161">Текст справки для скрипта или документа функции</span><span class="sxs-lookup"><span data-stu-id="8a497-161">The Help text for a script or function document</span></span>

<span data-ttu-id="8a497-162">Строка в строке может иметь любой из следующих форматов, где `<Enter>` представляет скрытый символ перевода строки или перехода на новую строку, который добавляется при нажатии клавиши <kbd>Ввод</kbd> .</span><span class="sxs-lookup"><span data-stu-id="8a497-162">A here-string can have either of the following formats, where `<Enter>` represents the linefeed or newline hidden character that is added when you press the <kbd>ENTER</kbd> key.</span></span>

<span data-ttu-id="8a497-163">Двойные кавычки:</span><span class="sxs-lookup"><span data-stu-id="8a497-163">Double-quotes:</span></span>

```
@"<Enter>
<string> [string] ...<Enter>
"@
```

<span data-ttu-id="8a497-164">Одинарные кавычки:</span><span class="sxs-lookup"><span data-stu-id="8a497-164">Single-quotes:</span></span>

```
@'<Enter>
<string> [string] ...<Enter>
'@
```

<span data-ttu-id="8a497-165">В любом формате закрывающие кавычки должны быть первыми символами в строке.</span><span class="sxs-lookup"><span data-stu-id="8a497-165">In either format, the closing quotation mark must be the first character in the line.</span></span>

<span data-ttu-id="8a497-166">Строка here содержит весь текст между двумя скрытыми символами.</span><span class="sxs-lookup"><span data-stu-id="8a497-166">A here-string contains all the text between the two hidden characters.</span></span> <span data-ttu-id="8a497-167">В этой строке все кавычки обрабатываются буквально.</span><span class="sxs-lookup"><span data-stu-id="8a497-167">In the here-string, all quotation marks are interpreted literally.</span></span> <span data-ttu-id="8a497-168">Пример:</span><span class="sxs-lookup"><span data-stu-id="8a497-168">For example:</span></span>

```powershell
@"
For help, type "get-help"
"@
```

<span data-ttu-id="8a497-169">Выходные данные этой команды:</span><span class="sxs-lookup"><span data-stu-id="8a497-169">The output of this command is:</span></span>

```Output
For help, type "get-help"
```

<span data-ttu-id="8a497-170">Использование строки "строка" может упростить, используя строку в команде.</span><span class="sxs-lookup"><span data-stu-id="8a497-170">Using a here-string can simplify using a string in a command.</span></span> <span data-ttu-id="8a497-171">Пример:</span><span class="sxs-lookup"><span data-stu-id="8a497-171">For example:</span></span>

```powershell
@"
Use a quotation mark (') to begin a string.
"@
```

<span data-ttu-id="8a497-172">Выходные данные этой команды:</span><span class="sxs-lookup"><span data-stu-id="8a497-172">The output of this command is:</span></span>

```Output
Use a quotation mark (') to begin a string.
```

<span data-ttu-id="8a497-173">В строках с одинарными кавычками (строки) переменные обрабатываются буквально и воспроизводится точно.</span><span class="sxs-lookup"><span data-stu-id="8a497-173">In single-quoted here-strings, variables are interpreted literally and reproduced exactly.</span></span> <span data-ttu-id="8a497-174">Пример:</span><span class="sxs-lookup"><span data-stu-id="8a497-174">For example:</span></span>

```powershell
@'
The $profile variable contains the path
of your PowerShell profile.
'@
```

<span data-ttu-id="8a497-175">Выходные данные этой команды:</span><span class="sxs-lookup"><span data-stu-id="8a497-175">The output of this command is:</span></span>

```Output
The $profile variable contains the path
of your PowerShell profile.
```

<span data-ttu-id="8a497-176">В строках, заключенных в двойные кавычки, переменные заменяются значениями.</span><span class="sxs-lookup"><span data-stu-id="8a497-176">In double-quoted here-strings, variables are replaced by their values.</span></span> <span data-ttu-id="8a497-177">Пример:</span><span class="sxs-lookup"><span data-stu-id="8a497-177">For example:</span></span>

```powershell
@"
Even if you have not created a profile,
the path of the profile file is:
$profile.
"@
```

<span data-ttu-id="8a497-178">Выходные данные этой команды:</span><span class="sxs-lookup"><span data-stu-id="8a497-178">The output of this command is:</span></span>

```Output
Even if you have not created a profile,
the path of the profile file is:
C:\Users\User1\Documents\WindowsPowerShell\Microsoft.PowerShell_profile.ps1.
```

<span data-ttu-id="8a497-179">Здесь строки обычно используются для назначения нескольких строк переменной.</span><span class="sxs-lookup"><span data-stu-id="8a497-179">Here-strings are typically used to assign multiple lines to a variable.</span></span> <span data-ttu-id="8a497-180">Например, следующая строка here присваивает $page переменной страницу XML.</span><span class="sxs-lookup"><span data-stu-id="8a497-180">For example, the following here-string assigns a page of XML to the $page variable.</span></span>

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

<span data-ttu-id="8a497-181">Здесь также удобно использовать для ввода `ConvertFrom-StringData` командлет, который преобразует строки в хэш-таблицы в виде строк.</span><span class="sxs-lookup"><span data-stu-id="8a497-181">Here-strings are also a convenient format for input to the `ConvertFrom-StringData` cmdlet, which converts here-strings to hash tables.</span></span>
<span data-ttu-id="8a497-182">Для получения дополнительной информации см. `ConvertFrom-StringData`.</span><span class="sxs-lookup"><span data-stu-id="8a497-182">For more information, see `ConvertFrom-StringData`.</span></span>

## <a name="see-also"></a><span data-ttu-id="8a497-183">СМ. ТАКЖЕ</span><span class="sxs-lookup"><span data-stu-id="8a497-183">SEE ALSO</span></span>

[<span data-ttu-id="8a497-184">about_Special_Characters</span><span class="sxs-lookup"><span data-stu-id="8a497-184">about_Special_Characters</span></span>](about_Special_Characters.md)

[<span data-ttu-id="8a497-185">ConvertFrom-StringData</span><span class="sxs-lookup"><span data-stu-id="8a497-185">ConvertFrom-StringData</span></span>](xref:Microsoft.PowerShell.Utility.ConvertFrom-StringData)
