---
description: Описание специальных последовательностей символов, управляющих тем, как PowerShell интерпретирует следующие символы в последовательности.
keywords: powershell,командлет
Locale: en-US
ms.date: 04/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_special_characters?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Special_Characters
ms.openlocfilehash: 875a1c3c63e759151c3c64b5396312b030955cb7
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231925"
---
# <a name="about-special-characters"></a><span data-ttu-id="952c4-104">О специальных символах</span><span class="sxs-lookup"><span data-stu-id="952c4-104">About Special Characters</span></span>

## <a name="short-description"></a><span data-ttu-id="952c4-105">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="952c4-105">Short description</span></span>

<span data-ttu-id="952c4-106">Описание специальных последовательностей символов, управляющих тем, как PowerShell интерпретирует следующие символы в последовательности.</span><span class="sxs-lookup"><span data-stu-id="952c4-106">Describes the special character sequences that control how PowerShell interprets the next characters in the sequence.</span></span>

## <a name="long-description"></a><span data-ttu-id="952c4-107">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="952c4-107">Long description</span></span>

<span data-ttu-id="952c4-108">PowerShell поддерживает набор специальных последовательностей символов, которые используются для представления символов, не входящих в стандартную кодировку.</span><span class="sxs-lookup"><span data-stu-id="952c4-108">PowerShell supports a set of special character sequences that are used to represent characters that aren't part of the standard character set.</span></span> <span data-ttu-id="952c4-109">Последовательности обычно называют _escape-последовательностями_ .</span><span class="sxs-lookup"><span data-stu-id="952c4-109">The sequences are commonly known as _escape sequences_ .</span></span>

<span data-ttu-id="952c4-110">Escape-последовательности начинаются с символа обратной косой черты, называемого грависом (ASCII 96), и учитывают регистр.</span><span class="sxs-lookup"><span data-stu-id="952c4-110">Escape sequences begin with the backtick character, known as the grave accent (ASCII 96), and are case-sensitive.</span></span> <span data-ttu-id="952c4-111">Символ обратной кавычки также может называться Escape- _символом_ .</span><span class="sxs-lookup"><span data-stu-id="952c4-111">The backtick character can also be referred to as the _escape character_ .</span></span>

<span data-ttu-id="952c4-112">Escape-последовательности обрабатываются только в строках, содержащихся в двойных кавычках ( `"` ).</span><span class="sxs-lookup"><span data-stu-id="952c4-112">Escape sequences are only interpreted when contained in double-quoted (`"`) strings.</span></span>

<span data-ttu-id="952c4-113">PowerShell распознает следующие escape-последовательности:</span><span class="sxs-lookup"><span data-stu-id="952c4-113">PowerShell recognizes these escape sequences:</span></span>

|  <span data-ttu-id="952c4-114">Последовательность</span><span class="sxs-lookup"><span data-stu-id="952c4-114">Sequence</span></span>   |       <span data-ttu-id="952c4-115">Описание</span><span class="sxs-lookup"><span data-stu-id="952c4-115">Description</span></span>       |
| ----------- | ----------------------- |
| `` `0 ``    | <span data-ttu-id="952c4-116">NULL</span><span class="sxs-lookup"><span data-stu-id="952c4-116">Null</span></span>                    |
| `` `a ``    | <span data-ttu-id="952c4-117">Оповещение</span><span class="sxs-lookup"><span data-stu-id="952c4-117">Alert</span></span>                   |
| `` `b ``    | <span data-ttu-id="952c4-118">Отмена</span><span class="sxs-lookup"><span data-stu-id="952c4-118">Backspace</span></span>               |
| `` `f ``    | <span data-ttu-id="952c4-119">Перевод страницы</span><span class="sxs-lookup"><span data-stu-id="952c4-119">Form feed</span></span>               |
| `` `n ``    | <span data-ttu-id="952c4-120">Новая строка</span><span class="sxs-lookup"><span data-stu-id="952c4-120">New line</span></span>                |
| `` `r ``    | <span data-ttu-id="952c4-121">Возврат каретки</span><span class="sxs-lookup"><span data-stu-id="952c4-121">Carriage return</span></span>         |
| `` `t ``    | <span data-ttu-id="952c4-122">Горизонтальная табуляция</span><span class="sxs-lookup"><span data-stu-id="952c4-122">Horizontal tab</span></span>          |
| `` `v ``    | <span data-ttu-id="952c4-123">Вертикальная табуляция</span><span class="sxs-lookup"><span data-stu-id="952c4-123">Vertical tab</span></span>            |

