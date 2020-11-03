---
description: Описание специальных последовательностей символов, управляющих тем, как PowerShell интерпретирует следующие символы в последовательности.
keywords: powershell,командлет
Locale: en-US
ms.date: 04/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_special_characters?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Special_Characters
ms.openlocfilehash: 6856d903276f5cbe4db222ac4c5d64ce6939413e
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93232185"
---
# <a name="about-special-characters"></a><span data-ttu-id="80f69-104">О специальных символах</span><span class="sxs-lookup"><span data-stu-id="80f69-104">About Special Characters</span></span>

## <a name="short-description"></a><span data-ttu-id="80f69-105">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="80f69-105">Short description</span></span>

<span data-ttu-id="80f69-106">Описание специальных последовательностей символов, управляющих тем, как PowerShell интерпретирует следующие символы в последовательности.</span><span class="sxs-lookup"><span data-stu-id="80f69-106">Describes the special character sequences that control how PowerShell interprets the next characters in the sequence.</span></span>

## <a name="long-description"></a><span data-ttu-id="80f69-107">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="80f69-107">Long description</span></span>

<span data-ttu-id="80f69-108">PowerShell поддерживает набор специальных последовательностей символов, которые используются для представления символов, не входящих в стандартную кодировку.</span><span class="sxs-lookup"><span data-stu-id="80f69-108">PowerShell supports a set of special character sequences that are used to represent characters that aren't part of the standard character set.</span></span> <span data-ttu-id="80f69-109">Последовательности обычно называют _escape-последовательностями_.</span><span class="sxs-lookup"><span data-stu-id="80f69-109">The sequences are commonly known as _escape sequences_.</span></span>

<span data-ttu-id="80f69-110">Escape-последовательности начинаются с символа обратной косой черты, называемого грависом (ASCII 96), и учитывают регистр.</span><span class="sxs-lookup"><span data-stu-id="80f69-110">Escape sequences begin with the backtick character, known as the grave accent (ASCII 96), and are case-sensitive.</span></span> <span data-ttu-id="80f69-111">Символ обратной кавычки также может называться Escape- _символом_.</span><span class="sxs-lookup"><span data-stu-id="80f69-111">The backtick character can also be referred to as the _escape character_.</span></span>

<span data-ttu-id="80f69-112">Escape-последовательности обрабатываются только в строках, содержащихся в двойных кавычках ( `"` ).</span><span class="sxs-lookup"><span data-stu-id="80f69-112">Escape sequences are only interpreted when contained in double-quoted (`"`) strings.</span></span>

<span data-ttu-id="80f69-113">PowerShell распознает следующие escape-последовательности:</span><span class="sxs-lookup"><span data-stu-id="80f69-113">PowerShell recognizes these escape sequences:</span></span>

|  <span data-ttu-id="80f69-114">Последовательность</span><span class="sxs-lookup"><span data-stu-id="80f69-114">Sequence</span></span>   |       <span data-ttu-id="80f69-115">Описание</span><span class="sxs-lookup"><span data-stu-id="80f69-115">Description</span></span>       |
| ----------- | ----------------------- |
| `` `0 ``    | <span data-ttu-id="80f69-116">NULL</span><span class="sxs-lookup"><span data-stu-id="80f69-116">Null</span></span>                    |
| `` `a ``    | <span data-ttu-id="80f69-117">Оповещение</span><span class="sxs-lookup"><span data-stu-id="80f69-117">Alert</span></span>                   |
| `` `b ``    | <span data-ttu-id="80f69-118">Отмена</span><span class="sxs-lookup"><span data-stu-id="80f69-118">Backspace</span></span>               |
| `` `e ``    | <span data-ttu-id="80f69-119">ESC</span><span class="sxs-lookup"><span data-stu-id="80f69-119">Escape</span></span>                  |
| `` `f ``    | <span data-ttu-id="80f69-120">Перевод страницы</span><span class="sxs-lookup"><span data-stu-id="80f69-120">Form feed</span></span>               |
| `` `n ``    | <span data-ttu-id="80f69-121">Новая строка</span><span class="sxs-lookup"><span data-stu-id="80f69-121">New line</span></span>                |
| `` `r ``    | <span data-ttu-id="80f69-122">Возврат каретки</span><span class="sxs-lookup"><span data-stu-id="80f69-122">Carriage return</span></span>         |
| `` `t ``    | <span data-ttu-id="80f69-123">Горизонтальная табуляция</span><span class="sxs-lookup"><span data-stu-id="80f69-123">Horizontal tab</span></span>          |
| `` `u{x} `` | <span data-ttu-id="80f69-124">Escape-последовательность Юникода</span><span class="sxs-lookup"><span data-stu-id="80f69-124">Unicode escape sequence</span></span> |
| `` `v ``    | <span data-ttu-id="80f69-125">Вертикальная табуляция</span><span class="sxs-lookup"><span data-stu-id="80f69-125">Vertical tab</span></span>            |

