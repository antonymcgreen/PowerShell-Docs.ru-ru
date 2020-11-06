---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/21/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertfrom-stringdata?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertFrom-StringData
ms.openlocfilehash: 8ffb7a33bb1b4b5409c48445b88a8eb58f9b93b9
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93229081"
---
# <span data-ttu-id="3159e-103">ConvertFrom-StringData</span><span class="sxs-lookup"><span data-stu-id="3159e-103">ConvertFrom-StringData</span></span>

## <span data-ttu-id="3159e-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="3159e-104">SYNOPSIS</span></span>
<span data-ttu-id="3159e-105">Преобразует строку, содержащую одну или несколько пар типа ключ-значение в хэш-таблицу.</span><span class="sxs-lookup"><span data-stu-id="3159e-105">Converts a string containing one or more key and value pairs to a hash table.</span></span>

## <span data-ttu-id="3159e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3159e-106">SYNTAX</span></span>

### <span data-ttu-id="3159e-107">Все</span><span class="sxs-lookup"><span data-stu-id="3159e-107">All</span></span>

```
ConvertFrom-StringData [-StringData] <String> [<CommonParameters>]
```

## <span data-ttu-id="3159e-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3159e-108">DESCRIPTION</span></span>

<span data-ttu-id="3159e-109">`ConvertFrom-StringData`Командлет преобразует строку, содержащую одну или несколько пар "ключ — значение", в хэш-таблицу.</span><span class="sxs-lookup"><span data-stu-id="3159e-109">The `ConvertFrom-StringData` cmdlet converts a string that contains one or more key and value pairs into a hash table.</span></span> <span data-ttu-id="3159e-110">Так как каждая пара "ключ-значение" должна находиться в отдельной строке, в качестве входного формата часто используются строки.</span><span class="sxs-lookup"><span data-stu-id="3159e-110">Because each key-value pair must be on a separate line, here-strings are often used as the input format.</span></span> <span data-ttu-id="3159e-111">По умолчанию **ключ** должен быть отделен от **значения** знаком равенства ( `=` ).</span><span class="sxs-lookup"><span data-stu-id="3159e-111">By default, the **key** must be separated from the **value** by an equals sign (`=`) character.</span></span>

<span data-ttu-id="3159e-112">`ConvertFrom-StringData`Командлет считается безопасным командлетом, который можно использовать в `DATA` разделе скрипта или функции.</span><span class="sxs-lookup"><span data-stu-id="3159e-112">The `ConvertFrom-StringData` cmdlet is considered to be a safe cmdlet that can be used in the `DATA` section of a script or function.</span></span> <span data-ttu-id="3159e-113">При использовании в `DATA` разделе содержимое строки должно соответствовать правилам для раздела данных.</span><span class="sxs-lookup"><span data-stu-id="3159e-113">When used in a `DATA` section, the contents of the string must conform to the rules for a DATA section.</span></span> <span data-ttu-id="3159e-114">Дополнительные сведения см. в разделе [about_Data_Sections](../Microsoft.PowerShell.Core/About/about_Data_Sections.md).</span><span class="sxs-lookup"><span data-stu-id="3159e-114">For more information, see [about_Data_Sections](../Microsoft.PowerShell.Core/About/about_Data_Sections.md).</span></span>