<span data-ttu-id="952c4-124">Кроме того, PowerShell имеет специальный маркер, помечающий, где следует останавливаться при разборе.</span><span class="sxs-lookup"><span data-stu-id="952c4-124">PowerShell also has a special token to mark where you want parsing to stop.</span></span> <span data-ttu-id="952c4-125">Все символы, которые следуют за этим маркером, используются в качестве литеральных значений, которые не интерпретируемы.</span><span class="sxs-lookup"><span data-stu-id="952c4-125">All characters that follow this token are used as literal values that aren't interpreted.</span></span>

<span data-ttu-id="952c4-126">Специальный маркер синтаксического анализа:</span><span class="sxs-lookup"><span data-stu-id="952c4-126">Special parsing token:</span></span>

| <span data-ttu-id="952c4-127">Последовательность</span><span class="sxs-lookup"><span data-stu-id="952c4-127">Sequence</span></span> |            <span data-ttu-id="952c4-128">Описание</span><span class="sxs-lookup"><span data-stu-id="952c4-128">Description</span></span>             |
| -------- | ---------------------------------- |
| `--%`    | <span data-ttu-id="952c4-129">Завершите синтаксический анализ всех следующих элементов</span><span class="sxs-lookup"><span data-stu-id="952c4-129">Stop parsing anything that follows</span></span> |

## <a name="null-0"></a><span data-ttu-id="952c4-130">NULL (' 0)</span><span class="sxs-lookup"><span data-stu-id="952c4-130">Null (\`0)</span></span>

<span data-ttu-id="952c4-131">Символ null ( `` `0 `` ) отображается как пустое пространство в выходных данных PowerShell.</span><span class="sxs-lookup"><span data-stu-id="952c4-131">The null (`` `0 ``) character appears as an empty space in PowerShell output.</span></span>
<span data-ttu-id="952c4-132">Эта функция позволяет использовать PowerShell для чтения и обработки текстовых файлов, использующих нуль символов, таких как завершение строк или индикаторы завершения записи.</span><span class="sxs-lookup"><span data-stu-id="952c4-132">This functionality allows you to use PowerShell to read and process text files that use null characters, such as string termination or record termination indicators.</span></span> <span data-ttu-id="952c4-133">Специальный символ NULL не эквивалентен `$null` переменной, в которой хранится значение **null** .</span><span class="sxs-lookup"><span data-stu-id="952c4-133">The null special character isn't equivalent to the `$null` variable, which stores a **null** value.</span></span>

## <a name="alert-a"></a><span data-ttu-id="952c4-134">Предупреждение (' а)</span><span class="sxs-lookup"><span data-stu-id="952c4-134">Alert (\`a)</span></span>

<span data-ttu-id="952c4-135">Символ предупреждения ( `` `a `` ) отправляет звуковой сигнал на динамик компьютера.</span><span class="sxs-lookup"><span data-stu-id="952c4-135">The alert (`` `a ``) character sends a beep signal to the computer's speaker.</span></span>
<span data-ttu-id="952c4-136">Этот символ можно использовать для предупреждения пользователя о предопределенном действии.</span><span class="sxs-lookup"><span data-stu-id="952c4-136">You can use this character to warn a user about an impending action.</span></span> <span data-ttu-id="952c4-137">В следующем примере два звуковых сигнала отправляются на динамик локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="952c4-137">The following example sends two beep signals to the local computer's speaker.</span></span>

