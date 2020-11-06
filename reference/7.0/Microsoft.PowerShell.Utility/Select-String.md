---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/22/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/select-string?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Select-String
ms.openlocfilehash: 7c614314eb13ea484f5a0a5ade36aabdd6afdf58
ms.sourcegitcommit: 9a8bb1b459b5939c95e1f6d9499fcb13d01a58c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "93230482"
---
# <span data-ttu-id="1ae22-103">Select-String</span><span class="sxs-lookup"><span data-stu-id="1ae22-103">Select-String</span></span>

## <span data-ttu-id="1ae22-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="1ae22-104">SYNOPSIS</span></span>
<span data-ttu-id="1ae22-105">Выполняет поиск текста в строках и файлах.</span><span class="sxs-lookup"><span data-stu-id="1ae22-105">Finds text in strings and files.</span></span>

## <span data-ttu-id="1ae22-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1ae22-106">SYNTAX</span></span>

### <span data-ttu-id="1ae22-107">Файл (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="1ae22-107">File (Default)</span></span>

```
Select-String [-Culture <String>] [-Pattern] <String[]> [-Path] <String[]> [-SimpleMatch]
 [-CaseSensitive] [-Quiet] [-List] [-NoEmphasis] [-Include <String[]>] [-Exclude <String[]>]
 [-NotMatch] [-AllMatches] [-Encoding <Encoding>] [-Context <Int32[]>] [<CommonParameters>]
```

### <span data-ttu-id="1ae22-108">обжектрав</span><span class="sxs-lookup"><span data-stu-id="1ae22-108">ObjectRaw</span></span>

```
Select-String [-Culture <String>] -InputObject <PSObject> [-Pattern] <String[]> -Raw [-SimpleMatch]
 [-CaseSensitive] [-List] [-NoEmphasis] [-Include <String[]>] [-Exclude <String[]>] [-NotMatch]
 [-AllMatches] [-Encoding <Encoding>] [-Context <Int32[]>] [<CommonParameters>]
```

### <span data-ttu-id="1ae22-109">Объект</span><span class="sxs-lookup"><span data-stu-id="1ae22-109">Object</span></span>

```
Select-String [-Culture <String>] -InputObject <PSObject> [-Pattern] <String[]> [-SimpleMatch]
 [-CaseSensitive] [-Quiet] [-List] [-NoEmphasis] [-Include <String[]>] [-Exclude <String[]>]
 [-NotMatch] [-AllMatches] [-Encoding <Encoding>] [-Context <Int32[]>] [<CommonParameters>]
```

### <span data-ttu-id="1ae22-110">филерав</span><span class="sxs-lookup"><span data-stu-id="1ae22-110">FileRaw</span></span>

```
Select-String [-Culture <String>] [-Pattern] <String[]> [-Path] <String[]> -Raw [-SimpleMatch]
 [-CaseSensitive] [-List] [-NoEmphasis] [-Include <String[]>] [-Exclude <String[]>] [-NotMatch]
 [-AllMatches] [-Encoding <Encoding>] [-Context <Int32[]>] [<CommonParameters>]
```

### <span data-ttu-id="1ae22-111">литералфилерав</span><span class="sxs-lookup"><span data-stu-id="1ae22-111">LiteralFileRaw</span></span>

```
Select-String [-Culture <String>] [-Pattern] <String[]> -LiteralPath <String[]> -Raw [-SimpleMatch]
 [-CaseSensitive] [-List] [-NoEmphasis] [-Include <String[]>] [-Exclude <String[]>] [-NotMatch]
 [-AllMatches] [-Encoding <Encoding>] [-Context <Int32[]>] [<CommonParameters>]
```

### <span data-ttu-id="1ae22-112">литералфиле</span><span class="sxs-lookup"><span data-stu-id="1ae22-112">LiteralFile</span></span>

```
Select-String [-Culture <String>] [-Pattern] <String[]> -LiteralPath <String[]> [-SimpleMatch]
 [-CaseSensitive] [-Quiet] [-List] [-NoEmphasis] [-Include <String[]>] [-Exclude <String[]>]
 [-NotMatch] [-AllMatches] [-Encoding <Encoding>] [-Context <Int32[]>] [<CommonParameters>]
```

## <span data-ttu-id="1ae22-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1ae22-113">DESCRIPTION</span></span>

<span data-ttu-id="1ae22-114">`Select-String`Командлет выполняет поиск текстовых и текстовых шаблонов во входных строках и файлах.</span><span class="sxs-lookup"><span data-stu-id="1ae22-114">The `Select-String` cmdlet searches for text and text patterns in input strings and files.</span></span> <span data-ttu-id="1ae22-115">Вы можете использовать `Select-String` аналогичные возможности **grep** в UNIX или **findstr.exe** в Windows.</span><span class="sxs-lookup"><span data-stu-id="1ae22-115">You can use `Select-String` similar to **grep** in UNIX or **findstr.exe** in Windows.</span></span>

<span data-ttu-id="1ae22-116">`Select-String` основано на строках текста.</span><span class="sxs-lookup"><span data-stu-id="1ae22-116">`Select-String` is based on lines of text.</span></span> <span data-ttu-id="1ae22-117">По умолчанию `Select-String` находит первое совпадение в каждой строке и для каждого совпадения отображает имя файла, номер строки и весь текст в строке, содержащей совпадение.</span><span class="sxs-lookup"><span data-stu-id="1ae22-117">By default, `Select-String` finds the first match in each line and, for each match, it displays the file name, line number, and all text in the line containing the match.</span></span> <span data-ttu-id="1ae22-118">Можно направить `Select-String` Поиск нескольких совпадений в строке, отображаемый текст до и после соответствия или отобразить логическое значение (true или false), указывающее, найдено ли совпадение.</span><span class="sxs-lookup"><span data-stu-id="1ae22-118">You can direct `Select-String` to find multiple matches per line, display text before and after the match, or display a Boolean value (True or False) that indicates whether a match is found.</span></span>

<span data-ttu-id="1ae22-119">`Select-String` использует сопоставление регулярных выражений, но может также выполнять поиск, который ищет указанный текст в входных данных.</span><span class="sxs-lookup"><span data-stu-id="1ae22-119">`Select-String` uses regular expression matching, but it can also perform a match that searches the input for the text that you specify.</span></span>

<span data-ttu-id="1ae22-120">`Select-String` может отображать все текстовые совпадения или останавливаться после первого совпадения во входном файле.</span><span class="sxs-lookup"><span data-stu-id="1ae22-120">`Select-String` can display all the text matches or stop after the first match in each input file.</span></span>
<span data-ttu-id="1ae22-121">`Select-String` может использоваться для вывода всего текста, не соответствующего указанному шаблону.</span><span class="sxs-lookup"><span data-stu-id="1ae22-121">`Select-String` can be used to display all text that doesn't match the specified pattern.</span></span>

<span data-ttu-id="1ae22-122">Можно также указать, что `Select-String` должна рассчитывать определенную кодировку символов, например при поиске файлов в Юникоде.</span><span class="sxs-lookup"><span data-stu-id="1ae22-122">You can also specify that `Select-String` should expect a particular character encoding, such as when you're searching files of Unicode text.</span></span> <span data-ttu-id="1ae22-123">`Select-String` для определения формата кодирования файла использует символ-отметку (BOM).</span><span class="sxs-lookup"><span data-stu-id="1ae22-123">`Select-String` uses the byte-order-mark (BOM) to detect the encoding format of the file.</span></span> <span data-ttu-id="1ae22-124">Если файл не имеет BOM, предполагается, что используется кодировка UTF8.</span><span class="sxs-lookup"><span data-stu-id="1ae22-124">If the file has no BOM, it assumes the encoding is UTF8.</span></span>

## <span data-ttu-id="1ae22-125">Примеры</span><span class="sxs-lookup"><span data-stu-id="1ae22-125">EXAMPLES</span></span>

### <span data-ttu-id="1ae22-126">Пример 1. Поиск совпадения с учетом регистра</span><span class="sxs-lookup"><span data-stu-id="1ae22-126">Example 1: Find a case-sensitive match</span></span>

<span data-ttu-id="1ae22-127">В этом примере учитывается регистр текста, который был отправлен по конвейеру в `Select-String` командлет.</span><span class="sxs-lookup"><span data-stu-id="1ae22-127">This example does a case-sensitive match of the text that was sent down the pipeline to the `Select-String` cmdlet.</span></span>

```powershell
'Hello', 'HELLO' | Select-String -Pattern 'HELLO' -CaseSensitive -SimpleMatch
```

<span data-ttu-id="1ae22-128">Текстовые строки **Hello** и **Hello** отправляются в командлет по конвейеру `Select-String` .</span><span class="sxs-lookup"><span data-stu-id="1ae22-128">The text strings **Hello** and **HELLO** are sent down the pipeline to the `Select-String` cmdlet.</span></span>
<span data-ttu-id="1ae22-129">`Select-String` использует параметр **pattern** для указания **Hello** .</span><span class="sxs-lookup"><span data-stu-id="1ae22-129">`Select-String` uses the **Pattern** parameter to specify **HELLO** .</span></span> <span data-ttu-id="1ae22-130">Параметр **CaseSensitive** указывает, что Регистр должен совпадать только с шаблоном верхнего регистра.</span><span class="sxs-lookup"><span data-stu-id="1ae22-130">The **CaseSensitive** parameter specifies that the case must match only the upper-case pattern.</span></span> <span data-ttu-id="1ae22-131">**SimpleMatch** является необязательным параметром и указывает, что строка в шаблоне не интерпретируется как регулярное выражение.</span><span class="sxs-lookup"><span data-stu-id="1ae22-131">**SimpleMatch** is an optional parameter and specifies that the string in the pattern isn't interpreted as a regular expression.</span></span>
<span data-ttu-id="1ae22-132">`Select-String` Отображает **Hello** в консоли PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1ae22-132">`Select-String` displays **HELLO** in the PowerShell console.</span></span>