<span data-ttu-id="3159e-115">`ConvertFrom-StringData` поддерживает последовательности escape-символов, которые разрешены обычными средствами машинного перевода.</span><span class="sxs-lookup"><span data-stu-id="3159e-115">`ConvertFrom-StringData` supports escape character sequences that are allowed by conventional machine translation tools.</span></span> <span data-ttu-id="3159e-116">То есть командлет может интерпретировать обратные косые черты ( `\` ) в виде escape-символов в строковых данных с помощью [метода Regex. Unescape](/dotnet/api/system.text.regularexpressions.regex.unescape)вместо символа обратной кавычки PowerShell ( \` ), который обычно сигнализирует об окончании строки в скрипте.</span><span class="sxs-lookup"><span data-stu-id="3159e-116">That is, the cmdlet can interpret backslashes (`\`) as escape characters in the string data by using the [Regex.Unescape Method](/dotnet/api/system.text.regularexpressions.regex.unescape), instead of the PowerShell backtick character (\`) that would normally signal the end of a line in a script.</span></span> <span data-ttu-id="3159e-117">Внутри строки here символ обратного апострофа не работает.</span><span class="sxs-lookup"><span data-stu-id="3159e-117">Inside the here-string, the backtick character does not work.</span></span> <span data-ttu-id="3159e-118">Можно также сохранить литеральную обратную косую черту в результатах, отменив ее на предшествующую обратную косую черту следующим образом: `\\` .</span><span class="sxs-lookup"><span data-stu-id="3159e-118">You can also preserve a literal backslash in your results by escaping it with a preceding backslash, like this: `\\`.</span></span> <span data-ttu-id="3159e-119">Неэкранированные символы обратной косой черты, например часто используемые в путях к файлам, могут при обработке расцениваться как недопустимые escape-символы.</span><span class="sxs-lookup"><span data-stu-id="3159e-119">Unescaped backslash characters, such as those that are commonly used in file paths, can render as illegal escape sequences in your results.</span></span>

## <span data-ttu-id="3159e-120">Примеры</span><span class="sxs-lookup"><span data-stu-id="3159e-120">EXAMPLES</span></span>

### <span data-ttu-id="3159e-121">Пример 1. Преобразование строки с одним предложением в кавычки в хэш-таблицу</span><span class="sxs-lookup"><span data-stu-id="3159e-121">Example 1: Convert a single-quoted here-string to a hash table</span></span>

<span data-ttu-id="3159e-122">В этом примере в хэш-таблицу преобразуется строка сообщения пользователя с одинарной кавычкой.</span><span class="sxs-lookup"><span data-stu-id="3159e-122">This example converts a single-quoted here-string of user messages into a hash table.</span></span> <span data-ttu-id="3159e-123">В строках с одиночными кавычками значения переменных не подставляются и выражения не вычисляются.</span><span class="sxs-lookup"><span data-stu-id="3159e-123">In a single-quoted string, values are not substituted for variables and expressions are not evaluated.</span></span>
<span data-ttu-id="3159e-124">`ConvertFrom-StringData`Командлет преобразует значение `$Here` переменной в хэш-таблицу.</span><span class="sxs-lookup"><span data-stu-id="3159e-124">The `ConvertFrom-StringData` cmdlet converts the value in the `$Here` variable to a hash table.</span></span>

```powershell
$Here = @'
Msg1 = The string parameter is required.
Msg2 = Credentials are required for this command.
Msg3 = The specified variable does not exist.
'@
ConvertFrom-StringData -StringData $Here
```

```Output
Name                           Value
----                           -----
Msg3                           The specified variable does not exist.
Msg2                           Credentials are required for this command.
Msg1                           The string parameter is required.
```

### <span data-ttu-id="3159e-125">Пример 2. Преобразование строки, содержащей комментарий</span><span class="sxs-lookup"><span data-stu-id="3159e-125">Example 2: Convert a here-string containing a comment</span></span>

<span data-ttu-id="3159e-126">В этом примере преобразуется строка, содержащая комментарий и несколько пар "ключ-значение", в хэш-таблицу.</span><span class="sxs-lookup"><span data-stu-id="3159e-126">This example converts a here-string that contains a comment and multiple key-value pairs into a hash table.</span></span>

```powershell
ConvertFrom-StringData -StringData @'
Name = Disks.ps1

# Category is optional.

Category = Storage
Cost = Free
'@
```

```Output
Name                           Value
----                           -----
Cost                           Free
Category                       Storage
Name                           Disks.ps1
```

<span data-ttu-id="3159e-127">Значением параметра **StringData** является строка String, а не переменная, содержащая строку String.</span><span class="sxs-lookup"><span data-stu-id="3159e-127">The value of the **StringData** parameter is a here-string, instead of a variable that contains a here-string.</span></span> <span data-ttu-id="3159e-128">Допустимы оба формата.</span><span class="sxs-lookup"><span data-stu-id="3159e-128">Either format is valid.</span></span> <span data-ttu-id="3159e-129">Строка here содержит комментарий об одной из строк.</span><span class="sxs-lookup"><span data-stu-id="3159e-129">The here-string includes a comment about one of the strings.</span></span>
<span data-ttu-id="3159e-130">`ConvertFrom-StringData` игнорирует однострочные комментарии, но `#` символ должен быть первым символом, не являющимся пробелом в строке.</span><span class="sxs-lookup"><span data-stu-id="3159e-130">`ConvertFrom-StringData` ignores single-line comments, but the `#` character must be the first non-whitespace character on the line.</span></span> <span data-ttu-id="3159e-131">Все символы в строке после символов `#` игнорируются.</span><span class="sxs-lookup"><span data-stu-id="3159e-131">All characters on the line after the `#` are ignored.</span></span>

### <span data-ttu-id="3159e-132">Пример 3. Преобразование строки в хэш-таблицу</span><span class="sxs-lookup"><span data-stu-id="3159e-132">Example 3: Convert a string to a hash table</span></span>

<span data-ttu-id="3159e-133">Этот пример преобразует обычную строку в двойных кавычках (а не строку) в хэш-таблицу и сохраняет ее в `$A` переменной.</span><span class="sxs-lookup"><span data-stu-id="3159e-133">This example converts a regular double-quoted string (not a here-string) into a hash table and saves it in the `$A` variable.</span></span>

```powershell
$A = ConvertFrom-StringData -StringData "Top = Red `n Bottom = Blue"
$A
```

```Output
Name             Value
----             -----
Bottom           Blue
Top              Red
```

<span data-ttu-id="3159e-134">Для соответствия условию, что каждая пара «ключ-значение» должна находиться в отдельной строке, в строке используется символ новой строки в PowerShell ( \` n) для разделения пар.</span><span class="sxs-lookup"><span data-stu-id="3159e-134">To satisfy the condition that each key-value pair must be on a separate line, the string uses the PowerShell newline character (\`n) to separate the pairs.</span></span>

### <span data-ttu-id="3159e-135">Пример 4. Использование ConvertFrom-StringData в разделе данных скрипта</span><span class="sxs-lookup"><span data-stu-id="3159e-135">Example 4: Use ConvertFrom-StringData in the DATA section of a script</span></span>

<span data-ttu-id="3159e-136">В этом примере показана `ConvertFrom-StringData` команда, используемая в разделе данных скрипта.</span><span class="sxs-lookup"><span data-stu-id="3159e-136">This example shows a `ConvertFrom-StringData` command used in the DATA section of a script.</span></span>
<span data-ttu-id="3159e-137">Инструкции, расположенные ниже раздела DATA, служат для вывода текста для пользователя.</span><span class="sxs-lookup"><span data-stu-id="3159e-137">The statements below the DATA section display the text to the user.</span></span>

```powershell
$TextMsgs = DATA {
ConvertFrom-StringData @'
Text001 = The $Notebook variable contains the name of the user's system notebook.
Text002 = The $MyNotebook variable contains the name of the user's private notebook.
'@
}
$TextMsgs
```

```Output
Name             Value
----             -----
Text001          The $Notebook variable contains the name of the user's system notebook.
Text002          The $MyNotebook variable contains the name of the user's private notebook.
```

<span data-ttu-id="3159e-138">Так как текст содержит имена переменных, его необходимо заключить в одиночные кавычки, чтобы переменные интерпретировались как текст и вместо них не подставлялись значения.</span><span class="sxs-lookup"><span data-stu-id="3159e-138">Because the text includes variable names, it must be enclosed in a single-quoted string so that the variables are interpreted literally and not expanded.</span></span> <span data-ttu-id="3159e-139">В разделе **Data** не допускаются переменные.</span><span class="sxs-lookup"><span data-stu-id="3159e-139">Variables are not permitted in the **DATA** section.</span></span>

### <span data-ttu-id="3159e-140">Пример 5. Использование оператора конвейера для передачи строки</span><span class="sxs-lookup"><span data-stu-id="3159e-140">Example 5: Use the pipeline operator to pass a string</span></span>

<span data-ttu-id="3159e-141">В этом примере показано, как можно использовать оператор конвейера ( `|` ) для отправки строки в `ConvertFrom-StringData` .</span><span class="sxs-lookup"><span data-stu-id="3159e-141">This example shows that you can use a pipeline operator (`|`) to send a string to `ConvertFrom-StringData`.</span></span> <span data-ttu-id="3159e-142">Значение `$Here` переменной передается в, `ConvertFrom-StringData` а результат — в `$Hash` переменную.</span><span class="sxs-lookup"><span data-stu-id="3159e-142">The the value of the `$Here` variable is piped to `ConvertFrom-StringData` and the result in the `$Hash` variable.</span></span>

```powershell
$Here = @'
Msg1 = The string parameter is required.
Msg2 = Credentials are required for this command.
Msg3 = The specified variable does not exist.
'@
$Hash = $Here | ConvertFrom-StringData
$Hash
```

```Output
Name     Value
----     -----
Msg3     The specified variable does not exist.
Msg2     Credentials are required for this command.
Msg1     The string parameter is required.
```

### <span data-ttu-id="3159e-143">Пример 6. использование escape-символов для добавления новых строк и возврата символов</span><span class="sxs-lookup"><span data-stu-id="3159e-143">Example 6: Use escape characters to add new lines and return characters</span></span>

<span data-ttu-id="3159e-144">В этом примере показано использование escape-символов для создания новых строк и возврата символов в исходные данные.</span><span class="sxs-lookup"><span data-stu-id="3159e-144">This example shows the use of escape characters to create new lines and return characters in source data.</span></span> <span data-ttu-id="3159e-145">Escape-последовательность `\n` используется для создания новых строк внутри блока текста, связанного с именем или элементом в результирующей хэш-таблице.</span><span class="sxs-lookup"><span data-stu-id="3159e-145">The escape sequence `\n` is used to create new lines within a block of text that is associated with a name or item in the resulting hash table.</span></span>

```powershell
ConvertFrom-StringData @"
Vincentio = Heaven doth with us as we with torches do,\nNot light them for themselves; for if our virtues\nDid not go forth of us, 'twere all alike\nAs if we had them not.
Angelo = Let there be some more test made of my metal,\nBefore so noble and so great a figure\nBe stamp'd upon it.
"@ | Format-List
```

```Output
Name  : Angelo
Value : Let there be some more test made of my metal,
        Before so noble and so great a figure
        Be stamp'd upon it.

Name  : Vincentio
Value : Heaven doth with us as we with torches do,
        Not light them for themselves; for if our virtues
        Did not go forth of us, 'twere all alike
        As if we had them not.
```

### <span data-ttu-id="3159e-146">Пример 7. использование escape-символа обратной косой черты для правильного отображения пути к файлу</span><span class="sxs-lookup"><span data-stu-id="3159e-146">Example 7: Use backslash escape character to correctly render a file path</span></span>

<span data-ttu-id="3159e-147">В этом примере показано, как использовать escape-символ обратной косой черты в строковых данных, чтобы обеспечить правильное отображение пути к файлу в результирующей `ConvertFrom-StringData` хэш таблице.</span><span class="sxs-lookup"><span data-stu-id="3159e-147">This example shows how to use of the backslash escape character in the string data to allow a file path to render correctly in the resulting `ConvertFrom-StringData` hash table.</span></span> <span data-ttu-id="3159e-148">С помощью двойной обратной косой черты гарантируется правильное представление символов обратной косой черты в выходных данных хэш-таблицы.</span><span class="sxs-lookup"><span data-stu-id="3159e-148">The double backslash ensures that the literal backslash characters render correctly in the hash table output.</span></span>

```powershell
ConvertFrom-StringData "Message=Look in c:\\Windows\\System32"
```

```Output
Name                           Value
----                           -----
Message                        Look in c:\Windows\System32
```

## <span data-ttu-id="3159e-149">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3159e-149">PARAMETERS</span></span>

### <span data-ttu-id="3159e-150">-StringData</span><span class="sxs-lookup"><span data-stu-id="3159e-150">-StringData</span></span>

<span data-ttu-id="3159e-151">Указывает строку, которую нужно преобразовать.</span><span class="sxs-lookup"><span data-stu-id="3159e-151">Specifies the string to be converted.</span></span> <span data-ttu-id="3159e-152">Можно использовать этот параметр или передать строку в `ConvertFrom-StringData` .</span><span class="sxs-lookup"><span data-stu-id="3159e-152">You can use this parameter or pipe a string to `ConvertFrom-StringData`.</span></span> <span data-ttu-id="3159e-153">Имя параметра является необязательным.</span><span class="sxs-lookup"><span data-stu-id="3159e-153">The parameter name is optional.</span></span>

<span data-ttu-id="3159e-154">Значение этого параметра должно быть строкой, содержащей одну или несколько пар "ключ-значение".</span><span class="sxs-lookup"><span data-stu-id="3159e-154">The value of this parameter must be a string that contains one or more key-value pairs.</span></span> <span data-ttu-id="3159e-155">Каждая пара "ключ-значение" должна находиться в отдельной строке, или каждая пара должна быть разделена символами новой строки ( \` n).</span><span class="sxs-lookup"><span data-stu-id="3159e-155">Each key-value pair must be on a separate line, or each pair must be separated by newline characters (\`n).</span></span>

<span data-ttu-id="3159e-156">В строку можно включить комментарии, но комментарии не могут находиться в той же строке, что и пара "ключ-значение".</span><span class="sxs-lookup"><span data-stu-id="3159e-156">You can include comments in the string, but the comments cannot be on the same line as a key-value pair.</span></span> <span data-ttu-id="3159e-157">`ConvertFrom-StringData` игнорирует однострочные комментарии.</span><span class="sxs-lookup"><span data-stu-id="3159e-157">`ConvertFrom-StringData` ignores single-line comments.</span></span> <span data-ttu-id="3159e-158">`#`Символ должен быть первым символом, отличным от пробела, в строке.</span><span class="sxs-lookup"><span data-stu-id="3159e-158">The `#` character must be the first non-whitespace character on the line.</span></span> <span data-ttu-id="3159e-159">Все символы в строке после символов `#` игнорируются.</span><span class="sxs-lookup"><span data-stu-id="3159e-159">All characters on the line after the `#` are ignored.</span></span> <span data-ttu-id="3159e-160">Комментарии не включаются в хэш-таблицу.</span><span class="sxs-lookup"><span data-stu-id="3159e-160">The comments are not included in the hash table.</span></span>

<span data-ttu-id="3159e-161">Строка Here — это строка, состоящая из одной или нескольких строк.</span><span class="sxs-lookup"><span data-stu-id="3159e-161">A here-string is a string consisting of one or more lines.</span></span> <span data-ttu-id="3159e-162">Кавычки в текстовой строке обрабатываются буквально как часть строковых данных.</span><span class="sxs-lookup"><span data-stu-id="3159e-162">Quotation marks within the here-string are interpreted literally as part of the string data.</span></span> <span data-ttu-id="3159e-163">Дополнительные сведения см. в разделе [about_Quoting_Rules](../Microsoft.PowerShell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="3159e-163">For more information, see [about_Quoting_Rules](../Microsoft.PowerShell.Core/About/about_Quoting_Rules.md).</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="3159e-164">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="3159e-164">CommonParameters</span></span>

<span data-ttu-id="3159e-165">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="3159e-165">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="3159e-166">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="3159e-166">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="3159e-167">Входные данные</span><span class="sxs-lookup"><span data-stu-id="3159e-167">INPUTS</span></span>

### <span data-ttu-id="3159e-168">System.String</span><span class="sxs-lookup"><span data-stu-id="3159e-168">System.String</span></span>

<span data-ttu-id="3159e-169">Строку, содержащую пару "ключ-значение", можно передать в `ConvertFrom-StringData` .</span><span class="sxs-lookup"><span data-stu-id="3159e-169">You can pipe a string containing a key-value pair to `ConvertFrom-StringData`.</span></span>

## <span data-ttu-id="3159e-170">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="3159e-170">OUTPUTS</span></span>

### <span data-ttu-id="3159e-171">System.Collections.Hashtable</span><span class="sxs-lookup"><span data-stu-id="3159e-171">System.Collections.Hashtable</span></span>

<span data-ttu-id="3159e-172">Этот командлет возвращает хэш-таблицу, которая создается из пар "ключ-значение".</span><span class="sxs-lookup"><span data-stu-id="3159e-172">This cmdlet returns a hash table that it creates from the key-value pairs.</span></span>

## <span data-ttu-id="3159e-173">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="3159e-173">NOTES</span></span>

<span data-ttu-id="3159e-174">Строка here — это строка, содержащая одну или несколько строк с кавычками, которые интерпретируются буквально.</span><span class="sxs-lookup"><span data-stu-id="3159e-174">A here-string is a string consisting of one or more lines within which quotation marks are interpreted literally.</span></span>

<span data-ttu-id="3159e-175">Этот командлет может быть полезен в сценариях, отображающих пользовательские сообщения на нескольких языках.</span><span class="sxs-lookup"><span data-stu-id="3159e-175">This cmdlet can be useful in scripts that display user messages in multiple spoken languages.</span></span> <span data-ttu-id="3159e-176">Хэш-таблицы, напоминающие словари, позволяют изолировать текстовые строки от кода, например в файлах ресурсов, и форматировать текстовые строки для использования в средствах перевода.</span><span class="sxs-lookup"><span data-stu-id="3159e-176">You can use the dictionary-style hash tables to isolate text strings from code, such as in resource files, and to format the text strings for use in translation tools.</span></span>

## <span data-ttu-id="3159e-177">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="3159e-177">RELATED LINKS</span></span>