---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convert-string?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Convert-String
ms.openlocfilehash: 29ec9e21277bae02ab94ce5e862787c86a87b439
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227738"
---
# <span data-ttu-id="e5b69-103">Convert-String</span><span class="sxs-lookup"><span data-stu-id="e5b69-103">Convert-String</span></span>

## <span data-ttu-id="e5b69-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="e5b69-104">SYNOPSIS</span></span>
<span data-ttu-id="e5b69-105">Форматирует строку в соответствии с примерами.</span><span class="sxs-lookup"><span data-stu-id="e5b69-105">Formats a string to match examples.</span></span>

## <span data-ttu-id="e5b69-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e5b69-106">SYNTAX</span></span>

```
Convert-String [-Example <System.Collections.Generic.List`1[System.Management.Automation.PSObject]>]
 -InputObject <String> [<CommonParameters>]
```

## <span data-ttu-id="e5b69-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e5b69-107">DESCRIPTION</span></span>

<span data-ttu-id="e5b69-108">Командлет **Convert-String** форматирует строку в соответствии с форматом примеров.</span><span class="sxs-lookup"><span data-stu-id="e5b69-108">The **Convert-String** cmdlet formats a string to match the format of examples.</span></span>

## <span data-ttu-id="e5b69-109">Примеры</span><span class="sxs-lookup"><span data-stu-id="e5b69-109">EXAMPLES</span></span>

### <span data-ttu-id="e5b69-110">Пример 1. преобразование формата строки</span><span class="sxs-lookup"><span data-stu-id="e5b69-110">Example 1: Convert format of a string</span></span>

```powershell
"Mu Han", "Jim Hance", "David Ahs", "Kim Akers" | Convert-String -Example "Ed Wilson=Wilson, E."
```

```output
Han, M.
Hance, J.
Ahs, D.
Akers, K.
```

<span data-ttu-id="e5b69-111">Первая команда создает массив, содержащий имя и фамилию.</span><span class="sxs-lookup"><span data-stu-id="e5b69-111">The first command creates an array that contains first and last names.</span></span>

<span data-ttu-id="e5b69-112">Вторая команда форматирует имена в соответствии с примером.</span><span class="sxs-lookup"><span data-stu-id="e5b69-112">The second command formats the names according to the example.</span></span>
<span data-ttu-id="e5b69-113">Сначала помещается фамилия в выходные данные, а затем — начальное.</span><span class="sxs-lookup"><span data-stu-id="e5b69-113">It puts the surname first in the output, followed by an initial.</span></span>

### <span data-ttu-id="e5b69-114">Пример 2. Упрощение формата строки</span><span class="sxs-lookup"><span data-stu-id="e5b69-114">Example 2: Simplify format of a string</span></span>

```powershell
$composers = @("Johann Sebastian Bach", "Wolfgang Amadeus Mozart", "Frederic Francois Chopin", "Johannes Brahms")
$composers | Convert-String -Example "first middle last=last, first"
```

```output
Bach, Johann
Mozart, Wolfgang
Chopin, Frederic
Brahms, Johannes
```

<span data-ttu-id="e5b69-115">Первая команда создает массив, содержащий имя, отчество и фамилию.</span><span class="sxs-lookup"><span data-stu-id="e5b69-115">The first command creates an array that contains first, middle and last names.</span></span>
<span data-ttu-id="e5b69-116">Обратите внимание, что у последней записи нет отчества.</span><span class="sxs-lookup"><span data-stu-id="e5b69-116">Note that the last entry has no middle name.</span></span>

<span data-ttu-id="e5b69-117">Вторая команда форматирует имена в соответствии с примером.</span><span class="sxs-lookup"><span data-stu-id="e5b69-117">The second command formats the names according to the example.</span></span>
<span data-ttu-id="e5b69-118">Сначала в выходных данных помещается фамилия, за которой следует имя.</span><span class="sxs-lookup"><span data-stu-id="e5b69-118">It puts the last name first in the output, followed by the first name.</span></span>
<span data-ttu-id="e5b69-119">Все средние имена удалены; запись без промежуточного имени обрабатывается правильно.</span><span class="sxs-lookup"><span data-stu-id="e5b69-119">All middle names removed; entry without middle name is handled correctly.</span></span>

### <span data-ttu-id="e5b69-120">Пример 3. управление выходом при несовпадении строк</span><span class="sxs-lookup"><span data-stu-id="e5b69-120">Example 3: Output management when strings don't match example</span></span>

```powershell
$composers = @("Johann Sebastian Bach", "Wolfgang Amadeus Mozart", "Frederic Francois Chopin", "Johannes Brahms")
$composers | Convert-String -Example "first middle last=middle, first"
```

```output
Sebastian, Johann
Amadeus, Wolfgang
Francois, Frederic
```

<span data-ttu-id="e5b69-121">Первая команда создает массив, содержащий имя, отчество и фамилию.</span><span class="sxs-lookup"><span data-stu-id="e5b69-121">The first command creates an array that contains first, middle and last names.</span></span>
<span data-ttu-id="e5b69-122">Обратите внимание, что у последней записи нет отчества.</span><span class="sxs-lookup"><span data-stu-id="e5b69-122">Note that the last entry has no middle name.</span></span>

<span data-ttu-id="e5b69-123">Вторая команда форматирует имена в соответствии с примером.</span><span class="sxs-lookup"><span data-stu-id="e5b69-123">The second command formats the names according to the example.</span></span>
<span data-ttu-id="e5b69-124">Сначала помещается **отчество** в выходных данных, а затем — имя.</span><span class="sxs-lookup"><span data-stu-id="e5b69-124">It puts the **middle name** first in the output, followed by the first name.</span></span>
<span data-ttu-id="e5b69-125">Последняя запись в **$composers** пропускается, так как она не соответствует образцу шаблона: имя не имеет отчества.</span><span class="sxs-lookup"><span data-stu-id="e5b69-125">The last entry in **$Composers** is skipped, because it doesn't match the sample pattern: it has no middle name.</span></span>

### <span data-ttu-id="e5b69-126">Пример 4. предупреждение с помощью непривлекательных пространств</span><span class="sxs-lookup"><span data-stu-id="e5b69-126">Example 4: Caution with beauty spaces</span></span>

```powershell
$composers = @("Antonio Vivaldi", "Richard Wagner ", "Franz Schubert", "Johannes Brahms ")
$composers | Convert-String -Example "Patti Fuller = Fuller, P."
```

```output
 Wagner, R.
 Brahms, J.