```powershell
for ($i = 0; $i -le 1; $i++){"`a"}
```

## <a name="backspace-b"></a><span data-ttu-id="952c4-138">Backspace (' б)</span><span class="sxs-lookup"><span data-stu-id="952c4-138">Backspace (\`b)</span></span>

<span data-ttu-id="952c4-139">Символ Backspace ( `` `b `` ) перемещает курсор назад на один символ, но не удаляет символы.</span><span class="sxs-lookup"><span data-stu-id="952c4-139">The backspace (`` `b ``) character moves the cursor back one character, but it doesn't delete any characters.</span></span>

<span data-ttu-id="952c4-140">Этот пример записывает слово **BACKUP** , а затем дважды перемещает курсор назад.</span><span class="sxs-lookup"><span data-stu-id="952c4-140">The example writes the word **backup** and then moves the cursor back twice.</span></span>
<span data-ttu-id="952c4-141">Затем в новой позиции записывается пробел, за которым следует слово **out** .</span><span class="sxs-lookup"><span data-stu-id="952c4-141">Then, at the new position, writes a space followed by the word **out** .</span></span>

```powershell
"backup`b`b out"
```

```Output
back out
```

## <a name="form-feed-f"></a><span data-ttu-id="952c4-142">Веб-канал формы (' ' f ' ')</span><span class="sxs-lookup"><span data-stu-id="952c4-142">Form feed (\`f)</span></span>

<span data-ttu-id="952c4-143">Символ перевода формы ( `` `f `` ) представляет собой инструкцию PRINT, которая извлекает текущую страницу и продолжит печать на следующей странице.</span><span class="sxs-lookup"><span data-stu-id="952c4-143">The form feed (`` `f ``) character is a print instruction that ejects the current page and continues printing on the next page.</span></span> <span data-ttu-id="952c4-144">Символ перевода формы влияет только на печатные документы.</span><span class="sxs-lookup"><span data-stu-id="952c4-144">The form feed character only affects printed documents.</span></span> <span data-ttu-id="952c4-145">Он не влияет на вывод на экран.</span><span class="sxs-lookup"><span data-stu-id="952c4-145">It doesn't affect screen output.</span></span>

## <a name="new-line-n"></a><span data-ttu-id="952c4-146">Новая строка (' n)</span><span class="sxs-lookup"><span data-stu-id="952c4-146">New line (\`n)</span></span>

<span data-ttu-id="952c4-147">Символ новой строки ( `` `n `` ) вставляет разрыв строки сразу после символа.</span><span class="sxs-lookup"><span data-stu-id="952c4-147">The new line (`` `n ``) character inserts a line break immediately after the character.</span></span>

<span data-ttu-id="952c4-148">В этом примере показано, как использовать символ новой строки для создания разрывов строк в `Write-Host` команде.</span><span class="sxs-lookup"><span data-stu-id="952c4-148">This example shows how to use the new line character to create line breaks in a `Write-Host` command.</span></span>

```powershell
"There are two line breaks to create a blank line`n`nbetween the words."
```

```Output
There are two line breaks to create a blank line

between the words.
```

## <a name="carriage-return-r"></a><span data-ttu-id="952c4-149">Возврат каретки (' r)</span><span class="sxs-lookup"><span data-stu-id="952c4-149">Carriage return (\`r)</span></span>

<span data-ttu-id="952c4-150">Символ возврата каретки ( `` `r `` ) перемещает выходной курсор в начало текущей строки и продолжается запись.</span><span class="sxs-lookup"><span data-stu-id="952c4-150">The carriage return (`` `r ``) character moves the output cursor to the beginning of the current line and continues writing.</span></span> <span data-ttu-id="952c4-151">Все символы в текущей строке перезаписываются.</span><span class="sxs-lookup"><span data-stu-id="952c4-151">Any characters on the current line are overwritten.</span></span>

<span data-ttu-id="952c4-152">В этом примере текст перед возвратом каретки перезаписывается.</span><span class="sxs-lookup"><span data-stu-id="952c4-152">In this example, the text before the carriage return is overwritten.</span></span>

```powershell
Write-Host "These characters are overwritten.`rI want this text instead "
```

<span data-ttu-id="952c4-153">Обратите внимание, что текст перед `` `r `` символом не удаляется, он перезаписывается.</span><span class="sxs-lookup"><span data-stu-id="952c4-153">Notice that the text before the `` `r `` character is not deleted, it is overwritten.</span></span>

```Output
I want this text instead written.
```

## <a name="horizontal-tab-t"></a><span data-ttu-id="952c4-154">Горизонтальная табуляция ('t)</span><span class="sxs-lookup"><span data-stu-id="952c4-154">Horizontal tab (\`t)</span></span>

<span data-ttu-id="952c4-155">Символ горизонтальной табуляции ( `` `t `` ) перемещается на следующую позицию табуляции и продолжит запись в этот момент.</span><span class="sxs-lookup"><span data-stu-id="952c4-155">The horizontal tab (`` `t ``) character advances to the next tab stop and continues writing at that point.</span></span> <span data-ttu-id="952c4-156">По умолчанию в консоли PowerShell имеется позиция табуляции в каждой восьмой области.</span><span class="sxs-lookup"><span data-stu-id="952c4-156">By default, the PowerShell console has a tab stop at every eighth space.</span></span>

<span data-ttu-id="952c4-157">В этом примере вставляются две вкладки между каждым столбцом.</span><span class="sxs-lookup"><span data-stu-id="952c4-157">This example inserts two tabs between each column.</span></span>

```powershell
"Column1`t`tColumn2`t`tColumn3"
```

```Output
Column1         Column2         Column3
```

## <a name="vertical-tab-v"></a><span data-ttu-id="952c4-158">Вертикальная табуляция ("v")</span><span class="sxs-lookup"><span data-stu-id="952c4-158">Vertical tab (\`v)</span></span>

<span data-ttu-id="952c4-159">Символ горизонтальной табуляции ( `` `v `` ) перемещается на следующую позицию вертикальной табуляции и записывает остальные выходные данные в этот момент.</span><span class="sxs-lookup"><span data-stu-id="952c4-159">The horizontal tab (`` `v ``) character advances to the next vertical tab stop and writes the remaining output at that point.</span></span> <span data-ttu-id="952c4-160">Это не влияет на консоль Windows по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="952c4-160">This has no effect in the default Windows console.</span></span>

```powershell
Write-Host "There is a vertical tab`vbetween the words."
```

<span data-ttu-id="952c4-161">В следующем примере показаны выходные данные, которые можно получить на принтере или на другом узле консоли.</span><span class="sxs-lookup"><span data-stu-id="952c4-161">The following example shows the output you would get on a printer or in a different console host.</span></span>

```Output
There is a vertical tab
                       between the words.
```

## <a name="stop-parsing-token---"></a><span data-ttu-id="952c4-162">Маркер отмены синтаксического анализа (--%)</span><span class="sxs-lookup"><span data-stu-id="952c4-162">Stop-parsing token (--%)</span></span>

<span data-ttu-id="952c4-163">Токен "Отмена синтаксического анализа" ( `--%` ) предотвращает интерпретацию строк в PowerShell как командами и выражениями PowerShell.</span><span class="sxs-lookup"><span data-stu-id="952c4-163">The stop-parsing (`--%`) token prevents PowerShell from interpreting strings as PowerShell commands and expressions.</span></span> <span data-ttu-id="952c4-164">Это позволяет передавать эти строки другим программам для интерпретации.</span><span class="sxs-lookup"><span data-stu-id="952c4-164">This allows those strings to be passed to other programs for interpretation.</span></span>

<span data-ttu-id="952c4-165">Поместите токен "точка-анализ" после имени программы и перед аргументами программы, которые могут вызвать ошибки.</span><span class="sxs-lookup"><span data-stu-id="952c4-165">Place the stop-parsing token after the program name and before program arguments that might cause errors.</span></span>

<span data-ttu-id="952c4-166">В этом примере `Icacls` команда использует токен-синтаксический анализ.</span><span class="sxs-lookup"><span data-stu-id="952c4-166">In this example, the `Icacls` command uses the stop-parsing token.</span></span>

```powershell
icacls X:\VMS --% /grant Dom\HVAdmin:(CI)(OI)F
```

<span data-ttu-id="952c4-167">PowerShell отправляет следующую строку в `Icacls` .</span><span class="sxs-lookup"><span data-stu-id="952c4-167">PowerShell sends the following string to `Icacls`.</span></span>

```
X:\VMS /grant Dom\HVAdmin:(CI)(OI)F
```

<span data-ttu-id="952c4-168">Вот еще один пример.</span><span class="sxs-lookup"><span data-stu-id="952c4-168">Here is another example.</span></span> <span data-ttu-id="952c4-169">Функция **шоваргс** выводит переданные ей значения.</span><span class="sxs-lookup"><span data-stu-id="952c4-169">The **showArgs** function outputs the values passed to it.</span></span> <span data-ttu-id="952c4-170">В этом примере мы передаем переменную с именем `$HOME` в функцию дважды.</span><span class="sxs-lookup"><span data-stu-id="952c4-170">In this example, we pass the variable named `$HOME` to the function twice.</span></span>

```powershell
function showArgs {
  "`$args = " + ($args -join '|')
}

showArgs $HOME --% $HOME
```

В выходных данных можно увидеть, что для первого параметра Переменная `$HOME` интерпретируется PowerShell, чтобы значение переменной передавалось функции. <span data-ttu-id="952c4-172">Второе использование `$HOME` поступает после маркера-синтаксического анализа, поэтому строка "$Home" передается в функцию без интерпретации.</span><span class="sxs-lookup"><span data-stu-id="952c4-172">The second use of `$HOME` comes after the stop-parsing token, so the string "$HOME" is passed to the function without interpretation.</span></span>

```Output
$args = C:\Users\username|--%|$HOME
```

<span data-ttu-id="952c4-173">Дополнительные сведения о токене завершения синтаксического анализа см. в разделе [about_Parsing](about_Parsing.md).</span><span class="sxs-lookup"><span data-stu-id="952c4-173">For more information about the stop-parsing token, see [about_Parsing](about_Parsing.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="952c4-174">См. также статью</span><span class="sxs-lookup"><span data-stu-id="952c4-174">See also</span></span>

[<span data-ttu-id="952c4-175">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="952c4-175">about_Quoting_Rules</span></span>](about_Quoting_Rules.md)