### <span data-ttu-id="1ae22-133">Пример 2. Поиск совпадений в текстовых файлах</span><span class="sxs-lookup"><span data-stu-id="1ae22-133">Example 2: Find matches in text files</span></span>

<span data-ttu-id="1ae22-134">Эта команда выполняет поиск `.txt` в текущем каталоге всех файлов с расширением имени файла.</span><span class="sxs-lookup"><span data-stu-id="1ae22-134">This command searches all files with the `.txt` file name extension in the current directory.</span></span> <span data-ttu-id="1ae22-135">В выходных данных отображаются строки в этих файлах, содержащие указанную строку.</span><span class="sxs-lookup"><span data-stu-id="1ae22-135">The output displays the lines in those files that include the specified string.</span></span>

```powershell
Get-Alias | Out-File -FilePath .\Alias.txt
Get-Command | Out-File -FilePath .\Command.txt
Select-String -Path .\*.txt -Pattern 'Get-'
```

```Output
Alias.txt:8:Alias            cat -> Get-Content
Alias.txt:28:Alias           dir -> Get-ChildItem
Alias.txt:43:Alias           gal -> Get-Alias
Command.txt:966:Cmdlet       Get-Acl
Command.txt:967:Cmdlet       Get-Alias
```

<span data-ttu-id="1ae22-136">В этом примере `Get-Alias` и `Get-Command` используются с `Out-File` командлетом для создания двух текстовых файлов в текущем каталоге, **Alias.txt** и **Command.txt** .</span><span class="sxs-lookup"><span data-stu-id="1ae22-136">In this example, `Get-Alias` and `Get-Command` are used with the `Out-File` cmdlet to create two text files in the current directory, **Alias.txt** and **Command.txt** .</span></span>

<span data-ttu-id="1ae22-137">`Select-String` использует параметр **path** с `*` подстановочным знаком звездочки () для поиска всех файлов в текущем каталоге с расширением имени файла `.txt` .</span><span class="sxs-lookup"><span data-stu-id="1ae22-137">`Select-String` uses the **Path** parameter with the asterisk (`*`) wildcard to search all files in the current directory with the file name extension `.txt`.</span></span> <span data-ttu-id="1ae22-138">Параметр **pattern** указывает текст, соответствующий **Get-** .</span><span class="sxs-lookup"><span data-stu-id="1ae22-138">The **Pattern** parameter specifies the text to match **Get-** .</span></span> <span data-ttu-id="1ae22-139">`Select-String` Отображает выходные данные в консоли PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1ae22-139">`Select-String` displays the output in the PowerShell console.</span></span> <span data-ttu-id="1ae22-140">Имя файла и номер строки предшествуют каждой строке содержимого, содержащей соответствие для параметра **pattern** .</span><span class="sxs-lookup"><span data-stu-id="1ae22-140">The file name and line number precede each line of content that contains a match for the **Pattern** parameter.</span></span>

### <span data-ttu-id="1ae22-141">Пример 3. Поиск соответствия шаблону</span><span class="sxs-lookup"><span data-stu-id="1ae22-141">Example 3: Find a pattern match</span></span>

<span data-ttu-id="1ae22-142">В этом примере выполняется поиск в нескольких файлах для поиска совпадений для указанного шаблона.</span><span class="sxs-lookup"><span data-stu-id="1ae22-142">In this example, multiple files are searched to find matches for the specified pattern.</span></span> <span data-ttu-id="1ae22-143">В шаблоне используется квантификатор регулярного выражения.</span><span class="sxs-lookup"><span data-stu-id="1ae22-143">The pattern uses a regular expression quantifier.</span></span> <span data-ttu-id="1ae22-144">Дополнительные сведения см. в разделе [about_Regular_Expressions](../Microsoft.PowerShell.Core/About/About_Regular_Expressions.md).</span><span class="sxs-lookup"><span data-stu-id="1ae22-144">For more information, see [about_Regular_Expressions](../Microsoft.PowerShell.Core/About/About_Regular_Expressions.md).</span></span>

```powershell
Select-String -Path "$PSHOME\en-US\*.txt" -Pattern '\?'
```

```Output
C:\Program Files\PowerShell\6\en-US\default.help.txt:27:    beginning at https://go.microsoft.com/fwlink/?LinkID=108518.
C:\Program Files\PowerShell\6\en-US\default.help.txt:50:    or go to: https://go.microsoft.com/fwlink/?LinkID=210614
```

<span data-ttu-id="1ae22-145">`Select-String`Командлет использует два параметра: **path** и **pattern** .</span><span class="sxs-lookup"><span data-stu-id="1ae22-145">The `Select-String` cmdlet uses two parameters, **Path** and **Pattern** .</span></span> <span data-ttu-id="1ae22-146">Параметр **path** использует переменную `$PSHOME` , которая указывает каталог PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1ae22-146">The **Path** parameter uses the variable `$PSHOME` that specifies the PowerShell directory.</span></span> <span data-ttu-id="1ae22-147">Оставшаяся часть пути включает подкаталог **en-US** и указывает каждый `*.txt` файл в каталоге.</span><span class="sxs-lookup"><span data-stu-id="1ae22-147">The remainder of the path includes the subdirectory **en-US** and specifies each `*.txt` file in the directory.</span></span> <span data-ttu-id="1ae22-148">Параметр **pattern** указывает, что соответствует вопросительному знаку ( `?` ) в каждом файле.</span><span class="sxs-lookup"><span data-stu-id="1ae22-148">The **Pattern** parameter specifies to match a question mark (`?`) in each file.</span></span> <span data-ttu-id="1ae22-149">Обратная косая черта ( `\` ) используется в качестве escape-символа и необходима, поскольку вопросительный знак ( `?` ) является квантификатором регулярного выражения.</span><span class="sxs-lookup"><span data-stu-id="1ae22-149">A backslash (`\`) is used as an escape character and is necessary because the question mark (`?`) is a regular expression quantifier.</span></span> <span data-ttu-id="1ae22-150">`Select-String` Отображает выходные данные в консоли PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1ae22-150">`Select-String` displays the output in the PowerShell console.</span></span> <span data-ttu-id="1ae22-151">Имя файла и номер строки предшествуют каждой строке содержимого, содержащей соответствие для параметра **pattern** .</span><span class="sxs-lookup"><span data-stu-id="1ae22-151">The file name and line number precede each line of content that contains a match for the **Pattern** parameter.</span></span>

### <span data-ttu-id="1ae22-152">Пример 4. Использование Select-String в функции</span><span class="sxs-lookup"><span data-stu-id="1ae22-152">Example 4: Use Select-String in a function</span></span>

<span data-ttu-id="1ae22-153">В этом примере создается функция для поиска шаблона в файлах справки PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1ae22-153">This example creates a function to search for a pattern in the PowerShell help files.</span></span> <span data-ttu-id="1ae22-154">В этом примере функция существует только в сеансе PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1ae22-154">For this example, the function only exists in the PowerShell session.</span></span> <span data-ttu-id="1ae22-155">При закрытии сеанса PowerShell функция удаляется.</span><span class="sxs-lookup"><span data-stu-id="1ae22-155">When the PowerShell session is closed, the function is deleted.</span></span> <span data-ttu-id="1ae22-156">Дополнительные сведения см. в разделе [about_Functions](../Microsoft.PowerShell.Core/About/about_Functions.md).</span><span class="sxs-lookup"><span data-stu-id="1ae22-156">For more information, see [about_Functions](../Microsoft.PowerShell.Core/About/about_Functions.md).</span></span>

```
PS> Function Search-Help
>> {
>> $PSHelp = "$PSHOME\en-US\*.txt"
>> Select-String -Path $PSHelp -Pattern 'About_'
>> }
PS>

PS> Search-Help

C:\Program Files\PowerShell\6\en-US\default.help.txt:67:    The titles of conceptual topics begin with "About_".
C:\Program Files\PowerShell\6\en-US\default.help.txt:70:    Get-Help About_<topic-name>
C:\Program Files\PowerShell\6\en-US\default.help.txt:93:    Get-Help About_Modules : Displays help about PowerShell modules.
C:\Program Files\PowerShell\6\en-US\default.help.txt:97:    about_Updatable_Help
```

<span data-ttu-id="1ae22-157">Функция создается в командной строке PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1ae22-157">The function is created on the PowerShell command line.</span></span> <span data-ttu-id="1ae22-158">`Function`Команда использует имя **поиска-Help** .</span><span class="sxs-lookup"><span data-stu-id="1ae22-158">The `Function` command uses the name **Search-Help** .</span></span> <span data-ttu-id="1ae22-159">Нажмите клавишу **Ввод** , чтобы начать Добавление операторов в функцию.</span><span class="sxs-lookup"><span data-stu-id="1ae22-159">Press **Enter** to begin adding statements to the function.</span></span> <span data-ttu-id="1ae22-160">В `>>` командной строке добавьте каждую инструкцию и нажмите клавишу **Ввод** , как показано в примере.</span><span class="sxs-lookup"><span data-stu-id="1ae22-160">From the `>>` prompt, add each statement and press **Enter** as shown in the example.</span></span> <span data-ttu-id="1ae22-161">После добавления закрывающей скобки вы вернетесь в командную строку PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1ae22-161">After the closing bracket is added, you're returned to a PowerShell prompt.</span></span>