```

<span data-ttu-id="e5b69-127">Первая команда создает массив первых и последних имен.</span><span class="sxs-lookup"><span data-stu-id="e5b69-127">The first command creates an array of first and last names.</span></span>
<span data-ttu-id="e5b69-128">Обратите внимание, что второй и четвертый элементы содержат дополнительное место в конце, после последнего имени.</span><span class="sxs-lookup"><span data-stu-id="e5b69-128">Note that second and fourth items have an extra trailing space, after the last name.</span></span>

<span data-ttu-id="e5b69-129">Вторая команда преобразует все строки, которые соответствуют образцу шаблона: _слово, пробел, слово и конечная конечная область_ , все это перед знаком равенства.</span><span class="sxs-lookup"><span data-stu-id="e5b69-129">The second command converts all strings that match the sample pattern: _word, space, word, and final trailing space_ , all of this before the equal sign.</span></span>
<span data-ttu-id="e5b69-130">Кроме того, обратите внимание на начальное пространство в выходных данных.</span><span class="sxs-lookup"><span data-stu-id="e5b69-130">Also, note the leading space in the output.</span></span>

### <span data-ttu-id="e5b69-131">Пример 5. Форматирование сведений о процессе с помощью нескольких шаблонов</span><span class="sxs-lookup"><span data-stu-id="e5b69-131">Example 5: Format process information with multiple patterns</span></span>

```powershell
$ExamplePatterns = @(
    @{before='"Hello","World"'; after='World: Hello'},
    @{before='"Hello","1"'; after='1: Hello'},
    @{before='"Hello-World","22"'; after='22: Hello-World'},
    @{before='"hello world","333"'; after='333: hello world'}
)
$Processes = Get-Process   | Select-Object -Property ProcessName, Id | ConvertTo-Csv -NoTypeInformation
$Processes | Convert-String -Example $ExamplePatterns
```

```output
Id: ProcessName
4368: AGSService
8896: Amazon Music Helper
4420: AppleMobileDeviceService
...
11140: git-bash
0: Idle
...
56: Secure System
...
13028: WmiPrvSE
2724: WUDFHost
2980: WUDFHost
3348: WUDFHost
```

<span data-ttu-id="e5b69-132">В примерах **$ExamplePatterns** определяются различные ожидаемые закономерности в данных.</span><span class="sxs-lookup"><span data-stu-id="e5b69-132">**$ExamplePatterns** defines different expected patterns in the data, through examples.</span></span>

<span data-ttu-id="e5b69-133">Первый шаблон, `@{before='"Hello","World"'; after='World: Hello'}` , считывается следующим образом: _Ожидание строк, в которых слово заключено в двойные кавычки, затем запятая,_ 
 _а вторая и последняя слова, заключенные в кавычки;_ 
 без _пробелов в строке. На выходе: сначала поместите второе слово,_ 
 _без кавычек, затем один пробел, а затем первое слово без кавычек._</span><span class="sxs-lookup"><span data-stu-id="e5b69-133">The first pattern, `@{before='"Hello","World"'; after='World: Hello'}`, reads as follows: _expect strings where a word comes enclosed in double quotes, then a comma,_
_and then the second, and last, word enclosed in quotes;_
_with no spaces in the string. On the output: place second word first,_
_without quotes, then a single space, and then the first word, without quotes._</span></span>

<span data-ttu-id="e5b69-134">Второй шаблон, `@{before='"Hello","1"'; after='1: Hello'}` , считывается следующим образом: _Ожидание строк, в которых слово заключено в двойные кавычки, затем запятая,_ 
 _а затем число, заключенное в кавычки._ 
 без _пробелов в строке. На выходе: сначала поместите номер_ 
 _без кавычек, а затем — один пробел, а затем слово без кавычек._</span><span class="sxs-lookup"><span data-stu-id="e5b69-134">The second pattern, `@{before='"Hello","1"'; after='1: Hello'}`, reads as follows: _expect strings where a word comes enclosed in double quotes, then a comma,_
_and then a number enclosed in quotes;_
_with no spaces in the string. On the output: place the number first,_
_without quotes, then a single space, and then the word, without quotes._</span></span>

<span data-ttu-id="e5b69-135">Третий шаблон, `@{before='"Hello-World","22"'; after='22: Hello-World'}` , выполняет чтение следующим образом: _Ожидание строк, в которых два слова с дефисом заключены в_ 
 _двойные кавычки, затем запятая, а затем число, заключенное в кавычки._ 
 без _пробелов между запятой и третьей двойной кавычкой._ 
 _На выходе: сначала поместите номер без кавычек, а затем один пробел._ 
 _а затем продефисировать слова без кавычек._</span><span class="sxs-lookup"><span data-stu-id="e5b69-135">The third pattern, `@{before='"Hello-World","22"'; after='22: Hello-World'}`, reads as follows: _expect strings where two words with a hyphen in between come enclosed in_
_double quotes, then a comma, and then a number enclosed in quotes;_
_with no spaces between the comma and the third double quote._
_On the output: place the number first, without quotes, then a single space,_
_and then the hyphenated words, without quotes._</span></span>

<span data-ttu-id="e5b69-136">Четвертый и последний, шаблон, `@{before='"hello world","333"'; after='333: hello world'}` , выполняет чтение следующим образом: _ожидайте строки, в которых два слова с пробелами заключены в_ 
 _двойные кавычки, затем запятую, а затем число, заключенное в кавычки._ 
 без _пробелов между запятой и третьей двойной кавычкой._ 
 _На выходе: сначала поместите номер без кавычек, а затем один пробел._ 
 _а затем слова с пробелами между, без кавычек._</span><span class="sxs-lookup"><span data-stu-id="e5b69-136">The fourth, and final, pattern, `@{before='"hello world","333"'; after='333: hello world'}`, reads as follows: _expect strings where two words with a space in between come enclosed in_
_double quotes, then a comma, and then a number enclosed in quotes;_
_with no spaces between the comma and the third double quote._
_On the output: place the number first, without quotes, then a single space,_
_and then the words with the space in between, without quotes._</span></span>

<span data-ttu-id="e5b69-137">Первая команда получает все процессы с помощью командлета Get-Process.</span><span class="sxs-lookup"><span data-stu-id="e5b69-137">The first command gets all processes by using the Get-Process cmdlet.</span></span>
<span data-ttu-id="e5b69-138">Команда передает их в командлет Select-Object, который выбирает имя процесса и идентификатор процесса.</span><span class="sxs-lookup"><span data-stu-id="e5b69-138">The command passes them to the Select-Object cmdlet, which selects the process name and process ID.</span></span> <span data-ttu-id="e5b69-139">В конце конвейера команда преобразует выходные данные в значения с разделителями запятыми без сведений о типе с помощью командлета ConvertTo-Csv.</span><span class="sxs-lookup"><span data-stu-id="e5b69-139">At the end of the pipeline, the command converts the output to comma separated values, without type information, by using the ConvertTo-Csv cmdlet.</span></span>
<span data-ttu-id="e5b69-140">Команда сохраняет результаты в переменной **$Processes** .</span><span class="sxs-lookup"><span data-stu-id="e5b69-140">The command stores the results in the **$Processes** variable.</span></span>
<span data-ttu-id="e5b69-141">**$Processes** теперь содержит имена процессов и PID.</span><span class="sxs-lookup"><span data-stu-id="e5b69-141">**$Processes** now contains process names and PID.</span></span>

<span data-ttu-id="e5b69-142">Во второй команде указывается пример переменной, которая изменяет порядок входных элементов.</span><span class="sxs-lookup"><span data-stu-id="e5b69-142">The second command specifies an example variable that changes the order of the input items.</span></span>
<span data-ttu-id="e5b69-143">Команда преобразует каждую строку в **$Processes** .</span><span class="sxs-lookup"><span data-stu-id="e5b69-143">The command coverts each string in **$Processes** .</span></span>

><span data-ttu-id="e5b69-144">**Примечание** . Четвертый шаблон неявно говорит о том, что сопоставлены два или более слов, разделенных пробелами.</span><span class="sxs-lookup"><span data-stu-id="e5b69-144">**Note** The fourth pattern implicitly says that two or more words separated by spaces are matched.</span></span>
>
><span data-ttu-id="e5b69-145">Без четвертого шаблона сопоставляется только первое слово строки, заключенной в двойные кавычки.</span><span class="sxs-lookup"><span data-stu-id="e5b69-145">Without the fourth pattern, only the first word of the string enclosed in double quotes is matched.</span></span>

## <span data-ttu-id="e5b69-146">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e5b69-146">PARAMETERS</span></span>

### <span data-ttu-id="e5b69-147">-Пример</span><span class="sxs-lookup"><span data-stu-id="e5b69-147">-Example</span></span>

<span data-ttu-id="e5b69-148">Задает список примеров для целевого формата.</span><span class="sxs-lookup"><span data-stu-id="e5b69-148">Specifies a list of examples of the target format.</span></span>
<span data-ttu-id="e5b69-149">Укажите пары, разделенные знаком равенства (=), с исходным шаблоном слева и целевым шаблоном справа, как показано в следующих примерах:</span><span class="sxs-lookup"><span data-stu-id="e5b69-149">Specify pairs separated by the equal (=) sign, with the source pattern on the left and the target pattern on the right, as in the following examples:</span></span>

* `-Example "Hello World=World, Hello"`
* `-Example "Hello World=World: Hello",'"Hello","1"=1: Hello'`

><span data-ttu-id="e5b69-150">**Примечание** . Во втором примере используется список шаблонов</span><span class="sxs-lookup"><span data-stu-id="e5b69-150">**Note** The second example uses a list of patterns</span></span>

<span data-ttu-id="e5b69-151">Кроме того, можно указать список хэш-таблиц, содержащих свойства **Before** и **After** .</span><span class="sxs-lookup"><span data-stu-id="e5b69-151">Alternatively, specify a list of hash tables that contain **Before** and **After** properties.</span></span>

* `-Example @{before='"Hello","World"'; after='World: Hello'}, @{before='"Hello","1"'; after='1: Hello'}`

><span data-ttu-id="e5b69-152">**Внимание!** Старайтесь не использовать пробелы вокруг знака равенства, так как они обрабатываются как часть шаблона.</span><span class="sxs-lookup"><span data-stu-id="e5b69-152">**Caution** Avoid using spaces around the equal sign, as they are treated as part of the pattern.</span></span>

```yaml
Type: System.Collections.Generic.List`1[System.Management.Automation.PSObject]
Parameter Sets: (All)
Aliases: E

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e5b69-153">-InputObject</span><span class="sxs-lookup"><span data-stu-id="e5b69-153">-InputObject</span></span>

<span data-ttu-id="e5b69-154">Задает строку для форматирования.</span><span class="sxs-lookup"><span data-stu-id="e5b69-154">Specifies a string to format.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="e5b69-155">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="e5b69-155">CommonParameters</span></span>

<span data-ttu-id="e5b69-156">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="e5b69-156">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e5b69-157">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="e5b69-157">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e5b69-158">Входные данные</span><span class="sxs-lookup"><span data-stu-id="e5b69-158">INPUTS</span></span>

### <span data-ttu-id="e5b69-159">Строка</span><span class="sxs-lookup"><span data-stu-id="e5b69-159">String</span></span>

<span data-ttu-id="e5b69-160">В этот командлет можно передать строки.</span><span class="sxs-lookup"><span data-stu-id="e5b69-160">You can pipe strings to this cmdlet.</span></span>

## <span data-ttu-id="e5b69-161">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="e5b69-161">OUTPUTS</span></span>

### <span data-ttu-id="e5b69-162">Строка</span><span class="sxs-lookup"><span data-stu-id="e5b69-162">String</span></span>

<span data-ttu-id="e5b69-163">Этот командлет возвращает строку.</span><span class="sxs-lookup"><span data-stu-id="e5b69-163">This cmdlet returns a string.</span></span>

## <span data-ttu-id="e5b69-164">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="e5b69-164">NOTES</span></span>

## <span data-ttu-id="e5b69-165">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="e5b69-165">RELATED LINKS</span></span>

[<span data-ttu-id="e5b69-166">ConvertFrom-String</span><span class="sxs-lookup"><span data-stu-id="e5b69-166">ConvertFrom-String</span></span>](ConvertFrom-String.md)

[<span data-ttu-id="e5b69-167">ConvertTo-Csv</span><span class="sxs-lookup"><span data-stu-id="e5b69-167">ConvertTo-Csv</span></span>](ConvertTo-Csv.md)

[<span data-ttu-id="e5b69-168">Get-Process</span><span class="sxs-lookup"><span data-stu-id="e5b69-168">Get-Process</span></span>](../Microsoft.PowerShell.Management/Get-Process.md)

[<span data-ttu-id="e5b69-169">Out-String</span><span class="sxs-lookup"><span data-stu-id="e5b69-169">Out-String</span></span>](Out-String.md)

[<span data-ttu-id="e5b69-170">Select-Object</span><span class="sxs-lookup"><span data-stu-id="e5b69-170">Select-Object</span></span>](Select-Object.md)