<span data-ttu-id="80f69-126">Кроме того, PowerShell имеет специальный маркер, помечающий, где следует останавливаться при разборе.</span><span class="sxs-lookup"><span data-stu-id="80f69-126">PowerShell also has a special token to mark where you want parsing to stop.</span></span> <span data-ttu-id="80f69-127">Все символы, которые следуют за этим маркером, используются в качестве литеральных значений, которые не интерпретируемы.</span><span class="sxs-lookup"><span data-stu-id="80f69-127">All characters that follow this token are used as literal values that aren't interpreted.</span></span>

<span data-ttu-id="80f69-128">Специальный маркер синтаксического анализа:</span><span class="sxs-lookup"><span data-stu-id="80f69-128">Special parsing token:</span></span>

| <span data-ttu-id="80f69-129">Последовательность</span><span class="sxs-lookup"><span data-stu-id="80f69-129">Sequence</span></span> |            <span data-ttu-id="80f69-130">Описание</span><span class="sxs-lookup"><span data-stu-id="80f69-130">Description</span></span>             |
| -------- | ---------------------------------- |
| `--%`    | <span data-ttu-id="80f69-131">Завершите синтаксический анализ всех следующих элементов</span><span class="sxs-lookup"><span data-stu-id="80f69-131">Stop parsing anything that follows</span></span> |

## <a name="null-0"></a><span data-ttu-id="80f69-132">NULL (' 0)</span><span class="sxs-lookup"><span data-stu-id="80f69-132">Null (\`0)</span></span>

<span data-ttu-id="80f69-133">Символ null ( `` `0 `` ) отображается как пустое пространство в выходных данных PowerShell.</span><span class="sxs-lookup"><span data-stu-id="80f69-133">The null (`` `0 ``) character appears as an empty space in PowerShell output.</span></span>
<span data-ttu-id="80f69-134">Эта функция позволяет использовать PowerShell для чтения и обработки текстовых файлов, использующих нуль символов, таких как завершение строк или индикаторы завершения записи.</span><span class="sxs-lookup"><span data-stu-id="80f69-134">This functionality allows you to use PowerShell to read and process text files that use null characters, such as string termination or record termination indicators.</span></span> <span data-ttu-id="80f69-135">Специальный символ NULL не эквивалентен `$null` переменной, в которой хранится значение **null** .</span><span class="sxs-lookup"><span data-stu-id="80f69-135">The null special character isn't equivalent to the `$null` variable, which stores a **null** value.</span></span>

## <a name="alert-a"></a><span data-ttu-id="80f69-136">Предупреждение (' а)</span><span class="sxs-lookup"><span data-stu-id="80f69-136">Alert (\`a)</span></span>