<span data-ttu-id="1ae22-162">Функция содержит две команды.</span><span class="sxs-lookup"><span data-stu-id="1ae22-162">The function contains two commands.</span></span> <span data-ttu-id="1ae22-163">`$PSHelp`Переменная хранит путь к файлам справки PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1ae22-163">The `$PSHelp` variable stores the path to the PowerShell help files.</span></span> <span data-ttu-id="1ae22-164">`$PSHOME` — это каталог установки PowerShell с подкаталогом **en-US** , который указывает каждый `*.txt` файл в каталоге.</span><span class="sxs-lookup"><span data-stu-id="1ae22-164">`$PSHOME` is the PowerShell installation directory with the subdirectory **en-US** that specifies each `*.txt` file in the directory.</span></span>

<span data-ttu-id="1ae22-165">`Select-String`Команда в функции использует **путь** и параметры **шаблона** .</span><span class="sxs-lookup"><span data-stu-id="1ae22-165">The `Select-String` command in the function uses the **Path** and **Pattern** parameters.</span></span> <span data-ttu-id="1ae22-166">Параметр **path** использует `$PSHelp` переменную для получения пути.</span><span class="sxs-lookup"><span data-stu-id="1ae22-166">The **Path** parameter uses the `$PSHelp` variable to get the path.</span></span> <span data-ttu-id="1ae22-167">Параметр **pattern** использует строку **about_** в качестве условия поиска.</span><span class="sxs-lookup"><span data-stu-id="1ae22-167">The **Pattern** parameter uses the string **About_** as the search criteria.</span></span>

<span data-ttu-id="1ae22-168">Чтобы запустить функцию, введите `Search-Help` .</span><span class="sxs-lookup"><span data-stu-id="1ae22-168">To run the function, type `Search-Help`.</span></span> <span data-ttu-id="1ae22-169">`Select-String`Команда функции отображает выходные данные в консоли PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1ae22-169">The function's `Select-String` command displays the output in the PowerShell console.</span></span>

### <span data-ttu-id="1ae22-170">Пример 5. Поиск строки в журнале событий Windows</span><span class="sxs-lookup"><span data-stu-id="1ae22-170">Example 5: Search for a string in a Windows event log</span></span>