<span data-ttu-id="80f69-137">Символ предупреждения ( `` `a `` ) отправляет звуковой сигнал на динамик компьютера.</span><span class="sxs-lookup"><span data-stu-id="80f69-137">The alert (`` `a ``) character sends a beep signal to the computer's speaker.</span></span>
<span data-ttu-id="80f69-138">Этот символ можно использовать для предупреждения пользователя о предопределенном действии.</span><span class="sxs-lookup"><span data-stu-id="80f69-138">You can use this character to warn a user about an impending action.</span></span> <span data-ttu-id="80f69-139">В следующем примере два звуковых сигнала отправляются на динамик локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="80f69-139">The following example sends two beep signals to the local computer's speaker.</span></span>

```powershell
for ($i = 0; $i -le 1; $i++){"`a"}
```

## <a name="backspace-b"></a><span data-ttu-id="80f69-140">Backspace (' б)</span><span class="sxs-lookup"><span data-stu-id="80f69-140">Backspace (\`b)</span></span>

<span data-ttu-id="80f69-141">Символ Backspace ( `` `b `` ) перемещает курсор назад на один символ, но не удаляет символы.</span><span class="sxs-lookup"><span data-stu-id="80f69-141">The backspace (`` `b ``) character moves the cursor back one character, but it doesn't delete any characters.</span></span>

<span data-ttu-id="80f69-142">Этот пример записывает слово **BACKUP** , а затем дважды перемещает курсор назад.</span><span class="sxs-lookup"><span data-stu-id="80f69-142">The example writes the word **backup** and then moves the cursor back twice.</span></span>
<span data-ttu-id="80f69-143">Затем в новой позиции записывается пробел, за которым следует слово **out**.</span><span class="sxs-lookup"><span data-stu-id="80f69-143">Then, at the new position, writes a space followed by the word **out**.</span></span>

```powershell
"backup`b`b out"
```

```Output
back out
```

## <a name="escape-e"></a><span data-ttu-id="80f69-144">Escape (' e ')</span><span class="sxs-lookup"><span data-stu-id="80f69-144">Escape (\`e)</span></span>

<span data-ttu-id="80f69-145">Escape- `` `e `` символ () чаще всего используется для указания виртуальной последовательности (escape-последовательность ANSI), которая изменяет цвет текста и других текстовых атрибутов, таких как выделение полужирным шрифтом и подчеркивание.</span><span class="sxs-lookup"><span data-stu-id="80f69-145">The escape (`` `e ``) character is most commonly used to specify a virtual terminal sequence (ANSI escape sequence) that modifies the color of text and other text attributes such as bolding and underlining.</span></span> <span data-ttu-id="80f69-146">Эти последовательности также можно использовать для позиционирования курсора и прокрутки.</span><span class="sxs-lookup"><span data-stu-id="80f69-146">These sequences can also be used for cursor positioning and scrolling.</span></span> <span data-ttu-id="80f69-147">Узел PowerShell должен поддерживать виртуальные последовательности терминалов.</span><span class="sxs-lookup"><span data-stu-id="80f69-147">The PowerShell host must support virtual terminal sequences.</span></span> <span data-ttu-id="80f69-148">Можно проверить логическое значение, `$Host.UI.SupportsVirtualTerminal` чтобы определить, поддерживаются ли эти последовательности ANSI.</span><span class="sxs-lookup"><span data-stu-id="80f69-148">You can check the boolean value of `$Host.UI.SupportsVirtualTerminal` to determine if these ANSI sequences are supported.</span></span>

<span data-ttu-id="80f69-149">Дополнительные сведения о escape-последовательностях ANSI см. в разделе [ANSI_escape_code](https://en.wikipedia.org/wiki/ANSI_escape_code).</span><span class="sxs-lookup"><span data-stu-id="80f69-149">For more information about ANSI escape sequences, see [ANSI_escape_code](https://en.wikipedia.org/wiki/ANSI_escape_code).</span></span>

<span data-ttu-id="80f69-150">В следующем примере выводится текст с зеленым цветом переднего плана.</span><span class="sxs-lookup"><span data-stu-id="80f69-150">The following example outputs text with a green foreground color.</span></span>

```powershell
$fgColor = 32 # green
"`e[${fgColor}mGreen text`e[0m"
```

```Output
Green text
```

## <a name="form-feed-f"></a><span data-ttu-id="80f69-151">Веб-канал формы (' ' f ' ')</span><span class="sxs-lookup"><span data-stu-id="80f69-151">Form feed (\`f)</span></span>

<span data-ttu-id="80f69-152">Символ перевода формы ( `` `f `` ) представляет собой инструкцию PRINT, которая извлекает текущую страницу и продолжит печать на следующей странице.</span><span class="sxs-lookup"><span data-stu-id="80f69-152">The form feed (`` `f ``) character is a print instruction that ejects the current page and continues printing on the next page.</span></span> <span data-ttu-id="80f69-153">Символ перевода формы влияет только на печатные документы.</span><span class="sxs-lookup"><span data-stu-id="80f69-153">The form feed character only affects printed documents.</span></span> <span data-ttu-id="80f69-154">Он не влияет на вывод на экран.</span><span class="sxs-lookup"><span data-stu-id="80f69-154">It doesn't affect screen output.</span></span>

## <a name="new-line-n"></a><span data-ttu-id="80f69-155">Новая строка (' n)</span><span class="sxs-lookup"><span data-stu-id="80f69-155">New line (\`n)</span></span>

<span data-ttu-id="80f69-156">Символ новой строки ( `` `n `` ) вставляет разрыв строки сразу после символа.</span><span class="sxs-lookup"><span data-stu-id="80f69-156">The new line (`` `n ``) character inserts a line break immediately after the character.</span></span>

<span data-ttu-id="80f69-157">В этом примере показано, как использовать символ новой строки для создания разрывов строк в `Write-Host` команде.</span><span class="sxs-lookup"><span data-stu-id="80f69-157">This example shows how to use the new line character to create line breaks in a `Write-Host` command.</span></span>

```powershell
"There are two line breaks to create a blank line`n`nbetween the words."
```

```Output
There are two line breaks to create a blank line

between the words.
```

## <a name="carriage-return-r"></a><span data-ttu-id="80f69-158">Возврат каретки (' r)</span><span class="sxs-lookup"><span data-stu-id="80f69-158">Carriage return (\`r)</span></span>

<span data-ttu-id="80f69-159">Символ возврата каретки ( `` `r `` ) перемещает выходной курсор в начало текущей строки и продолжается запись.</span><span class="sxs-lookup"><span data-stu-id="80f69-159">The carriage return (`` `r ``) character moves the output cursor to the beginning of the current line and continues writing.</span></span> <span data-ttu-id="80f69-160">Все символы в текущей строке перезаписываются.</span><span class="sxs-lookup"><span data-stu-id="80f69-160">Any characters on the current line are overwritten.</span></span>

<span data-ttu-id="80f69-161">В этом примере текст перед возвратом каретки перезаписывается.</span><span class="sxs-lookup"><span data-stu-id="80f69-161">In this example, the text before the carriage return is overwritten.</span></span>

```powershell
Write-Host "These characters are overwritten.`rI want this text instead "
```

<span data-ttu-id="80f69-162">Обратите внимание, что текст перед `` `r `` символом не удаляется, он перезаписывается.</span><span class="sxs-lookup"><span data-stu-id="80f69-162">Notice that the text before the `` `r `` character is not deleted, it is overwritten.</span></span>

```Output
I want this text instead written.
```

## <a name="horizontal-tab-t"></a><span data-ttu-id="80f69-163">Горизонтальная табуляция ('t)</span><span class="sxs-lookup"><span data-stu-id="80f69-163">Horizontal tab (\`t)</span></span>

<span data-ttu-id="80f69-164">Символ горизонтальной табуляции ( `` `t `` ) перемещается на следующую позицию табуляции и продолжит запись в этот момент.</span><span class="sxs-lookup"><span data-stu-id="80f69-164">The horizontal tab (`` `t ``) character advances to the next tab stop and continues writing at that point.</span></span> <span data-ttu-id="80f69-165">По умолчанию в консоли PowerShell имеется позиция табуляции в каждой восьмой области.</span><span class="sxs-lookup"><span data-stu-id="80f69-165">By default, the PowerShell console has a tab stop at every eighth space.</span></span>

<span data-ttu-id="80f69-166">В этом примере вставляются две вкладки между каждым столбцом.</span><span class="sxs-lookup"><span data-stu-id="80f69-166">This example inserts two tabs between each column.</span></span>

```powershell
"Column1`t`tColumn2`t`tColumn3"
```

```Output
Column1         Column2         Column3
```

## <a name="unicode-character-ux"></a><span data-ttu-id="80f69-167">Символ Юникода (' u {x})</span><span class="sxs-lookup"><span data-stu-id="80f69-167">Unicode character (\`u{x})</span></span>

<span data-ttu-id="80f69-168">Escape-последовательность Юникода ( `` `u{x} `` ) позволяет указать любой символ Юникода в шестнадцатеричном представлении его кодовой точки.</span><span class="sxs-lookup"><span data-stu-id="80f69-168">The Unicode escape sequence (`` `u{x} ``) allows you to specify any Unicode character by the hexadecimal representation of its code point.</span></span> <span data-ttu-id="80f69-169">Сюда входят символы Юникода, расположенные над базовой многоязычной плоскостью (> `0xFFFF` ), которая содержит символы эмодзи, такие как **бегунок up** ( `` `u{1F44D} `` ).</span><span class="sxs-lookup"><span data-stu-id="80f69-169">This includes Unicode characters above the Basic Multilingual Plane (> `0xFFFF`) which includes emoji characters such as the **thumbs up** (`` `u{1F44D} ``) character.</span></span> <span data-ttu-id="80f69-170">Escape-последовательности Юникода требуется по крайней мере одна шестнадцатеричная цифра и поддерживает до шести шестнадцатеричных цифр.</span><span class="sxs-lookup"><span data-stu-id="80f69-170">The Unicode escape sequence requires at least one hexadecimal digit and supports up to six hexadecimal digits.</span></span> <span data-ttu-id="80f69-171">Максимальное шестнадцатеричное значение для последовательности — `10FFFF` .</span><span class="sxs-lookup"><span data-stu-id="80f69-171">The maximum hexadecimal value for the sequence is `10FFFF`.</span></span>

<span data-ttu-id="80f69-172">В этом примере выводится символ " **стрелка вверх** " (&#x2195;).</span><span class="sxs-lookup"><span data-stu-id="80f69-172">This example outputs the **up down arrow** (&#x2195;) symbol.</span></span>

```powershell
"`u{2195}"
```

## <a name="vertical-tab-v"></a><span data-ttu-id="80f69-173">Вертикальная табуляция ("v")</span><span class="sxs-lookup"><span data-stu-id="80f69-173">Vertical tab (\`v)</span></span>

<span data-ttu-id="80f69-174">Символ горизонтальной табуляции ( `` `v `` ) перемещается на следующую позицию вертикальной табуляции и записывает остальные выходные данные в этот момент.</span><span class="sxs-lookup"><span data-stu-id="80f69-174">The horizontal tab (`` `v ``) character advances to the next vertical tab stop and writes the remaining output at that point.</span></span> <span data-ttu-id="80f69-175">Это не влияет на консоль Windows по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="80f69-175">This has no effect in the default Windows console.</span></span>

```powershell
Write-Host "There is a vertical tab`vbetween the words."
```

<span data-ttu-id="80f69-176">В следующем примере показаны выходные данные, которые можно получить на принтере или на другом узле консоли.</span><span class="sxs-lookup"><span data-stu-id="80f69-176">The following example shows the output you would get on a printer or in a different console host.</span></span>

```Output
There is a vertical tab
                       between the words.
```

## <a name="stop-parsing-token---"></a><span data-ttu-id="80f69-177">Маркер отмены синтаксического анализа (--%)</span><span class="sxs-lookup"><span data-stu-id="80f69-177">Stop-parsing token (--%)</span></span>

<span data-ttu-id="80f69-178">Токен "Отмена синтаксического анализа" ( `--%` ) предотвращает интерпретацию строк в PowerShell как командами и выражениями PowerShell.</span><span class="sxs-lookup"><span data-stu-id="80f69-178">The stop-parsing (`--%`) token prevents PowerShell from interpreting strings as PowerShell commands and expressions.</span></span> <span data-ttu-id="80f69-179">Это позволяет передавать эти строки другим программам для интерпретации.</span><span class="sxs-lookup"><span data-stu-id="80f69-179">This allows those strings to be passed to other programs for interpretation.</span></span>

<span data-ttu-id="80f69-180">Поместите токен "точка-анализ" после имени программы и перед аргументами программы, которые могут вызвать ошибки.</span><span class="sxs-lookup"><span data-stu-id="80f69-180">Place the stop-parsing token after the program name and before program arguments that might cause errors.</span></span>

<span data-ttu-id="80f69-181">В этом примере `Icacls` команда использует токен-синтаксический анализ.</span><span class="sxs-lookup"><span data-stu-id="80f69-181">In this example, the `Icacls` command uses the stop-parsing token.</span></span>

```powershell
icacls X:\VMS --% /grant Dom\HVAdmin:(CI)(OI)F
```

<span data-ttu-id="80f69-182">PowerShell отправляет следующую строку в `Icacls` .</span><span class="sxs-lookup"><span data-stu-id="80f69-182">PowerShell sends the following string to `Icacls`.</span></span>

```
X:\VMS /grant Dom\HVAdmin:(CI)(OI)F
```

<span data-ttu-id="80f69-183">Вот еще один пример.</span><span class="sxs-lookup"><span data-stu-id="80f69-183">Here is another example.</span></span> <span data-ttu-id="80f69-184">Функция **шоваргс** выводит переданные ей значения.</span><span class="sxs-lookup"><span data-stu-id="80f69-184">The **showArgs** function outputs the values passed to it.</span></span> <span data-ttu-id="80f69-185">В этом примере мы передаем переменную с именем `$HOME` в функцию дважды.</span><span class="sxs-lookup"><span data-stu-id="80f69-185">In this example, we pass the variable named `$HOME` to the function twice.</span></span>

```powershell
function showArgs {
  "`$args = " + ($args -join '|')
}

showArgs $HOME --% $HOME
```

В выходных данных можно увидеть, что для первого параметра Переменная `$HOME` интерпретируется PowerShell, чтобы значение переменной передавалось функции. <span data-ttu-id="80f69-187">Второе использование `$HOME` поступает после маркера-синтаксического анализа, поэтому строка "$Home" передается в функцию без интерпретации.</span><span class="sxs-lookup"><span data-stu-id="80f69-187">The second use of `$HOME` comes after the stop-parsing token, so the string "$HOME" is passed to the function without interpretation.</span></span>

```Output
$args = C:\Users\username|--%|$HOME
```

<span data-ttu-id="80f69-188">Дополнительные сведения о токене завершения синтаксического анализа см. в разделе [about_Parsing](about_Parsing.md).</span><span class="sxs-lookup"><span data-stu-id="80f69-188">For more information about the stop-parsing token, see [about_Parsing](about_Parsing.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="80f69-189">См. также статью</span><span class="sxs-lookup"><span data-stu-id="80f69-189">See also</span></span>

[<span data-ttu-id="80f69-190">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="80f69-190">about_Quoting_Rules</span></span>](about_Quoting_Rules.md)