<span data-ttu-id="1ae22-171">В этом примере выполняется поиск строки в журнале событий Windows.</span><span class="sxs-lookup"><span data-stu-id="1ae22-171">This example searches for a string in a Windows event log.</span></span> <span data-ttu-id="1ae22-172">Переменная `$_` представляет текущий объект в конвейере.</span><span class="sxs-lookup"><span data-stu-id="1ae22-172">The variable `$_` represents the current object in the pipeline.</span></span> <span data-ttu-id="1ae22-173">Дополнительные сведения см. в разделе [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="1ae22-173">For more information, see [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).</span></span>

```powershell
$Events = Get-WinEvent -LogName Application -MaxEvents 50
$Events | Select-String -InputObject {$_.message} -Pattern 'Failed'
```

<span data-ttu-id="1ae22-174">`Get-WinEvent`Командлет использует параметр " **/l** " для указания журнала приложения.</span><span class="sxs-lookup"><span data-stu-id="1ae22-174">The `Get-WinEvent` cmdlet uses the **LogName** parameter to specify the Application log.</span></span> <span data-ttu-id="1ae22-175">Параметр **MaxEvents** возвращает 50 последних событий из журнала.</span><span class="sxs-lookup"><span data-stu-id="1ae22-175">The **MaxEvents** parameter gets the 50 most recent events from the log.</span></span> <span data-ttu-id="1ae22-176">Содержимое журнала хранится в переменной с именем `$Events` .</span><span class="sxs-lookup"><span data-stu-id="1ae22-176">The log content is stored in the variable named `$Events`.</span></span>

<span data-ttu-id="1ae22-177">`$Events`Переменная отправляется в командлет по конвейеру `Select-String` .</span><span class="sxs-lookup"><span data-stu-id="1ae22-177">The `$Events` variable is sent down the pipeline to the `Select-String` cmdlet.</span></span> <span data-ttu-id="1ae22-178">`Select-String` использует параметр **InputObject** .</span><span class="sxs-lookup"><span data-stu-id="1ae22-178">`Select-String` uses the **InputObject** parameter.</span></span> <span data-ttu-id="1ae22-179">`$_`Переменная представляет текущий объект и `message` является свойством события.</span><span class="sxs-lookup"><span data-stu-id="1ae22-179">The `$_` variable represents the current object and `message` is a property of the event.</span></span> <span data-ttu-id="1ae22-180">**Сбой** параметра **шаблона** , виды цветов строку, и поиск совпадений в `$_.message` .</span><span class="sxs-lookup"><span data-stu-id="1ae22-180">The **Pattern** parameter species the string **Failed** and searches for matches in `$_.message`.</span></span> <span data-ttu-id="1ae22-181">`Select-String` Отображает выходные данные в консоли PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1ae22-181">`Select-String` displays the output in the PowerShell console.</span></span>

### <span data-ttu-id="1ae22-182">Пример 6. Поиск строки в подкаталогах</span><span class="sxs-lookup"><span data-stu-id="1ae22-182">Example 6: Find a string in subdirectories</span></span>

<span data-ttu-id="1ae22-183">В этом примере выполняется поиск заданной текстовой строки в каталоге и всех его подкаталогах.</span><span class="sxs-lookup"><span data-stu-id="1ae22-183">This example searches a directory and all of its subdirectories for a specific text string.</span></span>

```powershell
Get-ChildItem -Path C:\Windows\System32\*.txt -Recurse | Select-String -Pattern 'Microsoft' -CaseSensitive
```

<span data-ttu-id="1ae22-184">`Get-ChildItem` использует параметр **path** для указания **C:\Windows\System32 \* . txt** .</span><span class="sxs-lookup"><span data-stu-id="1ae22-184">`Get-ChildItem` uses the **Path** parameter to specify **C:\Windows\System32\*.txt** .</span></span> <span data-ttu-id="1ae22-185">**Рекурсивный** параметр включает подкаталоги.</span><span class="sxs-lookup"><span data-stu-id="1ae22-185">The **Recurse** parameter includes the subdirectories.</span></span> <span data-ttu-id="1ae22-186">Объекты отправляются по конвейеру в `Select-String` .</span><span class="sxs-lookup"><span data-stu-id="1ae22-186">The objects are sent down the pipeline to `Select-String`.</span></span>

<span data-ttu-id="1ae22-187">`Select-String` использует параметр **шаблона** и указывает строку **Microsoft** .</span><span class="sxs-lookup"><span data-stu-id="1ae22-187">`Select-String` uses the **Pattern** parameter and specifies the string **Microsoft** .</span></span> <span data-ttu-id="1ae22-188">Параметр **CaseSensitive** используется для сопоставления с точным регистром строки.</span><span class="sxs-lookup"><span data-stu-id="1ae22-188">The **CaseSensitive** parameter is used to match the exact case of the string.</span></span> <span data-ttu-id="1ae22-189">`Select-String` Отображает выходные данные в консоли PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1ae22-189">`Select-String` displays the output in the PowerShell console.</span></span>

> [!NOTE]
> <span data-ttu-id="1ae22-190">В зависимости от ваших разрешений в выходных данных может отображаться сообщение об **отказе в доступе** .</span><span class="sxs-lookup"><span data-stu-id="1ae22-190">Dependent upon your permissions, you might see **Access denied** messages in the output.</span></span>

### <span data-ttu-id="1ae22-191">Пример 7. Поиск строк, не соответствующих шаблону</span><span class="sxs-lookup"><span data-stu-id="1ae22-191">Example 7: Find strings that do not match a pattern</span></span>

<span data-ttu-id="1ae22-192">В этом примере показано, как исключить строки данных, которые не соответствуют шаблону.</span><span class="sxs-lookup"><span data-stu-id="1ae22-192">This example shows how to exclude lines of data that don't match a pattern.</span></span>

```powershell
Get-Command | Out-File -FilePath .\Command.txt
Select-String -Path .\Command.txt -Pattern 'Get', 'Set'  -NotMatch
```

<span data-ttu-id="1ae22-193">`Get-Command`Командлет отправляет объекты по конвейеру в, `Out-File` чтобы создать файл **Command.txt** в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="1ae22-193">The `Get-Command` cmdlet sends objects down the pipeline to the `Out-File` to create the **Command.txt** file in the current directory.</span></span> <span data-ttu-id="1ae22-194">`Select-String` использует параметр **path** для указания файла **Command.txt** .</span><span class="sxs-lookup"><span data-stu-id="1ae22-194">`Select-String` uses the **Path** parameter to specify the **Command.txt** file.</span></span> <span data-ttu-id="1ae22-195">Параметр **pattern** указывает **Get** и **Set** в качестве шаблона поиска.</span><span class="sxs-lookup"><span data-stu-id="1ae22-195">The **Pattern** parameter specifies **Get** and **Set** as the search pattern.</span></span> <span data-ttu-id="1ae22-196">Параметр **NotMatch** исключает **Get** и **Set** из результатов.</span><span class="sxs-lookup"><span data-stu-id="1ae22-196">The **NotMatch** parameter excludes **Get** and **Set** from the results.</span></span>
<span data-ttu-id="1ae22-197">`Select-String` Отображает выходные данные в консоли PowerShell, которые не включают **Get** или **Set** .</span><span class="sxs-lookup"><span data-stu-id="1ae22-197">`Select-String` displays the output in the PowerShell console that doesn't include **Get** or **Set** .</span></span>

### <span data-ttu-id="1ae22-198">Пример 8. Поиск строк до и после совпадения</span><span class="sxs-lookup"><span data-stu-id="1ae22-198">Example 8: Find lines before and after a match</span></span>

<span data-ttu-id="1ae22-199">В этом примере показано, как получить строки до и после совпадающего шаблона.</span><span class="sxs-lookup"><span data-stu-id="1ae22-199">This example shows how to get the lines before and after the matched pattern.</span></span>

```powershell
Get-Command | Out-File -FilePath .\Command.txt
Select-String -Path .\Command.txt -Pattern 'Get-Computer' -Context 2, 3
```

```Output
  Command.txt:986:Cmdlet          Get-CmsMessage           6.1.0.0    Microsoft.PowerShell.Security
  Command.txt:987:Cmdlet          Get-Command              6.1.2.0    Microsoft.PowerShell.Core
> Command.txt:988:Cmdlet          Get-ComputerInfo         6.1.0.0    Microsoft.PowerShell.Management
  Command.txt:990:Cmdlet          Get-Content              6.1.0.0    Microsoft.PowerShell.Management
  Command.txt:991:Cmdlet          Get-ControlPanelItem     3.1.0.0    Microsoft.PowerShell.Management
  Command.txt:992:Cmdlet          Get-Credential           6.1.0.0    Microsoft.PowerShell.Security
```

<span data-ttu-id="1ae22-200">`Get-Command`Командлет отправляет объекты по конвейеру в, `Out-File` чтобы создать файл **Command.txt** в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="1ae22-200">The `Get-Command` cmdlet sends objects down the pipeline to the `Out-File` to create the **Command.txt** file in the current directory.</span></span> <span data-ttu-id="1ae22-201">`Select-String` использует параметр **path** для указания файла **Command.txt** .</span><span class="sxs-lookup"><span data-stu-id="1ae22-201">`Select-String` uses the **Path** parameter to specify the **Command.txt** file.</span></span> <span data-ttu-id="1ae22-202">Параметр **pattern** указывает в качестве шаблона поиска командлет **Get-Computer** .</span><span class="sxs-lookup"><span data-stu-id="1ae22-202">The **Pattern** parameter specifies **Get-Computer** as the search pattern.</span></span> <span data-ttu-id="1ae22-203">Параметр **context** использует два значения, before и After, и помечает совпадения шаблона в выходных данных с помощью угловой скобки ( `>` ).</span><span class="sxs-lookup"><span data-stu-id="1ae22-203">The **Context** parameter uses two values, before and after, and marks pattern matches in the output with an angle bracket (`>`).</span></span> <span data-ttu-id="1ae22-204">Параметр **context** выводит две строки перед первым совпадением шаблона и три строки после последнего совпадения шаблона.</span><span class="sxs-lookup"><span data-stu-id="1ae22-204">The **Context** parameter outputs the two lines before the first pattern match and three lines after the last pattern match.</span></span>

### <span data-ttu-id="1ae22-205">Пример 9. Поиск всех совпадений шаблонов</span><span class="sxs-lookup"><span data-stu-id="1ae22-205">Example 9: Find all pattern matches</span></span>

<span data-ttu-id="1ae22-206">В этом примере показано, как параметр **аллматчес** находит каждое совпадение шаблона в строке текста.</span><span class="sxs-lookup"><span data-stu-id="1ae22-206">This example shows how the **AllMatches** parameter finds each pattern match in a line of text.</span></span> <span data-ttu-id="1ae22-207">По умолчанию `Select-String` находит только первое вхождение шаблона в строке текста.</span><span class="sxs-lookup"><span data-stu-id="1ae22-207">By default, `Select-String` only finds the first occurrence of a pattern in a line of text.</span></span> <span data-ttu-id="1ae22-208">В этом примере используются свойства объекта, которые обнаруживаются с помощью `Get-Member` командлета.</span><span class="sxs-lookup"><span data-stu-id="1ae22-208">This example uses object properties that are found with the `Get-Member` cmdlet.</span></span>

```
PS> $A = Get-ChildItem -Path "$PSHOME\en-US\*.txt" | Select-String -Pattern 'PowerShell'

PS> $A

C:\Program Files\PowerShell\6\en-US\default.help.txt:3:    PowerShell Help System
C:\Program Files\PowerShell\6\en-US\default.help.txt:6:    Displays help about PowerShell cmdlets and concepts.
C:\Program Files\PowerShell\6\en-US\default.help.txt:9:    PowerShell Help describes PowerShell cmdlets

PS> $A.Matches

Groups   : {0}
Success  : True
Name     : 0
Captures : {0}
Index    : 4
Length   : 10
Value    : PowerShell

PS> $A.Matches.Length

8

PS> $B = Get-ChildItem -Path "$PSHOME\en-US\*.txt" | Select-String -Pattern 'PowerShell' -AllMatches

PS> $B.Matches.Length

9
```

<span data-ttu-id="1ae22-209">`Get-ChildItem`Командлет использует параметр **path** .</span><span class="sxs-lookup"><span data-stu-id="1ae22-209">The `Get-ChildItem` cmdlet uses the **Path** parameter.</span></span> <span data-ttu-id="1ae22-210">Параметр **path** использует переменную `$PSHOME` , которая указывает каталог PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1ae22-210">The **Path** parameter uses the variable `$PSHOME` that specifies the PowerShell directory.</span></span> <span data-ttu-id="1ae22-211">Оставшаяся часть пути включает подкаталог **en-US** и указывает каждый `*.txt` файл в каталоге.</span><span class="sxs-lookup"><span data-stu-id="1ae22-211">The remainder of the path includes the subdirectory **en-US** and specifies each `*.txt` file in the directory.</span></span> <span data-ttu-id="1ae22-212">`Get-ChildItem`Объекты хранятся в `$A` переменной.</span><span class="sxs-lookup"><span data-stu-id="1ae22-212">The `Get-ChildItem` objects are stored in the `$A` variable.</span></span> <span data-ttu-id="1ae22-213">`$A`Переменная отправляется в командлет по конвейеру `Select-String` .</span><span class="sxs-lookup"><span data-stu-id="1ae22-213">The `$A` variable is sent down the pipeline to the `Select-String` cmdlet.</span></span> <span data-ttu-id="1ae22-214">`Select-String` использует параметр **pattern** для поиска строки **PowerShell** в каждом файле.</span><span class="sxs-lookup"><span data-stu-id="1ae22-214">`Select-String` uses the **Pattern** parameter to search each file for the string **PowerShell** .</span></span>

<span data-ttu-id="1ae22-215">В командной строке PowerShell `$A` отобразится содержимое переменной.</span><span class="sxs-lookup"><span data-stu-id="1ae22-215">From the PowerShell command line, the `$A` variable contents are displayed.</span></span> <span data-ttu-id="1ae22-216">Существует строка, содержащая два вхождения строки **PowerShell** .</span><span class="sxs-lookup"><span data-stu-id="1ae22-216">There's a line that contains two occurrences of the string **PowerShell** .</span></span>

<span data-ttu-id="1ae22-217">`$A.Matches`Свойство перечисляет первое вхождение шаблона **PowerShell** в каждой строке.</span><span class="sxs-lookup"><span data-stu-id="1ae22-217">The `$A.Matches` property lists the first occurrence of the pattern **PowerShell** on each line.</span></span>

<span data-ttu-id="1ae22-218">`$A.Matches.Length`Свойство подсчитывает первое вхождение шаблона **PowerShell** в каждой строке.</span><span class="sxs-lookup"><span data-stu-id="1ae22-218">The `$A.Matches.Length` property counts the first occurrence of the pattern **PowerShell** on each line.</span></span>

<span data-ttu-id="1ae22-219">`$B`Переменная использует те же `Get-ChildItem` `Select-String` командлеты и, но добавляет параметр **аллматчес** .</span><span class="sxs-lookup"><span data-stu-id="1ae22-219">The `$B` variable uses the same `Get-ChildItem` and `Select-String` cmdlets, but adds the **AllMatches** parameter.</span></span> <span data-ttu-id="1ae22-220">**Аллматчес** находит каждое вхождение шаблона **PowerShell** в каждой строке.</span><span class="sxs-lookup"><span data-stu-id="1ae22-220">**AllMatches** finds each occurrence of the pattern **PowerShell** on each line.</span></span> <span data-ttu-id="1ae22-221">Объекты, хранящиеся в `$A` переменных и, `$B` идентичны.</span><span class="sxs-lookup"><span data-stu-id="1ae22-221">The objects stored in the `$A` and `$B` variables are identical.</span></span>

<span data-ttu-id="1ae22-222">`$B.Matches.Length`Свойство увеличивается, так как для каждой строки учитывается каждое вхождение шаблона **PowerShell** .</span><span class="sxs-lookup"><span data-stu-id="1ae22-222">The `$B.Matches.Length` property increases because for each line, every occurrence of the pattern **PowerShell** is counted.</span></span>

## <span data-ttu-id="1ae22-223">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1ae22-223">PARAMETERS</span></span>

### <span data-ttu-id="1ae22-224">-Аллматчес</span><span class="sxs-lookup"><span data-stu-id="1ae22-224">-AllMatches</span></span>

<span data-ttu-id="1ae22-225">Указывает, что командлет выполняет поиск нескольких совпадений в каждой строке текста.</span><span class="sxs-lookup"><span data-stu-id="1ae22-225">Indicates that the cmdlet searches for more than one match in each line of text.</span></span> <span data-ttu-id="1ae22-226">Без этого параметра `Select-String` находит только первое совпадение в каждой строке текста.</span><span class="sxs-lookup"><span data-stu-id="1ae22-226">Without this parameter, `Select-String` finds only the first match in each line of text.</span></span>

<span data-ttu-id="1ae22-227">При `Select-String` обнаружении нескольких совпадений в строке текста он по-прежнему создает в строке только один объект **MatchInfo** , но свойство Match объекта содержит **Matches** все совпадения.</span><span class="sxs-lookup"><span data-stu-id="1ae22-227">When `Select-String` finds more than one match in a line of text, it still emits only one **MatchInfo** object for the line, but the **Matches** property of the object contains all the matches.</span></span>

> [!NOTE]
> <span data-ttu-id="1ae22-228">Этот параметр игнорируется при использовании в сочетании с параметром **SimpleMatch** .</span><span class="sxs-lookup"><span data-stu-id="1ae22-228">This parameter is ignored when used in combination with the **SimpleMatch** parameter.</span></span> <span data-ttu-id="1ae22-229">Если вы хотите вернуть все совпадения, а искомый шаблон содержит символы регулярного выражения, необходимо отфильтровать эти символы, а не использовать **SimpleMatch** .</span><span class="sxs-lookup"><span data-stu-id="1ae22-229">If you wish to return all matches and the pattern that you are searching for contains regular expression characters, you must escape those characters rather than using **SimpleMatch** .</span></span> <span data-ttu-id="1ae22-230">Дополнительные сведения о экранировании регулярных выражений см. в разделе [about_Regular_Expressions](../Microsoft.PowerShell.Core/About/about_Regular_Expressions.md) .</span><span class="sxs-lookup"><span data-stu-id="1ae22-230">See [about_Regular_Expressions](../Microsoft.PowerShell.Core/About/about_Regular_Expressions.md) for more information about escaping regular expressions.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1ae22-231">-CaseSensitive</span><span class="sxs-lookup"><span data-stu-id="1ae22-231">-CaseSensitive</span></span>

<span data-ttu-id="1ae22-232">Указывает, что в совпадении командлета учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="1ae22-232">Indicates that the cmdlet matches are case-sensitive.</span></span> <span data-ttu-id="1ae22-233">По умолчанию в совпадениях не учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="1ae22-233">By default, matches aren't case-sensitive.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1ae22-234">-Context</span><span class="sxs-lookup"><span data-stu-id="1ae22-234">-Context</span></span>

<span data-ttu-id="1ae22-235">Захватывает указанное число строк до и после строки, соответствующей шаблону.</span><span class="sxs-lookup"><span data-stu-id="1ae22-235">Captures the specified number of lines before and after the line that matches the pattern.</span></span>

<span data-ttu-id="1ae22-236">Если в качестве значения этого параметра вы введете одно число, оно будет определять количество записываемых строк до и после совпадения.</span><span class="sxs-lookup"><span data-stu-id="1ae22-236">If you enter one number as the value of this parameter, that number determines the number of lines captured before and after the match.</span></span> <span data-ttu-id="1ae22-237">Если вы укажете два числа, первое из них будет определять количество строк до совпадения, а второе — после совпадения.</span><span class="sxs-lookup"><span data-stu-id="1ae22-237">If you enter two numbers as the value, the first number determines the number of lines before the match and the second number determines the number of lines after the match.</span></span> <span data-ttu-id="1ae22-238">Например, `-Context 2,3`.</span><span class="sxs-lookup"><span data-stu-id="1ae22-238">For example, `-Context 2,3`.</span></span>

<span data-ttu-id="1ae22-239">В отображении по умолчанию строки с совпадением обозначаются правой угловой скобкой ( `>` ) (ASCII 62) в первом столбце экрана.</span><span class="sxs-lookup"><span data-stu-id="1ae22-239">In the default display, lines with a match are indicated by a right angle bracket (`>`) (ASCII 62) in the first column of the display.</span></span> <span data-ttu-id="1ae22-240">Строки без пометок формируют контекст.</span><span class="sxs-lookup"><span data-stu-id="1ae22-240">Unmarked lines are the context.</span></span>

<span data-ttu-id="1ae22-241">Параметр **context** не изменяет число объектов, создаваемых `Select-String` .</span><span class="sxs-lookup"><span data-stu-id="1ae22-241">The **Context** parameter doesn't change the number of objects generated by `Select-String`.</span></span>
<span data-ttu-id="1ae22-242">`Select-String` создает один объект [MatchInfo](/dotnet/api/microsoft.powershell.commands.matchinfo) для каждого соответствия.</span><span class="sxs-lookup"><span data-stu-id="1ae22-242">`Select-String` generates one [MatchInfo](/dotnet/api/microsoft.powershell.commands.matchinfo) object for each match.</span></span> <span data-ttu-id="1ae22-243">Контекст хранится в виде массива строк в свойстве **context** объекта.</span><span class="sxs-lookup"><span data-stu-id="1ae22-243">The context is stored as an array of strings in the **Context** property of the object.</span></span>

<span data-ttu-id="1ae22-244">Когда выходные данные `Select-String` команды отправляются по конвейеру в другую `Select-String` команду, принимающая команда выполняет поиск только текста в соответствующей строке.</span><span class="sxs-lookup"><span data-stu-id="1ae22-244">When the output of a `Select-String` command is sent down the pipeline to another `Select-String` command, the receiving command searches only the text in the matched line.</span></span> <span data-ttu-id="1ae22-245">Совпадающая строка является значением свойства **line** объекта **MatchInfo** , а не текстом в строках контекста.</span><span class="sxs-lookup"><span data-stu-id="1ae22-245">The matched line is the value of the **Line** property of the **MatchInfo** object, not the text in the context lines.</span></span> <span data-ttu-id="1ae22-246">В результате параметр **контекста** не является допустимым для принимающей `Select-String` команды.</span><span class="sxs-lookup"><span data-stu-id="1ae22-246">As a result, the **Context** parameter isn't valid on the receiving `Select-String` command.</span></span>

<span data-ttu-id="1ae22-247">Когда контекст включает совпадение, объект **MatchInfo** для каждого соответствия включает все строки контекста, но перекрывающиеся линии отображаются только один раз на экране.</span><span class="sxs-lookup"><span data-stu-id="1ae22-247">When the context includes a match, the **MatchInfo** object for each match includes all the context lines, but the overlapping lines appear only once in the display.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1ae22-248">-Culture</span><span class="sxs-lookup"><span data-stu-id="1ae22-248">-Culture</span></span>

<span data-ttu-id="1ae22-249">Указывает имя языка и региональных параметров для соответствия заданному шаблону.</span><span class="sxs-lookup"><span data-stu-id="1ae22-249">Specifies a culture name to match the specified pattern.</span></span> <span data-ttu-id="1ae22-250">Параметр **culture** должен использоваться с параметром **SimpleMatch** .</span><span class="sxs-lookup"><span data-stu-id="1ae22-250">The **Culture** parameter must be used with the **SimpleMatch** parameter.</span></span> <span data-ttu-id="1ae22-251">Поведение по умолчанию использует язык и региональные параметры текущего пространства выполнения PowerShell (сеанса).</span><span class="sxs-lookup"><span data-stu-id="1ae22-251">The default behavior uses the culture of the current PowerShell runspace (session).</span></span>

<span data-ttu-id="1ae22-252">Чтобы получить список всех поддерживаемых культур, используйте `Get-Culture -ListAvailable` команду.</span><span class="sxs-lookup"><span data-stu-id="1ae22-252">To get a list of all supported cultures, use `Get-Culture -ListAvailable` command.</span></span>

<span data-ttu-id="1ae22-253">Кроме того, этот параметр принимает следующие аргументы:</span><span class="sxs-lookup"><span data-stu-id="1ae22-253">In addition, this parameter accepts the following arguments:</span></span>

- <span data-ttu-id="1ae22-254">CurrentCulture, то есть по умолчанию;</span><span class="sxs-lookup"><span data-stu-id="1ae22-254">CurrentCulture, that is default;</span></span>
- <span data-ttu-id="1ae22-255">Порядковый номер, который является нелингвистическим двоичным сравнением;</span><span class="sxs-lookup"><span data-stu-id="1ae22-255">Ordinal, that is non-linguistic binary comparison;</span></span>
- <span data-ttu-id="1ae22-256">Инвариант, который является независимым от языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="1ae22-256">Invariant, that is culture independent comparison.</span></span>

<span data-ttu-id="1ae22-257">Команда with обеспечивает `Select-String -Culture Ordinal -CaseSensitive -SimpleMatch` самое быстрое двоичное сравнение.</span><span class="sxs-lookup"><span data-stu-id="1ae22-257">With `Select-String -Culture Ordinal -CaseSensitive -SimpleMatch` command you gets fastest binary comparison.</span></span>

<span data-ttu-id="1ae22-258">Параметр **culture** использует заполнение по клавише TAB для прокрутки списка аргументов, задающих доступные языки и региональные параметры.</span><span class="sxs-lookup"><span data-stu-id="1ae22-258">The **Culture** parameter uses tab completion to scroll through the list of arguments that specify the available cultures.</span></span> <span data-ttu-id="1ae22-259">Чтобы получить список всех доступных аргументов, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="1ae22-259">To list all available arguments, use the following command:</span></span>

`(Get-Command Select-String).Parameters.Culture.Attributes.ValidValues`

<span data-ttu-id="1ae22-260">Дополнительные сведения о свойстве .NET CultureInfo.Name см. в разделе [CultureInfo.Name](/dotnet/api//system.globalization.cultureinfo.name).</span><span class="sxs-lookup"><span data-stu-id="1ae22-260">For more information about .NET CultureInfo.Name property, see [CultureInfo.Name](/dotnet/api//system.globalization.cultureinfo.name).</span></span>

<span data-ttu-id="1ae22-261">Параметр **culture** появился в PowerShell 7.</span><span class="sxs-lookup"><span data-stu-id="1ae22-261">The **Culture** parameter was introduced in PowerShell 7.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Culture of the current PowerShell session
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1ae22-262">-Encoding</span><span class="sxs-lookup"><span data-stu-id="1ae22-262">-Encoding</span></span>

<span data-ttu-id="1ae22-263">Указывает тип кодировки для целевого файла.</span><span class="sxs-lookup"><span data-stu-id="1ae22-263">Specifies the type of encoding for the target file.</span></span> <span data-ttu-id="1ae22-264">Значение по умолчанию — `utf8NoBOM`.</span><span class="sxs-lookup"><span data-stu-id="1ae22-264">The default value is `utf8NoBOM`.</span></span>

<span data-ttu-id="1ae22-265">Для этого параметра допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="1ae22-265">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="1ae22-266">`ascii`: Использует кодировку для набора символов ASCII (7-разрядных).</span><span class="sxs-lookup"><span data-stu-id="1ae22-266">`ascii`: Uses the encoding for the ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="1ae22-267">`bigendianunicode`: Кодируется в формате UTF-16 с обратным порядком байтов.</span><span class="sxs-lookup"><span data-stu-id="1ae22-267">`bigendianunicode`: Encodes in UTF-16 format using the big-endian byte order.</span></span>
- <span data-ttu-id="1ae22-268">`oem`: Использует кодировку по умолчанию для программ MS-DOS и консолей.</span><span class="sxs-lookup"><span data-stu-id="1ae22-268">`oem`: Uses the default encoding for MS-DOS and console programs.</span></span>
- <span data-ttu-id="1ae22-269">`unicode`: Кодируется в формате UTF-16 с прямым порядком байтов.</span><span class="sxs-lookup"><span data-stu-id="1ae22-269">`unicode`: Encodes in UTF-16 format using the little-endian byte order.</span></span>
- <span data-ttu-id="1ae22-270">`utf7`: Кодируется в формате UTF-7.</span><span class="sxs-lookup"><span data-stu-id="1ae22-270">`utf7`: Encodes in UTF-7 format.</span></span>
- <span data-ttu-id="1ae22-271">`utf8`: Кодируется в формате UTF-8.</span><span class="sxs-lookup"><span data-stu-id="1ae22-271">`utf8`: Encodes in UTF-8 format.</span></span>
- <span data-ttu-id="1ae22-272">`utf8BOM`: Кодирует в формате UTF-8 с меткой порядка байтов (BOM)</span><span class="sxs-lookup"><span data-stu-id="1ae22-272">`utf8BOM`: Encodes in UTF-8 format with Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="1ae22-273">`utf8NoBOM`: Кодирует в формате UTF-8 без метки порядка байтов (BOM)</span><span class="sxs-lookup"><span data-stu-id="1ae22-273">`utf8NoBOM`: Encodes in UTF-8 format without Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="1ae22-274">`utf32`: Кодируется в формате UTF-32.</span><span class="sxs-lookup"><span data-stu-id="1ae22-274">`utf32`: Encodes in UTF-32 format.</span></span>

<span data-ttu-id="1ae22-275">Начиная с PowerShell 6,2, параметр **кодировки** также разрешает числовые идентификаторы зарегистрированных кодовых страниц (например `-Encoding 1251` ,) или строковых имен зарегистрированных кодовых страниц (например `-Encoding "windows-1251"` ,).</span><span class="sxs-lookup"><span data-stu-id="1ae22-275">Beginning with PowerShell 6.2, the **Encoding** parameter also allows numeric IDs of registered code pages (like `-Encoding 1251`) or string names of registered code pages (like `-Encoding "windows-1251"`).</span></span> <span data-ttu-id="1ae22-276">Дополнительные сведения см. в документации .NET по [кодированию. codepage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span><span class="sxs-lookup"><span data-stu-id="1ae22-276">For more information, see the .NET documentation for [Encoding.CodePage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span></span>

```yaml
Type: System.Text.Encoding
Parameter Sets: (All)
Aliases:
Accepted values: ASCII, BigEndianUnicode, OEM, Unicode, UTF7, UTF8, UTF8BOM, UTF8NoBOM, UTF32

Required: False
Position: Named
Default value: UTF8NoBOM
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1ae22-277">-Exclude</span><span class="sxs-lookup"><span data-stu-id="1ae22-277">-Exclude</span></span>

<span data-ttu-id="1ae22-278">Исключает указанные элементы.</span><span class="sxs-lookup"><span data-stu-id="1ae22-278">Exclude the specified items.</span></span> <span data-ttu-id="1ae22-279">Значение этого параметра определяет параметр **Path** .</span><span class="sxs-lookup"><span data-stu-id="1ae22-279">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="1ae22-280">Введите элемент пути или шаблон, например `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="1ae22-280">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="1ae22-281">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="1ae22-281">Wildcards are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="1ae22-282">-Include</span><span class="sxs-lookup"><span data-stu-id="1ae22-282">-Include</span></span>

<span data-ttu-id="1ae22-283">Включает указанные элементы.</span><span class="sxs-lookup"><span data-stu-id="1ae22-283">Includes the specified items.</span></span> <span data-ttu-id="1ae22-284">Значение этого параметра определяет параметр **Path** .</span><span class="sxs-lookup"><span data-stu-id="1ae22-284">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="1ae22-285">Введите элемент пути или шаблон, например `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="1ae22-285">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="1ae22-286">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="1ae22-286">Wildcards are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="1ae22-287">-InputObject</span><span class="sxs-lookup"><span data-stu-id="1ae22-287">-InputObject</span></span>

<span data-ttu-id="1ae22-288">Задает текст для поиска.</span><span class="sxs-lookup"><span data-stu-id="1ae22-288">Specifies the text to be searched.</span></span> <span data-ttu-id="1ae22-289">Укажите переменную, содержащую текст, либо введите команду или выражение, которые его возвращают.</span><span class="sxs-lookup"><span data-stu-id="1ae22-289">Enter a variable that contains the text, or type a command or expression that gets the text.</span></span>

<span data-ttu-id="1ae22-290">Использование параметра **InputObject** не отличается от отправки строк вниз по конвейеру `Select-String` .</span><span class="sxs-lookup"><span data-stu-id="1ae22-290">Using the **InputObject** parameter isn't the same as sending strings down the pipeline to `Select-String`.</span></span>

<span data-ttu-id="1ae22-291">При передаче более одной строки в `Select-String` командлет он выполняет поиск указанного текста в каждой строке и возвращает каждую строку, содержащую искомый текст.</span><span class="sxs-lookup"><span data-stu-id="1ae22-291">When you pipe more than one string to the `Select-String` cmdlet, it searches for the specified text in each string and returns each string that contains the search text.</span></span>

<span data-ttu-id="1ae22-292">При использовании параметра **InputObject** для отправки коллекции строк `Select-String` обрабатывает коллекцию как единую объединенную строку.</span><span class="sxs-lookup"><span data-stu-id="1ae22-292">When you use the **InputObject** parameter to submit a collection of strings, `Select-String` treats the collection as a single combined string.</span></span> <span data-ttu-id="1ae22-293">`Select-String` Возвращает строки в виде единицы, если находит искомый текст в любой строке.</span><span class="sxs-lookup"><span data-stu-id="1ae22-293">`Select-String` returns the strings as a unit if it finds the search text in any string.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: ObjectRaw, Object
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="1ae22-294">-List</span><span class="sxs-lookup"><span data-stu-id="1ae22-294">-List</span></span>

<span data-ttu-id="1ae22-295">Из каждого входного файла возвращается только первый экземпляр соответствующего текста.</span><span class="sxs-lookup"><span data-stu-id="1ae22-295">Only the first instance of matching text is returned from each input file.</span></span> <span data-ttu-id="1ae22-296">Это наиболее эффективный способ получения списка файлов с содержимым, соответствующим регулярному выражению.</span><span class="sxs-lookup"><span data-stu-id="1ae22-296">This is the most efficient way to retrieve a list of files that have contents matching the regular expression.</span></span>

<span data-ttu-id="1ae22-297">По умолчанию `Select-String` возвращает объект **MatchInfo** для каждого найденного совпадения.</span><span class="sxs-lookup"><span data-stu-id="1ae22-297">By default, `Select-String` returns a **MatchInfo** object for each match it finds.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1ae22-298">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="1ae22-298">-LiteralPath</span></span>

<span data-ttu-id="1ae22-299">Указывает путь к файлам для поиска.</span><span class="sxs-lookup"><span data-stu-id="1ae22-299">Specifies the path to the files to be searched.</span></span> <span data-ttu-id="1ae22-300">Значение параметра **LiteralPath** используется точно так же, как тип.</span><span class="sxs-lookup"><span data-stu-id="1ae22-300">The value of the **LiteralPath** parameter is used exactly as it's typed.</span></span> <span data-ttu-id="1ae22-301">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="1ae22-301">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="1ae22-302">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="1ae22-302">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="1ae22-303">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="1ae22-303">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span> <span data-ttu-id="1ae22-304">Дополнительные сведения см. в разделе [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="1ae22-304">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralFileRaw, LiteralFile
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="1ae22-305">-Выделение</span><span class="sxs-lookup"><span data-stu-id="1ae22-305">-NoEmphasis</span></span>

<span data-ttu-id="1ae22-306">По умолчанию `Select-String` выделяется строка, соответствующая шаблону, который вы искали с помощью параметра **pattern** .</span><span class="sxs-lookup"><span data-stu-id="1ae22-306">By default, `Select-String` highlights the string that matches the pattern you searched for with the **Pattern** parameter.</span></span> <span data-ttu-id="1ae22-307">Параметр **выделения** отключает выделение.</span><span class="sxs-lookup"><span data-stu-id="1ae22-307">The **NoEmphasis** parameter disables the highlighting.</span></span>

<span data-ttu-id="1ae22-308">Выделение использует отрицательные цвета в зависимости от цветов фона и текста PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1ae22-308">The emphasis uses negative colors based on your PowerShell background and text colors.</span></span> <span data-ttu-id="1ae22-309">Например, если цвета PowerShell представляют собой черный фон с белым текстом.</span><span class="sxs-lookup"><span data-stu-id="1ae22-309">For example, if your PowerShell colors are a black background with white text.</span></span> <span data-ttu-id="1ae22-310">Выделение представляет собой белый фон с черным текстом.</span><span class="sxs-lookup"><span data-stu-id="1ae22-310">The emphasis is a white background with black text.</span></span>

<span data-ttu-id="1ae22-311">Этот параметр появился в PowerShell 7.</span><span class="sxs-lookup"><span data-stu-id="1ae22-311">This parameter was introduced in PowerShell 7.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1ae22-312">-NotMatch</span><span class="sxs-lookup"><span data-stu-id="1ae22-312">-NotMatch</span></span>

<span data-ttu-id="1ae22-313">Параметр **NotMatch** находит текст, который не соответствует указанному шаблону.</span><span class="sxs-lookup"><span data-stu-id="1ae22-313">The **NotMatch** parameter finds text that doesn't match the specified pattern.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1ae22-314">-Path</span><span class="sxs-lookup"><span data-stu-id="1ae22-314">-Path</span></span>

<span data-ttu-id="1ae22-315">Указывает путь к файлам для поиска.</span><span class="sxs-lookup"><span data-stu-id="1ae22-315">Specifies the path to the files to search.</span></span> <span data-ttu-id="1ae22-316">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="1ae22-316">Wildcards are permitted.</span></span> <span data-ttu-id="1ae22-317">По умолчанию поиск выполняется в локальном каталоге.</span><span class="sxs-lookup"><span data-stu-id="1ae22-317">The default location is the local directory.</span></span>

<span data-ttu-id="1ae22-318">Укажите файлы в каталоге, например `log1.txt` , `*.doc` или `*.*` .</span><span class="sxs-lookup"><span data-stu-id="1ae22-318">Specify files in the directory, such as `log1.txt`, `*.doc`, or `*.*`.</span></span> <span data-ttu-id="1ae22-319">Если вы укажете только один каталог, команда завершится сбоем.</span><span class="sxs-lookup"><span data-stu-id="1ae22-319">If you specify only a directory, the command fails.</span></span>

```yaml
Type: System.String[]
Parameter Sets: File, FileRaw
Aliases:

Required: True
Position: 1
Default value: Local directory
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="1ae22-320">-Pattern</span><span class="sxs-lookup"><span data-stu-id="1ae22-320">-Pattern</span></span>

<span data-ttu-id="1ae22-321">Задает текст для поиска в каждой строке.</span><span class="sxs-lookup"><span data-stu-id="1ae22-321">Specifies the text to find on each line.</span></span> <span data-ttu-id="1ae22-322">Значение шаблона рассматривается как регулярное выражение.</span><span class="sxs-lookup"><span data-stu-id="1ae22-322">The pattern value is treated as a regular expression.</span></span>

<span data-ttu-id="1ae22-323">Дополнительные сведения о регулярных выражениях см. в разделе [about_Regular_Expressions](../Microsoft.PowerShell.Core/About/about_Regular_Expressions.md).</span><span class="sxs-lookup"><span data-stu-id="1ae22-323">To learn about regular expressions, see [about_Regular_Expressions](../Microsoft.PowerShell.Core/About/about_Regular_Expressions.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1ae22-324">-Quiet</span><span class="sxs-lookup"><span data-stu-id="1ae22-324">-Quiet</span></span>

<span data-ttu-id="1ae22-325">Указывает, что командлет возвращает логическое значение (true или false) вместо объекта **MatchInfo** .</span><span class="sxs-lookup"><span data-stu-id="1ae22-325">Indicates that the cmdlet returns a Boolean value (True or False), instead of a **MatchInfo** object.</span></span> <span data-ttu-id="1ae22-326">Значение равно true, если шаблон найден. в противном случае значение равно false.</span><span class="sxs-lookup"><span data-stu-id="1ae22-326">The value is True if the pattern is found; otherwise the value is False.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: File, Object, LiteralFile
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1ae22-327">-RAW</span><span class="sxs-lookup"><span data-stu-id="1ae22-327">-Raw</span></span>

<span data-ttu-id="1ae22-328">Приводит к тому, что командлет выводит только совпадающие строки, а не объекты **MatchInfo** .</span><span class="sxs-lookup"><span data-stu-id="1ae22-328">Causes the cmdlet to output only the matching strings, rather than **MatchInfo** objects.</span></span> <span data-ttu-id="1ae22-329">Это приводит к поведению, наиболее похожему на команды Unix **grep** или Windows **findstr.exe** .</span><span class="sxs-lookup"><span data-stu-id="1ae22-329">This is the results in behavior that's the most similar to the Unix **grep** or Windows **findstr.exe** commands.</span></span>

<span data-ttu-id="1ae22-330">Этот параметр появился в PowerShell 7.</span><span class="sxs-lookup"><span data-stu-id="1ae22-330">This parameter was introduced in PowerShell 7.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ObjectRaw, FileRaw, LiteralFileRaw
Aliases:

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1ae22-331">-SimpleMatch</span><span class="sxs-lookup"><span data-stu-id="1ae22-331">-SimpleMatch</span></span>

<span data-ttu-id="1ae22-332">Указывает, что командлет использует простое соответствие, а не сопоставление регулярного выражения.</span><span class="sxs-lookup"><span data-stu-id="1ae22-332">Indicates that the cmdlet uses a simple match rather than a regular expression match.</span></span> <span data-ttu-id="1ae22-333">При простое совпадение `Select-String` выполняет поиск текста в параметре **pattern** .</span><span class="sxs-lookup"><span data-stu-id="1ae22-333">In a simple match, `Select-String` searches the input for the text in the **Pattern** parameter.</span></span> <span data-ttu-id="1ae22-334">Значение параметра **pattern** не интерпретируется как оператор регулярного выражения.</span><span class="sxs-lookup"><span data-stu-id="1ae22-334">It doesn't interpret the value of the **Pattern** parameter as a regular expression statement.</span></span>

<span data-ttu-id="1ae22-335">Кроме того, при использовании **SimpleMatch** свойство **Matches** возвращаемого объекта **MatchInfo** является пустым.</span><span class="sxs-lookup"><span data-stu-id="1ae22-335">Also, when **SimpleMatch** is used, the **Matches** property of the **MatchInfo** object returned is empty.</span></span>

> [!NOTE]
> <span data-ttu-id="1ae22-336">Если этот параметр используется с параметром **аллматчес** , **аллматчес** игнорируется.</span><span class="sxs-lookup"><span data-stu-id="1ae22-336">When this parameter is used with the **AllMatches** parameter, the **AllMatches** is ignored.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1ae22-337">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="1ae22-337">CommonParameters</span></span>

<span data-ttu-id="1ae22-338">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="1ae22-338">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="1ae22-339">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="1ae22-339">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="1ae22-340">Входные данные</span><span class="sxs-lookup"><span data-stu-id="1ae22-340">INPUTS</span></span>

### <span data-ttu-id="1ae22-341">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="1ae22-341">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="1ae22-342">Любой объект, имеющий метод **ToString** , можно передать в `Select-String` .</span><span class="sxs-lookup"><span data-stu-id="1ae22-342">You can pipe any object that has a **ToString** method to `Select-String`.</span></span>

## <span data-ttu-id="1ae22-343">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="1ae22-343">OUTPUTS</span></span>

### <span data-ttu-id="1ae22-344">Microsoft. PowerShell. Commands. MatchInfo, System. Boolean, System. String</span><span class="sxs-lookup"><span data-stu-id="1ae22-344">Microsoft.PowerShell.Commands.MatchInfo, System.Boolean, System.String</span></span>

<span data-ttu-id="1ae22-345">По умолчанию выходные данные представляют собой набор объектов **MatchInfo** с по одному для каждого найденного совпадения.</span><span class="sxs-lookup"><span data-stu-id="1ae22-345">By default, the output is a set of **MatchInfo** objects with one for each match found.</span></span> <span data-ttu-id="1ae22-346">Если используется параметр **quiet** , то выходным значением является **логическое** значение, указывающее, был ли найден шаблон.</span><span class="sxs-lookup"><span data-stu-id="1ae22-346">If you use the **Quiet** parameter, the output is a **Boolean** value indicating whether the pattern was found.</span></span>
<span data-ttu-id="1ae22-347">Если используется параметр **RAW** , выходные данные представляют собой набор **строковых** объектов, соответствующих шаблону.</span><span class="sxs-lookup"><span data-stu-id="1ae22-347">If you use the **Raw** parameter, the output is a set of **String** objects that match the pattern.</span></span>

## <span data-ttu-id="1ae22-348">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="1ae22-348">NOTES</span></span>

<span data-ttu-id="1ae22-349">`Select-String` аналогичен **grep** в UNIX или **findstr.exe** в Windows.</span><span class="sxs-lookup"><span data-stu-id="1ae22-349">`Select-String` is similar to **grep** in UNIX or **findstr.exe** in Windows.</span></span>

<span data-ttu-id="1ae22-350">Псевдоним **СЛС** для `Select-String` командлета появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="1ae22-350">The **sls** alias for the `Select-String` cmdlet was introduced in PowerShell 3.0.</span></span>

> [!NOTE]
> <span data-ttu-id="1ae22-351">В соответствии с [утвержденными командами для команд PowerShell](/powershell/scripting/developer/cmdlet/approved-verbs-for-windows-powershell-commands)официальный префикс псевдонима для `Select-*` командлетов — `sc` , а не `sl` .</span><span class="sxs-lookup"><span data-stu-id="1ae22-351">According to [Approved Verbs for PowerShell Commands](/powershell/scripting/developer/cmdlet/approved-verbs-for-windows-powershell-commands), the official alias prefix for `Select-*` cmdlets is `sc`, not `sl`.</span></span> <span data-ttu-id="1ae22-352">Таким образом, правильный псевдоним для `Select-String` должен иметь значение `scs` , а не `sls` .</span><span class="sxs-lookup"><span data-stu-id="1ae22-352">Therefore, the proper alias for `Select-String` should be `scs`, not `sls`.</span></span> <span data-ttu-id="1ae22-353">Это исключение из этого правила.</span><span class="sxs-lookup"><span data-stu-id="1ae22-353">This is an exception to this rule.</span></span>

<span data-ttu-id="1ae22-354">Чтобы использовать `Select-String` , введите текст, который требуется найти в качестве значения параметра **pattern** .</span><span class="sxs-lookup"><span data-stu-id="1ae22-354">To use `Select-String`, type the text that you want to find as the value of the **Pattern** parameter.</span></span> <span data-ttu-id="1ae22-355">Чтобы указать текст для поиска, используйте следующие критерии.</span><span class="sxs-lookup"><span data-stu-id="1ae22-355">To specify the text to be searched, use the following criteria:</span></span>

- <span data-ttu-id="1ae22-356">Введите текст в строке в кавычках и затем передайте его в `Select-String` .</span><span class="sxs-lookup"><span data-stu-id="1ae22-356">Type the text in a quoted string, and then pipe it to `Select-String`.</span></span>
- <span data-ttu-id="1ae22-357">Сохраните текстовую строку в переменной, а затем укажите переменную в качестве значения параметра **InputObject** .</span><span class="sxs-lookup"><span data-stu-id="1ae22-357">Store a text string in a variable, and then specify the variable as the value of the **InputObject** parameter.</span></span>
- <span data-ttu-id="1ae22-358">Если текст хранится в файлах, используйте параметр **path** , чтобы указать путь к файлам.</span><span class="sxs-lookup"><span data-stu-id="1ae22-358">If the text is stored in files, use the **Path** parameter to specify the path to the files.</span></span>

<span data-ttu-id="1ae22-359">По умолчанию `Select-String` интерпретирует значение параметра **шаблона** как регулярное выражение.</span><span class="sxs-lookup"><span data-stu-id="1ae22-359">By default, `Select-String` interprets the value of the **Pattern** parameter as a regular expression.</span></span> <span data-ttu-id="1ae22-360">Дополнительные сведения см. в разделе [about_Regular_Expressions](../Microsoft.PowerShell.Core/About/about_Regular_Expressions.md).</span><span class="sxs-lookup"><span data-stu-id="1ae22-360">For more information, see [about_Regular_Expressions](../Microsoft.PowerShell.Core/About/about_Regular_Expressions.md).</span></span> <span data-ttu-id="1ae22-361">Для переопределения сопоставления регулярного выражения можно использовать параметр **SimpleMatch** .</span><span class="sxs-lookup"><span data-stu-id="1ae22-361">You can use the **SimpleMatch** parameter to override the regular expression matching.</span></span> <span data-ttu-id="1ae22-362">Параметр **SimpleMatch** находит экземпляры значения параметра **pattern** во входных данных.</span><span class="sxs-lookup"><span data-stu-id="1ae22-362">The **SimpleMatch** parameter finds instances of the value of the **Pattern** parameter in the input.</span></span>

<span data-ttu-id="1ae22-363">Выходом по умолчанию `Select-String` является объект **MatchInfo** , который содержит подробные сведения о совпадениях.</span><span class="sxs-lookup"><span data-stu-id="1ae22-363">The default output of `Select-String` is a **MatchInfo** object, which includes detailed information about the matches.</span></span> <span data-ttu-id="1ae22-364">Информация в объекте полезна при поиске текста в файлах, так как объекты **MatchInfo** имеют такие свойства, как **filename** и **line** .</span><span class="sxs-lookup"><span data-stu-id="1ae22-364">The information in the object is useful when you're searching for text in files, because **MatchInfo** objects have properties such as **Filename** and **Line** .</span></span> <span data-ttu-id="1ae22-365">Если входные данные не находятся в файле, значение этих параметров равно **InputStream** .</span><span class="sxs-lookup"><span data-stu-id="1ae22-365">When the input isn't from the file, the value of these parameters is **InputStream** .</span></span>

<span data-ttu-id="1ae22-366">Если сведения в объекте **MatchInfo** не нужны, используйте параметр **quiet** .</span><span class="sxs-lookup"><span data-stu-id="1ae22-366">If you don't need the information in the **MatchInfo** object, use the **Quiet** parameter.</span></span> <span data-ttu-id="1ae22-367">Параметр **quiet** возвращает логическое значение (true или false), указывающее, найдено ли совпадение вместо объекта **MatchInfo** .</span><span class="sxs-lookup"><span data-stu-id="1ae22-367">The **Quiet** parameter returns a Boolean value (True or False) to indicate whether it found a match, instead of a **MatchInfo** object.</span></span>

<span data-ttu-id="1ae22-368">При сопоставлении фраз `Select-String` использует текущий язык и региональные параметры, заданные для системы.</span><span class="sxs-lookup"><span data-stu-id="1ae22-368">When matching phrases, `Select-String` uses the current culture that is set for the system.</span></span> <span data-ttu-id="1ae22-369">Чтобы найти текущий язык и региональные параметры, используйте `Get-Culture` командлет.</span><span class="sxs-lookup"><span data-stu-id="1ae22-369">To find the current culture, use the `Get-Culture` cmdlet.</span></span>

<span data-ttu-id="1ae22-370">Чтобы найти свойства объекта **MatchInfo** , введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="1ae22-370">To find the properties of a **MatchInfo** object, type the following command:</span></span>

`Select-String -Path test.txt -Pattern 'test' | Get-Member | Format-List -Property *`

## <span data-ttu-id="1ae22-371">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="1ae22-371">RELATED LINKS</span></span>

[<span data-ttu-id="1ae22-372">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="1ae22-372">about_Automatic_Variables</span></span>](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md)

[<span data-ttu-id="1ae22-373">about_Comparison_Operators</span><span class="sxs-lookup"><span data-stu-id="1ae22-373">about_Comparison_Operators</span></span>](../Microsoft.PowerShell.Core/About/about_Comparison_Operators.md)

[<span data-ttu-id="1ae22-374">about_Functions</span><span class="sxs-lookup"><span data-stu-id="1ae22-374">about_Functions</span></span>](../Microsoft.PowerShell.Core/About/about_Functions.md)

[<span data-ttu-id="1ae22-375">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="1ae22-375">about_Quoting_Rules</span></span>](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)

[<span data-ttu-id="1ae22-376">about_Regular_Expressions</span><span class="sxs-lookup"><span data-stu-id="1ae22-376">about_Regular_Expressions</span></span>](../Microsoft.PowerShell.Core/About/about_Regular_Expressions.md)

[<span data-ttu-id="1ae22-377">Get-Alias</span><span class="sxs-lookup"><span data-stu-id="1ae22-377">Get-Alias</span></span>](Get-Alias.md)

[<span data-ttu-id="1ae22-378">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="1ae22-378">Get-ChildItem</span></span>](../Microsoft.PowerShell.Management/Get-ChildItem.md)

[<span data-ttu-id="1ae22-379">Get-Command</span><span class="sxs-lookup"><span data-stu-id="1ae22-379">Get-Command</span></span>](../Microsoft.PowerShell.Core/Get-Command.md)

[<span data-ttu-id="1ae22-380">Get-Member</span><span class="sxs-lookup"><span data-stu-id="1ae22-380">Get-Member</span></span>](Get-Member.md)

[<span data-ttu-id="1ae22-381">Get-WinEvent</span><span class="sxs-lookup"><span data-stu-id="1ae22-381">Get-WinEvent</span></span>](../Microsoft.PowerShell.Diagnostics/Get-WinEvent.md)

[<span data-ttu-id="1ae22-382">Out-File</span><span class="sxs-lookup"><span data-stu-id="1ae22-382">Out-File</span></span>](Out-File.md)