---
description: PSReadLine предоставляет улучшенные возможности редактирования командной строки в консоли PowerShell.
keywords: powershell
Locale: en-US
ms.date: 02/10/2020
online version: https://docs.microsoft.com/powershell/module/psreadline/about/about_psreadline?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: О PSReadLine
ms.openlocfilehash: ad6e85a30f866cb332c89a4c36f42231f511f5ae
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2020
ms.locfileid: "93233125"
---
# <a name="psreadline"></a><span data-ttu-id="cc43d-104">PSReadLine</span><span class="sxs-lookup"><span data-stu-id="cc43d-104">PSReadLine</span></span>

## <a name="about_psreadline"></a><span data-ttu-id="cc43d-105">about_PSReadLine</span><span class="sxs-lookup"><span data-stu-id="cc43d-105">about_PSReadLine</span></span>

## <a name="short-description"></a><span data-ttu-id="cc43d-106">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="cc43d-106">SHORT DESCRIPTION</span></span>

<span data-ttu-id="cc43d-107">PSReadLine предоставляет улучшенные возможности редактирования командной строки в консоли PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cc43d-107">PSReadLine provides an improved command-line editing experience in the PowerShell console.</span></span>

## <a name="long-description"></a><span data-ttu-id="cc43d-108">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="cc43d-108">LONG DESCRIPTION</span></span>

<span data-ttu-id="cc43d-109">PSReadLine 2,0 предоставляет широкие возможности редактирования командной строки для консоли PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cc43d-109">PSReadLine 2.0 provides a powerful command-line editing experience for the PowerShell console.</span></span> <span data-ttu-id="cc43d-110">Консоль предоставляет следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="cc43d-110">It provides:</span></span>

- <span data-ttu-id="cc43d-111">Цветовое выделение синтаксиса командной строки</span><span class="sxs-lookup"><span data-stu-id="cc43d-111">Syntax coloring of the command line</span></span>
- <span data-ttu-id="cc43d-112">Визуальное обозначение синтаксических ошибок</span><span class="sxs-lookup"><span data-stu-id="cc43d-112">A visual indication of syntax errors</span></span>
- <span data-ttu-id="cc43d-113">Более эффективный многострочный интерфейс (как редактирование, так и журнал)</span><span class="sxs-lookup"><span data-stu-id="cc43d-113">A better multi-line experience (both editing and history)</span></span>
- <span data-ttu-id="cc43d-114">Настраиваемые сочетания клавиш</span><span class="sxs-lookup"><span data-stu-id="cc43d-114">Customizable key bindings</span></span>
- <span data-ttu-id="cc43d-115">Режимы работы cmd и Emacs</span><span class="sxs-lookup"><span data-stu-id="cc43d-115">Cmd and Emacs modes</span></span>
- <span data-ttu-id="cc43d-116">Множество параметров конфигурации</span><span class="sxs-lookup"><span data-stu-id="cc43d-116">Many configuration options</span></span>
- <span data-ttu-id="cc43d-117">Завершение стиля bash (необязательно в режиме cmd, по умолчанию в режиме Emacs)</span><span class="sxs-lookup"><span data-stu-id="cc43d-117">Bash style completion (optional in Cmd mode, default in Emacs mode)</span></span>
- <span data-ttu-id="cc43d-118">Emacs: Янк/Kill-Ring</span><span class="sxs-lookup"><span data-stu-id="cc43d-118">Emacs yank/kill-ring</span></span>
- <span data-ttu-id="cc43d-119">Перемещение и уничтожение токена PowerShell на основе маркеров "Word"</span><span class="sxs-lookup"><span data-stu-id="cc43d-119">PowerShell token based "word" movement and kill</span></span>

<span data-ttu-id="cc43d-120">В классе **[Microsoft. PowerShell. псконсолереадлине]** доступны следующие функции.</span><span class="sxs-lookup"><span data-stu-id="cc43d-120">The following functions are available in the class **[Microsoft.PowerShell.PSConsoleReadLine]** .</span></span>

## <a name="basic-editing-functions"></a><span data-ttu-id="cc43d-121">Базовые функции редактирования</span><span class="sxs-lookup"><span data-stu-id="cc43d-121">Basic editing functions</span></span>

### <a name="abort"></a><span data-ttu-id="cc43d-122">Прерывание</span><span class="sxs-lookup"><span data-stu-id="cc43d-122">Abort</span></span>

<span data-ttu-id="cc43d-123">Прервать текущее действие, например добавочный поиск по журналу.</span><span class="sxs-lookup"><span data-stu-id="cc43d-123">Abort current action, e.g. incremental history search.</span></span>

- <span data-ttu-id="cc43d-124">Emacs: `<Ctrl+g>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-124">Emacs: `<Ctrl+g>`</span></span>

### <a name="acceptandgetnext"></a><span data-ttu-id="cc43d-125">акцептанджетнекст</span><span class="sxs-lookup"><span data-stu-id="cc43d-125">AcceptAndGetNext</span></span>

<span data-ttu-id="cc43d-126">Попытка выполнить текущий вход.</span><span class="sxs-lookup"><span data-stu-id="cc43d-126">Attempt to execute the current input.</span></span> <span data-ttu-id="cc43d-127">Если его можно выполнить (например, Акцептлине), то следует отозвать следующий элемент из журнала при следующем вызове метода ReadLine.</span><span class="sxs-lookup"><span data-stu-id="cc43d-127">If it can be executed (like AcceptLine), then recall the next item from history the next time ReadLine is called.</span></span>

- <span data-ttu-id="cc43d-128">Emacs: `<Ctrl+o>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-128">Emacs: `<Ctrl+o>`</span></span>

### <a name="acceptline"></a><span data-ttu-id="cc43d-129">акцептлине</span><span class="sxs-lookup"><span data-stu-id="cc43d-129">AcceptLine</span></span>

<span data-ttu-id="cc43d-130">Попытка выполнить текущий вход.</span><span class="sxs-lookup"><span data-stu-id="cc43d-130">Attempt to execute the current input.</span></span> <span data-ttu-id="cc43d-131">Если текущий ввод неполон (например, отсутствует закрывающая круглая скобка, квадратная скобка или кавычка, запрос продолжения отображается на следующей строке, а PSReadLine ожидает ввода ключей для изменения текущих входных данных.</span><span class="sxs-lookup"><span data-stu-id="cc43d-131">If the current input is incomplete (for example there is a missing closing parenthesis, bracket, or quote, then the continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span>

- <span data-ttu-id="cc43d-132">Процессор `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-132">Cmd: `<Enter>`</span></span>
- <span data-ttu-id="cc43d-133">Emacs: `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-133">Emacs: `<Enter>`</span></span>
- <span data-ttu-id="cc43d-134">Режим вставки в VI: `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-134">Vi insert mode: `<Enter>`</span></span>

### <a name="addline"></a><span data-ttu-id="cc43d-135">аддлине</span><span class="sxs-lookup"><span data-stu-id="cc43d-135">AddLine</span></span>

<span data-ttu-id="cc43d-136">Запрос продолжения отображается на следующей строке, а PSReadLine ожидает ввода ключей для изменения текущих входных данных.</span><span class="sxs-lookup"><span data-stu-id="cc43d-136">The continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span> <span data-ttu-id="cc43d-137">Это полезно для ввода многострочных входных данных в виде одной команды, даже если одна строка завершается самим вводом.</span><span class="sxs-lookup"><span data-stu-id="cc43d-137">This is useful to enter multi-line input as a single command even when a single line is complete input by itself.</span></span>

- <span data-ttu-id="cc43d-138">Процессор `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-138">Cmd: `<Shift+Enter>`</span></span>
- <span data-ttu-id="cc43d-139">Emacs: `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-139">Emacs: `<Shift+Enter>`</span></span>
- <span data-ttu-id="cc43d-140">Режим вставки в VI: `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-140">Vi insert mode: `<Shift+Enter>`</span></span>
- <span data-ttu-id="cc43d-141">Режим команд VI: `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-141">Vi command mode: `<Shift+Enter>`</span></span>

### <a name="backwarddeletechar"></a><span data-ttu-id="cc43d-142">бакквардделетечар</span><span class="sxs-lookup"><span data-stu-id="cc43d-142">BackwardDeleteChar</span></span>

<span data-ttu-id="cc43d-143">Удалить символ перед курсором.</span><span class="sxs-lookup"><span data-stu-id="cc43d-143">Delete the character before the cursor.</span></span>

- <span data-ttu-id="cc43d-144">Cmd: `<Backspace>` , `<Ctrl+h>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-144">Cmd: `<Backspace>`, `<Ctrl+h>`</span></span>
- <span data-ttu-id="cc43d-145">Emacs: `<Backspace>` , `<Ctrl+Backspace>` , `<Ctrl+h>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-145">Emacs: `<Backspace>`, `<Ctrl+Backspace>`, `<Ctrl+h>`</span></span>
- <span data-ttu-id="cc43d-146">Режим вставки в VI: `<Backspace>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-146">Vi insert mode: `<Backspace>`</span></span>
- <span data-ttu-id="cc43d-147">Режим команд VI: `<X>` , `<d,h>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-147">Vi command mode: `<X>`, `<d,h>`</span></span>

### <a name="backwarddeleteline"></a><span data-ttu-id="cc43d-148">бакквардделетелине</span><span class="sxs-lookup"><span data-stu-id="cc43d-148">BackwardDeleteLine</span></span>

<span data-ttu-id="cc43d-149">Like Бакквардкилллине — удаляет текст с точки до начала строки, но не помещает удаленный текст в инструкцию KILL-Ring.</span><span class="sxs-lookup"><span data-stu-id="cc43d-149">Like BackwardKillLine - deletes text from the point to the start of the line, but does not put the deleted text in the kill-ring.</span></span>

- <span data-ttu-id="cc43d-150">Процессор `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-150">Cmd: `<Ctrl+Home>`</span></span>
- <span data-ttu-id="cc43d-151">Режим вставки в VI: `<Ctrl+u>` , `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-151">Vi insert mode: `<Ctrl+u>`, `<Ctrl+Home>`</span></span>
- <span data-ttu-id="cc43d-152">Режим команд VI: `<Ctrl+u>` , `<Ctrl+Home>` , `<d,0>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-152">Vi command mode: `<Ctrl+u>`, `<Ctrl+Home>`, `<d,0>`</span></span>

### <a name="backwarddeleteword"></a><span data-ttu-id="cc43d-153">бакквардделетеворд</span><span class="sxs-lookup"><span data-stu-id="cc43d-153">BackwardDeleteWord</span></span>

<span data-ttu-id="cc43d-154">Удаляет предыдущее слово.</span><span class="sxs-lookup"><span data-stu-id="cc43d-154">Deletes the previous word.</span></span>

- <span data-ttu-id="cc43d-155">Режим команд VI: `<Ctrl+w>` , `<d,b>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-155">Vi command mode: `<Ctrl+w>`, `<d,b>`</span></span>

### <a name="backwardkillline"></a><span data-ttu-id="cc43d-156">бакквардкилллине</span><span class="sxs-lookup"><span data-stu-id="cc43d-156">BackwardKillLine</span></span>

<span data-ttu-id="cc43d-157">Очистить входные данные от начала ввода до курсора.</span><span class="sxs-lookup"><span data-stu-id="cc43d-157">Clear the input from the start of the input to the cursor.</span></span> <span data-ttu-id="cc43d-158">Очистка текста помещается в буфер Kill.</span><span class="sxs-lookup"><span data-stu-id="cc43d-158">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="cc43d-159">Emacs: `<Ctrl+u>` , `<Ctrl+x,Backspace>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-159">Emacs: `<Ctrl+u>`, `<Ctrl+x,Backspace>`</span></span>

### <a name="backwardkillword"></a><span data-ttu-id="cc43d-160">бакквардкиллворд</span><span class="sxs-lookup"><span data-stu-id="cc43d-160">BackwardKillWord</span></span>

<span data-ttu-id="cc43d-161">Очистить ввод от начала текущего слова до курсора.</span><span class="sxs-lookup"><span data-stu-id="cc43d-161">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="cc43d-162">Если курсор находится между словами, входные данные очищаются от начала предыдущего слова до курсора.</span><span class="sxs-lookup"><span data-stu-id="cc43d-162">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="cc43d-163">Очистка текста помещается в буфер Kill.</span><span class="sxs-lookup"><span data-stu-id="cc43d-163">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="cc43d-164">Процессор `<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-164">Cmd: `<Ctrl+Backspace>`</span></span>
- <span data-ttu-id="cc43d-165">Emacs: `<Alt+Backspace>` , `<Escape,Backspace>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-165">Emacs: `<Alt+Backspace>`, `<Escape,Backspace>`</span></span>
- <span data-ttu-id="cc43d-166">Режим вставки в VI: `<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-166">Vi insert mode: `<Ctrl+Backspace>`</span></span>
- <span data-ttu-id="cc43d-167">Режим команд VI: `<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-167">Vi command mode: `<Ctrl+Backspace>`</span></span>

### <a name="cancelline"></a><span data-ttu-id="cc43d-168">канцеллине</span><span class="sxs-lookup"><span data-stu-id="cc43d-168">CancelLine</span></span>

<span data-ttu-id="cc43d-169">Отмена текущих входных данных с выходом на экран, но возврат к узлу, чтобы снова выполнить оценку запроса.</span><span class="sxs-lookup"><span data-stu-id="cc43d-169">Cancel the current input, leaving the input on the screen, but returns back to the host so the prompt is evaluated again.</span></span>

- <span data-ttu-id="cc43d-170">Режим вставки в VI: `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-170">Vi insert mode: `<Ctrl+c>`</span></span>
- <span data-ttu-id="cc43d-171">Режим команд VI: `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-171">Vi command mode: `<Ctrl+c>`</span></span>

### <a name="copy"></a><span data-ttu-id="cc43d-172">Копировать</span><span class="sxs-lookup"><span data-stu-id="cc43d-172">Copy</span></span>

<span data-ttu-id="cc43d-173">Копировать выбранный регион в буфер обмена системы.</span><span class="sxs-lookup"><span data-stu-id="cc43d-173">Copy selected region to the system clipboard.</span></span> <span data-ttu-id="cc43d-174">Если регион не выбран, скопируйте всю строку.</span><span class="sxs-lookup"><span data-stu-id="cc43d-174">If no region is selected, copy the whole line.</span></span>

- <span data-ttu-id="cc43d-175">Процессор `<Ctrl+C>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-175">Cmd: `<Ctrl+C>`</span></span>

### <a name="copyorcancelline"></a><span data-ttu-id="cc43d-176">копйорканцеллине</span><span class="sxs-lookup"><span data-stu-id="cc43d-176">CopyOrCancelLine</span></span>

<span data-ttu-id="cc43d-177">Если выбран текст, скопируйте в буфер обмена, в противном случае отмените строку.</span><span class="sxs-lookup"><span data-stu-id="cc43d-177">If text is selected, copy to the clipboard, otherwise cancel the line.</span></span>

- <span data-ttu-id="cc43d-178">Процессор `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-178">Cmd: `<Ctrl+c>`</span></span>
- <span data-ttu-id="cc43d-179">Emacs: `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-179">Emacs: `<Ctrl+c>`</span></span>

### <a name="cut"></a><span data-ttu-id="cc43d-180">Вырезать</span><span class="sxs-lookup"><span data-stu-id="cc43d-180">Cut</span></span>

<span data-ttu-id="cc43d-181">Удалить выбранный регион, поместив удаленный текст в системный буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="cc43d-181">Delete selected region placing deleted text in the system clipboard.</span></span>

- <span data-ttu-id="cc43d-182">Процессор `<Ctrl+x>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-182">Cmd: `<Ctrl+x>`</span></span>

### <a name="deletechar"></a><span data-ttu-id="cc43d-183">делетечар</span><span class="sxs-lookup"><span data-stu-id="cc43d-183">DeleteChar</span></span>

<span data-ttu-id="cc43d-184">Удалите символ под курсором.</span><span class="sxs-lookup"><span data-stu-id="cc43d-184">Delete the character under the cursor.</span></span>

- <span data-ttu-id="cc43d-185">Процессор `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-185">Cmd: `<Delete>`</span></span>
- <span data-ttu-id="cc43d-186">Emacs: `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-186">Emacs: `<Delete>`</span></span>
- <span data-ttu-id="cc43d-187">Режим вставки в VI: `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-187">Vi insert mode: `<Delete>`</span></span>
- <span data-ttu-id="cc43d-188">Режим команд VI: `<Delete>` , `<x>` , `<d,l>` , `<d,Space>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-188">Vi command mode: `<Delete>`, `<x>`, `<d,l>`, `<d,Space>`</span></span>

### <a name="deletecharorexit"></a><span data-ttu-id="cc43d-189">делетечарорексит</span><span class="sxs-lookup"><span data-stu-id="cc43d-189">DeleteCharOrExit</span></span>

<span data-ttu-id="cc43d-190">Удалите символ под курсором или, если строка пуста, завершите процесс.</span><span class="sxs-lookup"><span data-stu-id="cc43d-190">Delete the character under the cursor, or if the line is empty, exit the process.</span></span>

- <span data-ttu-id="cc43d-191">Emacs: `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-191">Emacs: `<Ctrl+d>`</span></span>

### <a name="deleteendofword"></a><span data-ttu-id="cc43d-192">делетиндофворд</span><span class="sxs-lookup"><span data-stu-id="cc43d-192">DeleteEndOfWord</span></span>

<span data-ttu-id="cc43d-193">Удалить до конца слова.</span><span class="sxs-lookup"><span data-stu-id="cc43d-193">Delete to the end of the word.</span></span>

- <span data-ttu-id="cc43d-194">Режим команд VI: `<d,e>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-194">Vi command mode: `<d,e>`</span></span>

### <a name="deleteline"></a><span data-ttu-id="cc43d-195">Сбой deleteline</span><span class="sxs-lookup"><span data-stu-id="cc43d-195">DeleteLine</span></span>

<span data-ttu-id="cc43d-196">Удаляет текущую строку, включая отмену.</span><span class="sxs-lookup"><span data-stu-id="cc43d-196">Deletes the current line, enabling undo.</span></span>

- <span data-ttu-id="cc43d-197">Режим команд VI: `<d,d>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-197">Vi command mode: `<d,d>`</span></span>

### <a name="deletelinetofirstchar"></a><span data-ttu-id="cc43d-198">делетелинетофирстчар</span><span class="sxs-lookup"><span data-stu-id="cc43d-198">DeleteLineToFirstChar</span></span>

<span data-ttu-id="cc43d-199">Удаляет текст из курсора на первый символ строки, отличный от пробела.</span><span class="sxs-lookup"><span data-stu-id="cc43d-199">Deletes text from the cursor to the first non-blank character of the line.</span></span>

- <span data-ttu-id="cc43d-200">Режим команд VI: `<d,^>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-200">Vi command mode: `<d,^>`</span></span>

### <a name="deletetoend"></a><span data-ttu-id="cc43d-201">делететоенд</span><span class="sxs-lookup"><span data-stu-id="cc43d-201">DeleteToEnd</span></span>

<span data-ttu-id="cc43d-202">Удалить до конца строки.</span><span class="sxs-lookup"><span data-stu-id="cc43d-202">Delete to the end of the line.</span></span>

- <span data-ttu-id="cc43d-203">Режим команд VI: `<D>` , `<d,$>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-203">Vi command mode: `<D>`, `<d,$>`</span></span>

### <a name="deleteword"></a><span data-ttu-id="cc43d-204">DeleteWord</span><span class="sxs-lookup"><span data-stu-id="cc43d-204">DeleteWord</span></span>

<span data-ttu-id="cc43d-205">Удалить следующее слово.</span><span class="sxs-lookup"><span data-stu-id="cc43d-205">Delete the next word.</span></span>

- <span data-ttu-id="cc43d-206">Режим команд VI: `<d,w>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-206">Vi command mode: `<d,w>`</span></span>

### <a name="forwarddeleteline"></a><span data-ttu-id="cc43d-207">форвардделетелине</span><span class="sxs-lookup"><span data-stu-id="cc43d-207">ForwardDeleteLine</span></span>

<span data-ttu-id="cc43d-208">Как и Форвардкилллине — удаляет текст с точки до конца строки, но не помещает удаленный текст в инструкцию KILL-Ring.</span><span class="sxs-lookup"><span data-stu-id="cc43d-208">Like ForwardKillLine - deletes text from the point to the end of the line, but does not put the deleted text in the kill-ring.</span></span>

- <span data-ttu-id="cc43d-209">Процессор `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-209">Cmd: `<Ctrl+End>`</span></span>
- <span data-ttu-id="cc43d-210">Режим вставки в VI: `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-210">Vi insert mode: `<Ctrl+End>`</span></span>
- <span data-ttu-id="cc43d-211">Режим команд VI: `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-211">Vi command mode: `<Ctrl+End>`</span></span>

### <a name="insertlineabove"></a><span data-ttu-id="cc43d-212">инсертлинеабове</span><span class="sxs-lookup"><span data-stu-id="cc43d-212">InsertLineAbove</span></span>

<span data-ttu-id="cc43d-213">Новая пустая строка создается над текущей строкой, независимо от того, где находится курсор на текущей строке.</span><span class="sxs-lookup"><span data-stu-id="cc43d-213">A new empty line is created above the current line regardless of where the cursor is on the current line.</span></span> <span data-ttu-id="cc43d-214">Курсор переместится в начало новой строки.</span><span class="sxs-lookup"><span data-stu-id="cc43d-214">The cursor moves to the beginning of the new line.</span></span>

- <span data-ttu-id="cc43d-215">Процессор `<Ctrl+Enter>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-215">Cmd: `<Ctrl+Enter>`</span></span>

### <a name="insertlinebelow"></a><span data-ttu-id="cc43d-216">инсертлинебелов</span><span class="sxs-lookup"><span data-stu-id="cc43d-216">InsertLineBelow</span></span>

<span data-ttu-id="cc43d-217">Новая пустая строка создается под текущей строкой независимо от того, где находится курсор на текущей строке.</span><span class="sxs-lookup"><span data-stu-id="cc43d-217">A new empty line is created below the current line regardless of where the cursor is on the current line.</span></span> <span data-ttu-id="cc43d-218">Курсор переместится в начало новой строки.</span><span class="sxs-lookup"><span data-stu-id="cc43d-218">The cursor moves to the beginning of the new line.</span></span>

- <span data-ttu-id="cc43d-219">Процессор `<Shift+Ctrl+Enter>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-219">Cmd: `<Shift+Ctrl+Enter>`</span></span>

### <a name="invertcase"></a><span data-ttu-id="cc43d-220">инверткасе</span><span class="sxs-lookup"><span data-stu-id="cc43d-220">InvertCase</span></span>

<span data-ttu-id="cc43d-221">Инвертировать регистр текущего символа и перейти к следующему.</span><span class="sxs-lookup"><span data-stu-id="cc43d-221">Invert the case of the current character and move to the next one.</span></span>

- <span data-ttu-id="cc43d-222">Режим команд VI: `<~>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-222">Vi command mode: `<~>`</span></span>

### <a name="killline"></a><span data-ttu-id="cc43d-223">килллине</span><span class="sxs-lookup"><span data-stu-id="cc43d-223">KillLine</span></span>

<span data-ttu-id="cc43d-224">Очистить входные данные от курсора до конца входных данных.</span><span class="sxs-lookup"><span data-stu-id="cc43d-224">Clear the input from the cursor to the end of the input.</span></span> <span data-ttu-id="cc43d-225">Очистка текста помещается в буфер Kill.</span><span class="sxs-lookup"><span data-stu-id="cc43d-225">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="cc43d-226">Emacs: `<Ctrl+k>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-226">Emacs: `<Ctrl+k>`</span></span>

### <a name="killregion"></a><span data-ttu-id="cc43d-227">киллрегион</span><span class="sxs-lookup"><span data-stu-id="cc43d-227">KillRegion</span></span>

<span data-ttu-id="cc43d-228">Удалить текст между курсором и меткой.</span><span class="sxs-lookup"><span data-stu-id="cc43d-228">Kill the text between the cursor and the mark.</span></span>

- <span data-ttu-id="cc43d-229">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="cc43d-229">Function is unbound.</span></span>

### <a name="killword"></a><span data-ttu-id="cc43d-230">киллворд</span><span class="sxs-lookup"><span data-stu-id="cc43d-230">KillWord</span></span>

<span data-ttu-id="cc43d-231">Очистить ввод от курсора до конца текущего слова.</span><span class="sxs-lookup"><span data-stu-id="cc43d-231">Clear the input from the cursor to the end of the current word.</span></span> <span data-ttu-id="cc43d-232">Если курсор находится между словами, входные данные очищаются от курсора до конца следующего слова.</span><span class="sxs-lookup"><span data-stu-id="cc43d-232">If the cursor is between words, the input is cleared from the cursor to the end of the next word.</span></span> <span data-ttu-id="cc43d-233">Очистка текста помещается в буфер Kill.</span><span class="sxs-lookup"><span data-stu-id="cc43d-233">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="cc43d-234">Процессор `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-234">Cmd: `<Ctrl+Delete>`</span></span>
- <span data-ttu-id="cc43d-235">Emacs: `<Alt+d>` , `<Escape,d>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-235">Emacs: `<Alt+d>`, `<Escape,d>`</span></span>
- <span data-ttu-id="cc43d-236">Режим вставки в VI: `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-236">Vi insert mode: `<Ctrl+Delete>`</span></span>
- <span data-ttu-id="cc43d-237">Режим команд VI: `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-237">Vi command mode: `<Ctrl+Delete>`</span></span>

### <a name="paste"></a><span data-ttu-id="cc43d-238">Вставить</span><span class="sxs-lookup"><span data-stu-id="cc43d-238">Paste</span></span>

<span data-ttu-id="cc43d-239">Вставка текста из буфера обмена системы.</span><span class="sxs-lookup"><span data-stu-id="cc43d-239">Paste text from the system clipboard.</span></span>

- <span data-ttu-id="cc43d-240">Cmd: `<Ctrl+v>` , `<Shift+Insert>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-240">Cmd: `<Ctrl+v>`, `<Shift+Insert>`</span></span>
- <span data-ttu-id="cc43d-241">Режим вставки в VI: `<Ctrl+v>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-241">Vi insert mode: `<Ctrl+v>`</span></span>
- <span data-ttu-id="cc43d-242">Режим команд VI: `<Ctrl+v>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-242">Vi command mode: `<Ctrl+v>`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cc43d-243">При использовании функции **вставки** все содержимое буфера буфера обмена вставляется во входной буфер PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="cc43d-243">When using the **Paste** function, the entire contents of the clipboard buffer is pasted into the input buffer of PSReadLine.</span></span> <span data-ttu-id="cc43d-244">Затем входной буфер передается средству синтаксического анализа PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cc43d-244">The input buffer is then passed to the PowerShell parser.</span></span> <span data-ttu-id="cc43d-245">Вход, вставленный с помощью консольного приложения, щелкните **правой кнопкой мыши** метод вставки, скопированный во входной буфер по одному символу за раз.</span><span class="sxs-lookup"><span data-stu-id="cc43d-245">Input pasted using the console application's **right-click** paste method is copied to the input buffer one character at a time.</span></span> <span data-ttu-id="cc43d-246">Входной буфер передается средству синтаксического анализа при копировании символа новой строки.</span><span class="sxs-lookup"><span data-stu-id="cc43d-246">The input buffer is passed to the parser when a newline character is copied.</span></span> <span data-ttu-id="cc43d-247">Поэтому входные данные анализируются по одной строке за раз.</span><span class="sxs-lookup"><span data-stu-id="cc43d-247">Therefore, the input is parsed one line at a time.</span></span> <span data-ttu-id="cc43d-248">Различие между методами вставки приводит к различному поведению при выполнении.</span><span class="sxs-lookup"><span data-stu-id="cc43d-248">The difference between paste methods results in different execution behavior.</span></span>

### <a name="pasteafter"></a><span data-ttu-id="cc43d-249">пастеафтер</span><span class="sxs-lookup"><span data-stu-id="cc43d-249">PasteAfter</span></span>

<span data-ttu-id="cc43d-250">Вставьте буфер обмена после курсора, переместив курсор в конец вставленного текста.</span><span class="sxs-lookup"><span data-stu-id="cc43d-250">Paste the clipboard after the cursor, moving the cursor to the end of the pasted text.</span></span>

- <span data-ttu-id="cc43d-251">Режим команд VI: `<p>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-251">Vi command mode: `<p>`</span></span>

### <a name="pastebefore"></a><span data-ttu-id="cc43d-252">пастебефоре</span><span class="sxs-lookup"><span data-stu-id="cc43d-252">PasteBefore</span></span>

<span data-ttu-id="cc43d-253">Вставьте буфер обмена перед курсором, переместив курсор в конец вставленного текста.</span><span class="sxs-lookup"><span data-stu-id="cc43d-253">Paste the clipboard before the cursor, moving the cursor to the end of the pasted text.</span></span>

- <span data-ttu-id="cc43d-254">Режим команд VI: `<P>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-254">Vi command mode: `<P>`</span></span>

### <a name="prependandaccept"></a><span data-ttu-id="cc43d-255">препендандакцепт</span><span class="sxs-lookup"><span data-stu-id="cc43d-255">PrependAndAccept</span></span>

<span data-ttu-id="cc43d-256">Добавьте в начало "#" и примите строку.</span><span class="sxs-lookup"><span data-stu-id="cc43d-256">Prepend a '#' and accept the line.</span></span>

- <span data-ttu-id="cc43d-257">Режим команд VI: `<#>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-257">Vi command mode: `<#>`</span></span>

### <a name="redo"></a><span data-ttu-id="cc43d-258">Повторить</span><span class="sxs-lookup"><span data-stu-id="cc43d-258">Redo</span></span>

<span data-ttu-id="cc43d-259">Отмена отмены.</span><span class="sxs-lookup"><span data-stu-id="cc43d-259">Undo an undo.</span></span>

- <span data-ttu-id="cc43d-260">Процессор `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-260">Cmd: `<Ctrl+y>`</span></span>
- <span data-ttu-id="cc43d-261">Режим вставки в VI: `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-261">Vi insert mode: `<Ctrl+y>`</span></span>
- <span data-ttu-id="cc43d-262">Режим команд VI: `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-262">Vi command mode: `<Ctrl+y>`</span></span>

### <a name="repeatlastcommand"></a><span data-ttu-id="cc43d-263">репеатласткомманд</span><span class="sxs-lookup"><span data-stu-id="cc43d-263">RepeatLastCommand</span></span>

<span data-ttu-id="cc43d-264">Повторите Последнее изменение текста.</span><span class="sxs-lookup"><span data-stu-id="cc43d-264">Repeat the last text modification.</span></span>

- <span data-ttu-id="cc43d-265">Режим команд VI: `<.>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-265">Vi command mode: `<.>`</span></span>

### <a name="revertline"></a><span data-ttu-id="cc43d-266">ревертлине</span><span class="sxs-lookup"><span data-stu-id="cc43d-266">RevertLine</span></span>

<span data-ttu-id="cc43d-267">Меняет все входные данные на текущие входные данные.</span><span class="sxs-lookup"><span data-stu-id="cc43d-267">Reverts all of the input to the current input.</span></span>

- <span data-ttu-id="cc43d-268">Процессор `<Escape>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-268">Cmd: `<Escape>`</span></span>
- <span data-ttu-id="cc43d-269">Emacs: `<Alt+r>` , `<Escape,r>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-269">Emacs: `<Alt+r>`, `<Escape,r>`</span></span>

### <a name="shellbackwardkillword"></a><span data-ttu-id="cc43d-270">шеллбакквардкиллворд</span><span class="sxs-lookup"><span data-stu-id="cc43d-270">ShellBackwardKillWord</span></span>

<span data-ttu-id="cc43d-271">Очистить ввод от начала текущего слова до курсора.</span><span class="sxs-lookup"><span data-stu-id="cc43d-271">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="cc43d-272">Если курсор находится между словами, входные данные очищаются от начала предыдущего слова до курсора.</span><span class="sxs-lookup"><span data-stu-id="cc43d-272">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="cc43d-273">Очистка текста помещается в буфер Kill.</span><span class="sxs-lookup"><span data-stu-id="cc43d-273">The cleared text is placed in the kill-ring.</span></span>

<span data-ttu-id="cc43d-274">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="cc43d-274">Function is unbound.</span></span>

### <a name="shellkillword"></a><span data-ttu-id="cc43d-275">шеллкиллворд</span><span class="sxs-lookup"><span data-stu-id="cc43d-275">ShellKillWord</span></span>

<span data-ttu-id="cc43d-276">Очистить ввод от курсора до конца текущего слова.</span><span class="sxs-lookup"><span data-stu-id="cc43d-276">Clear the input from the cursor to the end of the current word.</span></span> <span data-ttu-id="cc43d-277">Если курсор находится между словами, входные данные очищаются от курсора до конца следующего слова.</span><span class="sxs-lookup"><span data-stu-id="cc43d-277">If the cursor is between words, the input is cleared from the cursor to the end of the next word.</span></span> <span data-ttu-id="cc43d-278">Очистка текста помещается в буфер Kill.</span><span class="sxs-lookup"><span data-stu-id="cc43d-278">The cleared text is placed in the kill-ring.</span></span>

<span data-ttu-id="cc43d-279">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="cc43d-279">Function is unbound.</span></span>

### <a name="swapcharacters"></a><span data-ttu-id="cc43d-280">свапчарактерс</span><span class="sxs-lookup"><span data-stu-id="cc43d-280">SwapCharacters</span></span>

<span data-ttu-id="cc43d-281">Поменять местами текущий и тот же символ.</span><span class="sxs-lookup"><span data-stu-id="cc43d-281">Swap the current character and the one before it.</span></span>

- <span data-ttu-id="cc43d-282">Emacs: `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-282">Emacs: `<Ctrl+t>`</span></span>
- <span data-ttu-id="cc43d-283">Режим вставки в VI: `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-283">Vi insert mode: `<Ctrl+t>`</span></span>
- <span data-ttu-id="cc43d-284">Режим команд VI: `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-284">Vi command mode: `<Ctrl+t>`</span></span>

### <a name="undo"></a><span data-ttu-id="cc43d-285">Отменить</span><span class="sxs-lookup"><span data-stu-id="cc43d-285">Undo</span></span>

<span data-ttu-id="cc43d-286">Отмена предыдущего изменения.</span><span class="sxs-lookup"><span data-stu-id="cc43d-286">Undo a previous edit.</span></span>

- <span data-ttu-id="cc43d-287">Процессор `<Ctrl+z>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-287">Cmd: `<Ctrl+z>`</span></span>
- <span data-ttu-id="cc43d-288">Emacs: `<Ctrl+_>` , `<Ctrl+x,Ctrl+u>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-288">Emacs: `<Ctrl+_>`, `<Ctrl+x,Ctrl+u>`</span></span>
- <span data-ttu-id="cc43d-289">Режим вставки в VI: `<Ctrl+z>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-289">Vi insert mode: `<Ctrl+z>`</span></span>
- <span data-ttu-id="cc43d-290">Режим команд VI: `<Ctrl+z>` , `<u>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-290">Vi command mode: `<Ctrl+z>`, `<u>`</span></span>

### <a name="undoall"></a><span data-ttu-id="cc43d-291">ундоалл</span><span class="sxs-lookup"><span data-stu-id="cc43d-291">UndoAll</span></span>

<span data-ttu-id="cc43d-292">Отмена всех предыдущих изменений для строки.</span><span class="sxs-lookup"><span data-stu-id="cc43d-292">Undo all previous edits for line.</span></span>

- <span data-ttu-id="cc43d-293">Режим команд VI: `<U>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-293">Vi command mode: `<U>`</span></span>

### <a name="unixwordrubout"></a><span data-ttu-id="cc43d-294">униксвордрубаут</span><span class="sxs-lookup"><span data-stu-id="cc43d-294">UnixWordRubout</span></span>

<span data-ttu-id="cc43d-295">Очистить ввод от начала текущего слова до курсора.</span><span class="sxs-lookup"><span data-stu-id="cc43d-295">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="cc43d-296">Если курсор находится между словами, входные данные очищаются от начала предыдущего слова до курсора.</span><span class="sxs-lookup"><span data-stu-id="cc43d-296">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="cc43d-297">Очистка текста помещается в буфер Kill.</span><span class="sxs-lookup"><span data-stu-id="cc43d-297">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="cc43d-298">Emacs: `<Ctrl+w>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-298">Emacs: `<Ctrl+w>`</span></span>

### <a name="validateandacceptline"></a><span data-ttu-id="cc43d-299">валидатеандакцептлине</span><span class="sxs-lookup"><span data-stu-id="cc43d-299">ValidateAndAcceptLine</span></span>

<span data-ttu-id="cc43d-300">Попытка выполнить текущий вход.</span><span class="sxs-lookup"><span data-stu-id="cc43d-300">Attempt to execute the current input.</span></span> <span data-ttu-id="cc43d-301">Если текущий ввод неполон (например, отсутствует закрывающая круглая скобка, квадратная скобка или кавычка, запрос продолжения отображается на следующей строке, а PSReadLine ожидает ввода ключей для изменения текущих входных данных.</span><span class="sxs-lookup"><span data-stu-id="cc43d-301">If the current input is incomplete (for example there is a missing closing parenthesis, bracket, or quote, then the continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span>

- <span data-ttu-id="cc43d-302">Emacs: `<Ctrl+m>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-302">Emacs: `<Ctrl+m>`</span></span>

### <a name="viacceptline"></a><span data-ttu-id="cc43d-303">виакцептлине</span><span class="sxs-lookup"><span data-stu-id="cc43d-303">ViAcceptLine</span></span>

<span data-ttu-id="cc43d-304">Примите строку и переключитесь в режим вставки.</span><span class="sxs-lookup"><span data-stu-id="cc43d-304">Accept the line and switch to Insert mode.</span></span>

- <span data-ttu-id="cc43d-305">Режим команд VI: `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-305">Vi command mode: `<Enter>`</span></span>

### <a name="viacceptlineorexit"></a><span data-ttu-id="cc43d-306">виакцептлинеорексит</span><span class="sxs-lookup"><span data-stu-id="cc43d-306">ViAcceptLineOrExit</span></span>

<span data-ttu-id="cc43d-307">Как и Делетечарорексит в режиме Emacs, но принимает строку вместо удаления символа.</span><span class="sxs-lookup"><span data-stu-id="cc43d-307">Like DeleteCharOrExit in Emacs mode, but accepts the line instead of deleting a character.</span></span>

- <span data-ttu-id="cc43d-308">Режим вставки в VI: `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-308">Vi insert mode: `<Ctrl+d>`</span></span>
- <span data-ttu-id="cc43d-309">Режим команд VI: `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-309">Vi command mode: `<Ctrl+d>`</span></span>

### <a name="viappendline"></a><span data-ttu-id="cc43d-310">виаппендлине</span><span class="sxs-lookup"><span data-stu-id="cc43d-310">ViAppendLine</span></span>

<span data-ttu-id="cc43d-311">Новая строка вставляется под текущей строкой.</span><span class="sxs-lookup"><span data-stu-id="cc43d-311">A new line is inserted below the current line.</span></span>

- <span data-ttu-id="cc43d-312">Режим команд VI: `<o>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-312">Vi command mode: `<o>`</span></span>

### <a name="vibackwarddeleteglob"></a><span data-ttu-id="cc43d-313">вибакквардделетеглоб</span><span class="sxs-lookup"><span data-stu-id="cc43d-313">ViBackwardDeleteGlob</span></span>

<span data-ttu-id="cc43d-314">Удаляет предыдущее слово, используя только пробелы в качестве разделителя слов.</span><span class="sxs-lookup"><span data-stu-id="cc43d-314">Deletes the previous word, using only white space as the word delimiter.</span></span>

- <span data-ttu-id="cc43d-315">Режим команд VI: `<d,B>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-315">Vi command mode: `<d,B>`</span></span>

### <a name="vibackwardglob"></a><span data-ttu-id="cc43d-316">вибакквардглоб</span><span class="sxs-lookup"><span data-stu-id="cc43d-316">ViBackwardGlob</span></span>

<span data-ttu-id="cc43d-317">Перемещает курсор назад к началу предыдущего слова, используя только пробелы в качестве разделителей.</span><span class="sxs-lookup"><span data-stu-id="cc43d-317">Moves the cursor back to the beginning of the previous word, using only white space as delimiters.</span></span>

- <span data-ttu-id="cc43d-318">Режим команд VI: `<B>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-318">Vi command mode: `<B>`</span></span>

### <a name="videletebrace"></a><span data-ttu-id="cc43d-319">виделетебраце</span><span class="sxs-lookup"><span data-stu-id="cc43d-319">ViDeleteBrace</span></span>

<span data-ttu-id="cc43d-320">Найдите парную фигурную скобку, круглую скобку или квадратную скобку и удалите все содержимое внутри, включая фигурную скобку.</span><span class="sxs-lookup"><span data-stu-id="cc43d-320">Find the matching brace, parenthesis, or square bracket and delete all contents within, including the brace.</span></span>

- <span data-ttu-id="cc43d-321">Режим команд VI: `<d,%>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-321">Vi command mode: `<d,%>`</span></span>

### <a name="videleteendofglob"></a><span data-ttu-id="cc43d-322">виделетиндофглоб</span><span class="sxs-lookup"><span data-stu-id="cc43d-322">ViDeleteEndOfGlob</span></span>

<span data-ttu-id="cc43d-323">Удалить до конца слова.</span><span class="sxs-lookup"><span data-stu-id="cc43d-323">Delete to the end of the word.</span></span>

- <span data-ttu-id="cc43d-324">Режим команд VI: `<d,E>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-324">Vi command mode: `<d,E>`</span></span>

### <a name="videleteglob"></a><span data-ttu-id="cc43d-325">виделетеглоб</span><span class="sxs-lookup"><span data-stu-id="cc43d-325">ViDeleteGlob</span></span>

<span data-ttu-id="cc43d-326">Удалите следующий стандартная маска (слово, разделенное пробелами).</span><span class="sxs-lookup"><span data-stu-id="cc43d-326">Delete the next glob (white space delimited word).</span></span>

- <span data-ttu-id="cc43d-327">Режим команд VI: `<d,W>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-327">Vi command mode: `<d,W>`</span></span>

### <a name="videletetobeforechar"></a><span data-ttu-id="cc43d-328">виделететобефоречар</span><span class="sxs-lookup"><span data-stu-id="cc43d-328">ViDeleteToBeforeChar</span></span>

<span data-ttu-id="cc43d-329">Удаляет до заданного символа.</span><span class="sxs-lookup"><span data-stu-id="cc43d-329">Deletes until given character.</span></span>

- <span data-ttu-id="cc43d-330">Режим команд VI: `<d,t>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-330">Vi command mode: `<d,t>`</span></span>

### <a name="videletetobeforecharbackward"></a><span data-ttu-id="cc43d-331">виделететобефоречарбакквард</span><span class="sxs-lookup"><span data-stu-id="cc43d-331">ViDeleteToBeforeCharBackward</span></span>

<span data-ttu-id="cc43d-332">Удаляет до заданного символа.</span><span class="sxs-lookup"><span data-stu-id="cc43d-332">Deletes until given character.</span></span>

- <span data-ttu-id="cc43d-333">Режим команд VI: `<d,T>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-333">Vi command mode: `<d,T>`</span></span>

### <a name="videletetochar"></a><span data-ttu-id="cc43d-334">виделететочар</span><span class="sxs-lookup"><span data-stu-id="cc43d-334">ViDeleteToChar</span></span>

<span data-ttu-id="cc43d-335">Удаляет до заданного символа.</span><span class="sxs-lookup"><span data-stu-id="cc43d-335">Deletes until given character.</span></span>

- <span data-ttu-id="cc43d-336">Режим команд VI: `<d,f>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-336">Vi command mode: `<d,f>`</span></span>

### <a name="videletetocharbackward"></a><span data-ttu-id="cc43d-337">виделететочарбакквард</span><span class="sxs-lookup"><span data-stu-id="cc43d-337">ViDeleteToCharBackward</span></span>

<span data-ttu-id="cc43d-338">Удаляет обратную сторону до заданного символа.</span><span class="sxs-lookup"><span data-stu-id="cc43d-338">Deletes backwards until given character.</span></span>

- <span data-ttu-id="cc43d-339">Режим команд VI: `<d,F>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-339">Vi command mode: `<d,F>`</span></span>

### <a name="viinsertatbegining"></a><span data-ttu-id="cc43d-340">виинсертатбегининг</span><span class="sxs-lookup"><span data-stu-id="cc43d-340">ViInsertAtBegining</span></span>

<span data-ttu-id="cc43d-341">Переключитесь в режим вставки и поместите курсор в начало строки.</span><span class="sxs-lookup"><span data-stu-id="cc43d-341">Switch to Insert mode and position the cursor at the beginning of the line.</span></span>

- <span data-ttu-id="cc43d-342">Режим команд VI: `<I>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-342">Vi command mode: `<I>`</span></span>

### <a name="viinsertatend"></a><span data-ttu-id="cc43d-343">виинсертатенд</span><span class="sxs-lookup"><span data-stu-id="cc43d-343">ViInsertAtEnd</span></span>

<span data-ttu-id="cc43d-344">Переключитесь в режим вставки и поместите курсор в конец строки.</span><span class="sxs-lookup"><span data-stu-id="cc43d-344">Switch to Insert mode and position the cursor at the end of the line.</span></span>

- <span data-ttu-id="cc43d-345">Режим команд VI: `<A>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-345">Vi command mode: `<A>`</span></span>

### <a name="viinsertline"></a><span data-ttu-id="cc43d-346">виинсертлине</span><span class="sxs-lookup"><span data-stu-id="cc43d-346">ViInsertLine</span></span>

<span data-ttu-id="cc43d-347">Новая строка вставляется над текущей строкой.</span><span class="sxs-lookup"><span data-stu-id="cc43d-347">A new line is inserted above the current line.</span></span>

- <span data-ttu-id="cc43d-348">Режим команд VI: `<O>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-348">Vi command mode: `<O>`</span></span>

### <a name="viinsertwithappend"></a><span data-ttu-id="cc43d-349">виинсертвисаппенд</span><span class="sxs-lookup"><span data-stu-id="cc43d-349">ViInsertWithAppend</span></span>

<span data-ttu-id="cc43d-350">Добавление из текущей позицией строки.</span><span class="sxs-lookup"><span data-stu-id="cc43d-350">Append from the current line position.</span></span>

- <span data-ttu-id="cc43d-351">Режим команд VI: `<a>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-351">Vi command mode: `<a>`</span></span>

### <a name="viinsertwithdelete"></a><span data-ttu-id="cc43d-352">виинсертвисделете</span><span class="sxs-lookup"><span data-stu-id="cc43d-352">ViInsertWithDelete</span></span>

<span data-ttu-id="cc43d-353">Удалите текущий символ и переключитесь в режим вставки.</span><span class="sxs-lookup"><span data-stu-id="cc43d-353">Delete the current character and switch to Insert mode.</span></span>

- <span data-ttu-id="cc43d-354">Режим команд VI: `<s>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-354">Vi command mode: `<s>`</span></span>

### <a name="vijoinlines"></a><span data-ttu-id="cc43d-355">вижоинлинес</span><span class="sxs-lookup"><span data-stu-id="cc43d-355">ViJoinLines</span></span>

<span data-ttu-id="cc43d-356">Объединяет текущую строку и следующую строку.</span><span class="sxs-lookup"><span data-stu-id="cc43d-356">Joins the current line and the next line.</span></span>

- <span data-ttu-id="cc43d-357">Режим команд VI: `<J>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-357">Vi command mode: `<J>`</span></span>

### <a name="vireplaceline"></a><span data-ttu-id="cc43d-358">виреплацелине</span><span class="sxs-lookup"><span data-stu-id="cc43d-358">ViReplaceLine</span></span>

<span data-ttu-id="cc43d-359">Очистить всю командную строку.</span><span class="sxs-lookup"><span data-stu-id="cc43d-359">Erase the entire command line.</span></span>

- <span data-ttu-id="cc43d-360">Режим команд VI: `<S>` , `<c,c>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-360">Vi command mode: `<S>`, `<c,c>`</span></span>

### <a name="vireplacetobeforechar"></a><span data-ttu-id="cc43d-361">виреплацетобефоречар</span><span class="sxs-lookup"><span data-stu-id="cc43d-361">ViReplaceToBeforeChar</span></span>

<span data-ttu-id="cc43d-362">Заменяет заданный символ.</span><span class="sxs-lookup"><span data-stu-id="cc43d-362">Replaces until given character.</span></span>

- <span data-ttu-id="cc43d-363">Режим команд VI: `<c,t>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-363">Vi command mode: `<c,t>`</span></span>

### <a name="vireplacetobeforecharbackward"></a><span data-ttu-id="cc43d-364">виреплацетобефоречарбакквард</span><span class="sxs-lookup"><span data-stu-id="cc43d-364">ViReplaceToBeforeCharBackward</span></span>

<span data-ttu-id="cc43d-365">Заменяет заданный символ.</span><span class="sxs-lookup"><span data-stu-id="cc43d-365">Replaces until given character.</span></span>

- <span data-ttu-id="cc43d-366">Режим команд VI: `<c,T>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-366">Vi command mode: `<c,T>`</span></span>

### <a name="vireplacetochar"></a><span data-ttu-id="cc43d-367">виреплацеточар</span><span class="sxs-lookup"><span data-stu-id="cc43d-367">ViReplaceToChar</span></span>

<span data-ttu-id="cc43d-368">Удаляет до заданного символа.</span><span class="sxs-lookup"><span data-stu-id="cc43d-368">Deletes until given character.</span></span>

- <span data-ttu-id="cc43d-369">Режим команд VI: `<c,f>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-369">Vi command mode: `<c,f>`</span></span>

### <a name="vireplacetocharbackward"></a><span data-ttu-id="cc43d-370">виреплацеточарбакквард</span><span class="sxs-lookup"><span data-stu-id="cc43d-370">ViReplaceToCharBackward</span></span>

<span data-ttu-id="cc43d-371">Заменяет заданный символ.</span><span class="sxs-lookup"><span data-stu-id="cc43d-371">Replaces until given character.</span></span>

- <span data-ttu-id="cc43d-372">Режим команд VI: `<c,F>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-372">Vi command mode: `<c,F>`</span></span>

### <a name="viyankbeginningofline"></a><span data-ttu-id="cc43d-373">вийанкбегиннингофлине</span><span class="sxs-lookup"><span data-stu-id="cc43d-373">ViYankBeginningOfLine</span></span>

<span data-ttu-id="cc43d-374">Янк от начала буфера до курсора.</span><span class="sxs-lookup"><span data-stu-id="cc43d-374">Yank from the beginning of the buffer to the cursor.</span></span>

- <span data-ttu-id="cc43d-375">Режим команд VI: `<y,0>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-375">Vi command mode: `<y,0>`</span></span>

### <a name="viyankendofglob"></a><span data-ttu-id="cc43d-376">вийанкендофглоб</span><span class="sxs-lookup"><span data-stu-id="cc43d-376">ViYankEndOfGlob</span></span>

<span data-ttu-id="cc43d-377">Янк от курсора до конца слова.</span><span class="sxs-lookup"><span data-stu-id="cc43d-377">Yank from the cursor to the end of the WORD(s).</span></span>

- <span data-ttu-id="cc43d-378">Режим команд VI: `<y,E>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-378">Vi command mode: `<y,E>`</span></span>

### <a name="viyankendofword"></a><span data-ttu-id="cc43d-379">вийанкендофворд</span><span class="sxs-lookup"><span data-stu-id="cc43d-379">ViYankEndOfWord</span></span>

<span data-ttu-id="cc43d-380">Янк от курсора до конца слова.</span><span class="sxs-lookup"><span data-stu-id="cc43d-380">Yank from the cursor to the end of the word(s).</span></span>

- <span data-ttu-id="cc43d-381">Режим команд VI: `<y,e>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-381">Vi command mode: `<y,e>`</span></span>

### <a name="viyankleft"></a><span data-ttu-id="cc43d-382">вийанклефт</span><span class="sxs-lookup"><span data-stu-id="cc43d-382">ViYankLeft</span></span>

<span data-ttu-id="cc43d-383">Янк символы слева от курсора.</span><span class="sxs-lookup"><span data-stu-id="cc43d-383">Yank character(s) to the left of the cursor.</span></span>

- <span data-ttu-id="cc43d-384">Режим команд VI: `<y,h>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-384">Vi command mode: `<y,h>`</span></span>

### <a name="viyankline"></a><span data-ttu-id="cc43d-385">вийанклине</span><span class="sxs-lookup"><span data-stu-id="cc43d-385">ViYankLine</span></span>

<span data-ttu-id="cc43d-386">Янк весь буфер.</span><span class="sxs-lookup"><span data-stu-id="cc43d-386">Yank the entire buffer.</span></span>

- <span data-ttu-id="cc43d-387">Режим команд VI: `<y,y>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-387">Vi command mode: `<y,y>`</span></span>

### <a name="viyanknextglob"></a><span data-ttu-id="cc43d-388">вийанкнекстглоб</span><span class="sxs-lookup"><span data-stu-id="cc43d-388">ViYankNextGlob</span></span>

<span data-ttu-id="cc43d-389">Янк от курсора до начала следующего слова.</span><span class="sxs-lookup"><span data-stu-id="cc43d-389">Yank from cursor to the start of the next WORD(s).</span></span>

- <span data-ttu-id="cc43d-390">Режим команд VI: `<y,W>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-390">Vi command mode: `<y,W>`</span></span>

### <a name="viyanknextword"></a><span data-ttu-id="cc43d-391">вийанкнекстворд</span><span class="sxs-lookup"><span data-stu-id="cc43d-391">ViYankNextWord</span></span>

<span data-ttu-id="cc43d-392">Янк слова после курсора.</span><span class="sxs-lookup"><span data-stu-id="cc43d-392">Yank the word(s) after the cursor.</span></span>

- <span data-ttu-id="cc43d-393">Режим команд VI: `<y,w>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-393">Vi command mode: `<y,w>`</span></span>

### <a name="viyankpercent"></a><span data-ttu-id="cc43d-394">вийанкперцент</span><span class="sxs-lookup"><span data-stu-id="cc43d-394">ViYankPercent</span></span>

<span data-ttu-id="cc43d-395">Янк в парную фигурную скобку.</span><span class="sxs-lookup"><span data-stu-id="cc43d-395">Yank to/from matching brace.</span></span>

- <span data-ttu-id="cc43d-396">Режим команд VI: `<y,%>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-396">Vi command mode: `<y,%>`</span></span>

### <a name="viyankpreviousglob"></a><span data-ttu-id="cc43d-397">вийанкпревиаусглоб</span><span class="sxs-lookup"><span data-stu-id="cc43d-397">ViYankPreviousGlob</span></span>

<span data-ttu-id="cc43d-398">Янк от начала слов до курсора.</span><span class="sxs-lookup"><span data-stu-id="cc43d-398">Yank from beginning of the WORD(s) to cursor.</span></span>

- <span data-ttu-id="cc43d-399">Режим команд VI: `<y,B>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-399">Vi command mode: `<y,B>`</span></span>

### <a name="viyankpreviousword"></a><span data-ttu-id="cc43d-400">вийанкпревиаусворд</span><span class="sxs-lookup"><span data-stu-id="cc43d-400">ViYankPreviousWord</span></span>

<span data-ttu-id="cc43d-401">Янк слова перед курсором.</span><span class="sxs-lookup"><span data-stu-id="cc43d-401">Yank the word(s) before the cursor.</span></span>

- <span data-ttu-id="cc43d-402">Режим команд VI: `<y,b>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-402">Vi command mode: `<y,b>`</span></span>

### <a name="viyankright"></a><span data-ttu-id="cc43d-403">вийанкригхт</span><span class="sxs-lookup"><span data-stu-id="cc43d-403">ViYankRight</span></span>

<span data-ttu-id="cc43d-404">Янк символы в положении и справа от курсора.</span><span class="sxs-lookup"><span data-stu-id="cc43d-404">Yank character(s) under and to the right of the cursor.</span></span>

- <span data-ttu-id="cc43d-405">Режим команд VI: `<y,l>` , `<y,Space>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-405">Vi command mode: `<y,l>`, `<y,Space>`</span></span>

### <a name="viyanktoendofline"></a><span data-ttu-id="cc43d-406">вийанктоендофлине</span><span class="sxs-lookup"><span data-stu-id="cc43d-406">ViYankToEndOfLine</span></span>

<span data-ttu-id="cc43d-407">Янк от курсора до конца буфера.</span><span class="sxs-lookup"><span data-stu-id="cc43d-407">Yank from the cursor to the end of the buffer.</span></span>

- <span data-ttu-id="cc43d-408">Режим команд VI: `<y,$>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-408">Vi command mode: `<y,$>`</span></span>

### <a name="viyanktofirstchar"></a><span data-ttu-id="cc43d-409">вийанктофирстчар</span><span class="sxs-lookup"><span data-stu-id="cc43d-409">ViYankToFirstChar</span></span>

<span data-ttu-id="cc43d-410">Янк от первого символа, отличного от пробела, к курсору.</span><span class="sxs-lookup"><span data-stu-id="cc43d-410">Yank from the first non-whitespace character to the cursor.</span></span>

- <span data-ttu-id="cc43d-411">Режим команд VI: `<y,^>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-411">Vi command mode: `<y,^>`</span></span>

### <a name="yank"></a><span data-ttu-id="cc43d-412">янк</span><span class="sxs-lookup"><span data-stu-id="cc43d-412">Yank</span></span>

<span data-ttu-id="cc43d-413">Добавление последнего недавнего текста во входные данные.</span><span class="sxs-lookup"><span data-stu-id="cc43d-413">Add the most recently killed text to the input.</span></span>

- <span data-ttu-id="cc43d-414">Emacs: `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-414">Emacs: `<Ctrl+y>`</span></span>

### <a name="yanklastarg"></a><span data-ttu-id="cc43d-415">янкластарг</span><span class="sxs-lookup"><span data-stu-id="cc43d-415">YankLastArg</span></span>

<span data-ttu-id="cc43d-416">Янк последний аргумент из предыдущей строки журнала.</span><span class="sxs-lookup"><span data-stu-id="cc43d-416">Yank the last argument from the previous history line.</span></span> <span data-ttu-id="cc43d-417">С аргументом при первом вызове он ведет себя так же, как Янкнсарг.</span><span class="sxs-lookup"><span data-stu-id="cc43d-417">With an argument, the first time it is invoked, behaves just like YankNthArg.</span></span> <span data-ttu-id="cc43d-418">Если вызывается несколько раз, вместо этого выполняется итерация по журналу, а аргумент устанавливает направление (отрицательно меняет направление на противоположное).</span><span class="sxs-lookup"><span data-stu-id="cc43d-418">If invoked multiple times, instead it iterates through history and arg sets the direction (negative reverses the direction.)</span></span>

- <span data-ttu-id="cc43d-419">Процессор `<Alt+.>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-419">Cmd: `<Alt+.>`</span></span>
- <span data-ttu-id="cc43d-420">Emacs: `<Alt+.>` , `<Alt+_>` , `<Escape,.>` , `<Escape,_>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-420">Emacs: `<Alt+.>`, `<Alt+_>`, `<Escape,.>`, `<Escape,_>`</span></span>

### <a name="yankntharg"></a><span data-ttu-id="cc43d-421">янкнсарг</span><span class="sxs-lookup"><span data-stu-id="cc43d-421">YankNthArg</span></span>

<span data-ttu-id="cc43d-422">Янк первый аргумент (после команды) из предыдущей строки журнала.</span><span class="sxs-lookup"><span data-stu-id="cc43d-422">Yank the first argument (after the command) from the previous history line.</span></span>
<span data-ttu-id="cc43d-423">При использовании аргумента Янк аргумент n (начиная с 0), если аргумент является отрицательным, начните с последнего аргумента.</span><span class="sxs-lookup"><span data-stu-id="cc43d-423">With an argument, yank the nth argument (starting from 0), if the argument is negative, start from the last argument.</span></span>

- <span data-ttu-id="cc43d-424">Emacs: `<Ctrl+Alt+y>` , `<Escape,Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-424">Emacs: `<Ctrl+Alt+y>`, `<Escape,Ctrl+y>`</span></span>

### <a name="yankpop"></a><span data-ttu-id="cc43d-425">янкпоп</span><span class="sxs-lookup"><span data-stu-id="cc43d-425">YankPop</span></span>

<span data-ttu-id="cc43d-426">Если предыдущая операция была Янк или Янкпоп, замените ранее янкед текст следующим уничтоженным текстом из Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="cc43d-426">If the previous operation was Yank or YankPop, replace the previously yanked text with the next killed text from the kill-ring.</span></span>

- <span data-ttu-id="cc43d-427">Emacs: `<Alt+y>` , `<Escape,y>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-427">Emacs: `<Alt+y>`, `<Escape,y>`</span></span>

## <a name="cursor-movement-functions"></a><span data-ttu-id="cc43d-428">Функции перемещения курсора</span><span class="sxs-lookup"><span data-stu-id="cc43d-428">Cursor movement functions</span></span>

### <a name="backwardchar"></a><span data-ttu-id="cc43d-429">бакквардчар</span><span class="sxs-lookup"><span data-stu-id="cc43d-429">BackwardChar</span></span>

<span data-ttu-id="cc43d-430">Переместить курсор на один символ влево.</span><span class="sxs-lookup"><span data-stu-id="cc43d-430">Move the cursor one character to the left.</span></span> <span data-ttu-id="cc43d-431">Это может переместить курсор к предыдущей строке многострочного ввода.</span><span class="sxs-lookup"><span data-stu-id="cc43d-431">This may move the cursor to the previous line of multi-line input.</span></span>

- <span data-ttu-id="cc43d-432">Процессор `<LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-432">Cmd: `<LeftArrow>`</span></span>
- <span data-ttu-id="cc43d-433">Emacs: `<LeftArrow>` , `<Ctrl+b>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-433">Emacs: `<LeftArrow>`, `<Ctrl+b>`</span></span>
- <span data-ttu-id="cc43d-434">Режим вставки в VI: `<LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-434">Vi insert mode: `<LeftArrow>`</span></span>
- <span data-ttu-id="cc43d-435">Режим команд VI: `<LeftArrow>` , `<Backspace>` , `<h>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-435">Vi command mode: `<LeftArrow>`, `<Backspace>`, `<h>`</span></span>

### <a name="backwardword"></a><span data-ttu-id="cc43d-436">бакквардворд</span><span class="sxs-lookup"><span data-stu-id="cc43d-436">BackwardWord</span></span>

<span data-ttu-id="cc43d-437">Перемещение курсора назад к началу текущего слова или между словами, с начала предыдущего слова.</span><span class="sxs-lookup"><span data-stu-id="cc43d-437">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="cc43d-438">Границы слов определяются с помощью настраиваемого набора символов.</span><span class="sxs-lookup"><span data-stu-id="cc43d-438">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="cc43d-439">Процессор `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-439">Cmd: `<Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="cc43d-440">Emacs: `<Alt+b>` , `<Escape,b>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-440">Emacs: `<Alt+b>`, `<Escape,b>`</span></span>
- <span data-ttu-id="cc43d-441">Режим вставки в VI: `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-441">Vi insert mode: `<Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="cc43d-442">Режим команд VI: `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-442">Vi command mode: `<Ctrl+LeftArrow>`</span></span>

### <a name="beginningofline"></a><span data-ttu-id="cc43d-443">бегиннингофлине</span><span class="sxs-lookup"><span data-stu-id="cc43d-443">BeginningOfLine</span></span>

<span data-ttu-id="cc43d-444">Если входные данные имеют несколько строк, переместитесь в начало текущей строки или, если они уже находятся в начале строки, перейдите к началу входного элемента.</span><span class="sxs-lookup"><span data-stu-id="cc43d-444">If the input has multiple lines, move to the start of the current line, or if already at the start of the line, move to the start of the input.</span></span> <span data-ttu-id="cc43d-445">Если входные данные имеют одну строку, переходите к началу входных данных.</span><span class="sxs-lookup"><span data-stu-id="cc43d-445">If the input has a single line, move to the start of the input.</span></span>

- <span data-ttu-id="cc43d-446">Процессор `<Home>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-446">Cmd: `<Home>`</span></span>
- <span data-ttu-id="cc43d-447">Emacs: `<Home>` , `<Ctrl+a>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-447">Emacs: `<Home>`, `<Ctrl+a>`</span></span>
- <span data-ttu-id="cc43d-448">Режим вставки в VI: `<Home>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-448">Vi insert mode: `<Home>`</span></span>
- <span data-ttu-id="cc43d-449">Режим команд VI: `<Home>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-449">Vi command mode: `<Home>`</span></span>

### <a name="endofline"></a><span data-ttu-id="cc43d-450">ендофлине</span><span class="sxs-lookup"><span data-stu-id="cc43d-450">EndOfLine</span></span>

<span data-ttu-id="cc43d-451">Если входные данные имеют несколько строк, переместитесь в конец текущей строки или, если они уже находятся в конце строки, перейдите к концу входных данных.</span><span class="sxs-lookup"><span data-stu-id="cc43d-451">If the input has multiple lines, move to the end of the current line, or if already at the end of the line, move to the end of the input.</span></span> <span data-ttu-id="cc43d-452">Если входные данные имеют одну строку, переходите к концу входных данных.</span><span class="sxs-lookup"><span data-stu-id="cc43d-452">If the input has a single line, move to the end of the input.</span></span>

- <span data-ttu-id="cc43d-453">Процессор `<End>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-453">Cmd: `<End>`</span></span>
- <span data-ttu-id="cc43d-454">Emacs: `<End>` , `<Ctrl+e>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-454">Emacs: `<End>`, `<Ctrl+e>`</span></span>
- <span data-ttu-id="cc43d-455">Режим вставки в VI: `<End>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-455">Vi insert mode: `<End>`</span></span>

### <a name="forwardchar"></a><span data-ttu-id="cc43d-456">форвардчар</span><span class="sxs-lookup"><span data-stu-id="cc43d-456">ForwardChar</span></span>

<span data-ttu-id="cc43d-457">Переместить курсор на один символ вправо.</span><span class="sxs-lookup"><span data-stu-id="cc43d-457">Move the cursor one character to the right.</span></span> <span data-ttu-id="cc43d-458">Это может переместить курсор на следующую строку многострочного ввода.</span><span class="sxs-lookup"><span data-stu-id="cc43d-458">This may move the cursor to the next line of multi-line input.</span></span>

- <span data-ttu-id="cc43d-459">Процессор `<RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-459">Cmd: `<RightArrow>`</span></span>
- <span data-ttu-id="cc43d-460">Emacs: `<RightArrow>` , `<Ctrl+f>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-460">Emacs: `<RightArrow>`, `<Ctrl+f>`</span></span>
- <span data-ttu-id="cc43d-461">Режим вставки в VI: `<RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-461">Vi insert mode: `<RightArrow>`</span></span>
- <span data-ttu-id="cc43d-462">Режим команд VI: `<RightArrow>` , `<Space>` , `<l>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-462">Vi command mode: `<RightArrow>`, `<Space>`, `<l>`</span></span>

### <a name="forwardword"></a><span data-ttu-id="cc43d-463">форвардворд</span><span class="sxs-lookup"><span data-stu-id="cc43d-463">ForwardWord</span></span>

<span data-ttu-id="cc43d-464">Переместить курсор вперед к концу текущего слова или между словами, до конца следующего слова.</span><span class="sxs-lookup"><span data-stu-id="cc43d-464">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="cc43d-465">Границы слов определяются с помощью настраиваемого набора символов.</span><span class="sxs-lookup"><span data-stu-id="cc43d-465">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="cc43d-466">Emacs: `<Alt+f>` , `<Escape,f>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-466">Emacs: `<Alt+f>`, `<Escape,f>`</span></span>

### <a name="gotobrace"></a><span data-ttu-id="cc43d-467">GotoBrace</span><span class="sxs-lookup"><span data-stu-id="cc43d-467">GotoBrace</span></span>

<span data-ttu-id="cc43d-468">Перейдите к парной фигурной скобке, круглой скобке или квадратной скобке.</span><span class="sxs-lookup"><span data-stu-id="cc43d-468">Go to the matching brace, parenthesis, or square bracket.</span></span>

- <span data-ttu-id="cc43d-469">Процессор `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-469">Cmd: `<Ctrl+]>`</span></span>
- <span data-ttu-id="cc43d-470">Режим вставки в VI: `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-470">Vi insert mode: `<Ctrl+]>`</span></span>
- <span data-ttu-id="cc43d-471">Режим команд VI: `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-471">Vi command mode: `<Ctrl+]>`</span></span>

### <a name="gotocolumn"></a><span data-ttu-id="cc43d-472">готоколумн</span><span class="sxs-lookup"><span data-stu-id="cc43d-472">GotoColumn</span></span>

<span data-ttu-id="cc43d-473">Переход к столбцу, указанному аргументом arg.</span><span class="sxs-lookup"><span data-stu-id="cc43d-473">Move to the column indicated by arg.</span></span>

- <span data-ttu-id="cc43d-474">Режим команд VI: `<|>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-474">Vi command mode: `<|>`</span></span>

### <a name="gotofirstnonblankofline"></a><span data-ttu-id="cc43d-475">готофирстнонбланкофлине</span><span class="sxs-lookup"><span data-stu-id="cc43d-475">GotoFirstNonBlankOfLine</span></span>

<span data-ttu-id="cc43d-476">Переместить курсор к первому непустому символу в строке.</span><span class="sxs-lookup"><span data-stu-id="cc43d-476">Move the cursor to the first non-blank character in the line.</span></span>

- <span data-ttu-id="cc43d-477">Режим команд VI: `<^>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-477">Vi command mode: `<^>`</span></span>

### <a name="movetoendofline"></a><span data-ttu-id="cc43d-478">моветоендофлине</span><span class="sxs-lookup"><span data-stu-id="cc43d-478">MoveToEndOfLine</span></span>

<span data-ttu-id="cc43d-479">Переместить курсор в конец входных данных.</span><span class="sxs-lookup"><span data-stu-id="cc43d-479">Move the cursor to the end of the input.</span></span>

- <span data-ttu-id="cc43d-480">Режим команд VI: `<End>` , `<$>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-480">Vi command mode: `<End>`, `<$>`</span></span>

### <a name="nextline"></a><span data-ttu-id="cc43d-481">некстлине</span><span class="sxs-lookup"><span data-stu-id="cc43d-481">NextLine</span></span>

<span data-ttu-id="cc43d-482">Переместить курсор на следующую строку.</span><span class="sxs-lookup"><span data-stu-id="cc43d-482">Move the cursor to the next line.</span></span>

- <span data-ttu-id="cc43d-483">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="cc43d-483">Function is unbound.</span></span>

### <a name="nextword"></a><span data-ttu-id="cc43d-484">некстворд</span><span class="sxs-lookup"><span data-stu-id="cc43d-484">NextWord</span></span>

<span data-ttu-id="cc43d-485">Переместить курсор вперед к началу следующего слова.</span><span class="sxs-lookup"><span data-stu-id="cc43d-485">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="cc43d-486">Границы слов определяются с помощью настраиваемого набора символов.</span><span class="sxs-lookup"><span data-stu-id="cc43d-486">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="cc43d-487">Процессор `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-487">Cmd: `<Ctrl+RightArrow>`</span></span>
- <span data-ttu-id="cc43d-488">Режим вставки в VI: `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-488">Vi insert mode: `<Ctrl+RightArrow>`</span></span>
- <span data-ttu-id="cc43d-489">Режим команд VI: `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-489">Vi command mode: `<Ctrl+RightArrow>`</span></span>

### <a name="nextwordend"></a><span data-ttu-id="cc43d-490">некстворденд</span><span class="sxs-lookup"><span data-stu-id="cc43d-490">NextWordEnd</span></span>

<span data-ttu-id="cc43d-491">Переместить курсор вперед к концу текущего слова или между словами, до конца следующего слова.</span><span class="sxs-lookup"><span data-stu-id="cc43d-491">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="cc43d-492">Границы слов определяются с помощью настраиваемого набора символов.</span><span class="sxs-lookup"><span data-stu-id="cc43d-492">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="cc43d-493">Режим команд VI: `<e>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-493">Vi command mode: `<e>`</span></span>

### <a name="previousline"></a><span data-ttu-id="cc43d-494">превиауслине</span><span class="sxs-lookup"><span data-stu-id="cc43d-494">PreviousLine</span></span>

<span data-ttu-id="cc43d-495">Переместить курсор на предыдущую строку.</span><span class="sxs-lookup"><span data-stu-id="cc43d-495">Move the cursor to the previous line.</span></span>

- <span data-ttu-id="cc43d-496">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="cc43d-496">Function is unbound.</span></span>

### <a name="shellbackwardword"></a><span data-ttu-id="cc43d-497">шеллбакквардворд</span><span class="sxs-lookup"><span data-stu-id="cc43d-497">ShellBackwardWord</span></span>

<span data-ttu-id="cc43d-498">Перемещение курсора назад к началу текущего слова или между словами, с начала предыдущего слова.</span><span class="sxs-lookup"><span data-stu-id="cc43d-498">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="cc43d-499">Границы слов определяются токенами PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cc43d-499">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="cc43d-500">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="cc43d-500">Function is unbound.</span></span>

### <a name="shellforwardword"></a><span data-ttu-id="cc43d-501">шеллфорвардворд</span><span class="sxs-lookup"><span data-stu-id="cc43d-501">ShellForwardWord</span></span>

<span data-ttu-id="cc43d-502">Переместить курсор вперед к началу следующего слова.</span><span class="sxs-lookup"><span data-stu-id="cc43d-502">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="cc43d-503">Границы слов определяются токенами PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cc43d-503">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="cc43d-504">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="cc43d-504">Function is unbound.</span></span>

### <a name="shellnextword"></a><span data-ttu-id="cc43d-505">шеллнекстворд</span><span class="sxs-lookup"><span data-stu-id="cc43d-505">ShellNextWord</span></span>

<span data-ttu-id="cc43d-506">Переместить курсор вперед к концу текущего слова или между словами, до конца следующего слова.</span><span class="sxs-lookup"><span data-stu-id="cc43d-506">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="cc43d-507">Границы слов определяются токенами PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cc43d-507">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="cc43d-508">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="cc43d-508">Function is unbound.</span></span>

### <a name="vibackwardword"></a><span data-ttu-id="cc43d-509">вибакквардворд</span><span class="sxs-lookup"><span data-stu-id="cc43d-509">ViBackwardWord</span></span>

<span data-ttu-id="cc43d-510">Перемещение курсора назад к началу текущего слова или между словами, с начала предыдущего слова.</span><span class="sxs-lookup"><span data-stu-id="cc43d-510">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="cc43d-511">Границы слов определяются с помощью настраиваемого набора символов.</span><span class="sxs-lookup"><span data-stu-id="cc43d-511">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="cc43d-512">Режим команд VI: `<b>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-512">Vi command mode: `<b>`</span></span>

### <a name="viendofglob"></a><span data-ttu-id="cc43d-513">виендофглоб</span><span class="sxs-lookup"><span data-stu-id="cc43d-513">ViEndOfGlob</span></span>

<span data-ttu-id="cc43d-514">Перемещает курсор в конец слова, используя только пробелы в качестве разделителей.</span><span class="sxs-lookup"><span data-stu-id="cc43d-514">Moves the cursor to the end of the word, using only white space as delimiters.</span></span>

- <span data-ttu-id="cc43d-515">Режим команд VI: `<E>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-515">Vi command mode: `<E>`</span></span>

### <a name="viendofpreviousglob"></a><span data-ttu-id="cc43d-516">виендофпревиаусглоб</span><span class="sxs-lookup"><span data-stu-id="cc43d-516">ViEndOfPreviousGlob</span></span>

<span data-ttu-id="cc43d-517">Переход к концу предыдущего слова с использованием только пробелов в качестве разделителя слов.</span><span class="sxs-lookup"><span data-stu-id="cc43d-517">Moves to the end of the previous word, using only white space as a word delimiter.</span></span>

- <span data-ttu-id="cc43d-518">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="cc43d-518">Function is unbound.</span></span>

### <a name="vigotobrace"></a><span data-ttu-id="cc43d-519">виготобраце</span><span class="sxs-lookup"><span data-stu-id="cc43d-519">ViGotoBrace</span></span>

<span data-ttu-id="cc43d-520">Аналогичен Готобраце, но является символом, а не основан на токене.</span><span class="sxs-lookup"><span data-stu-id="cc43d-520">Similar to GotoBrace, but is character based instead of token based.</span></span>

- <span data-ttu-id="cc43d-521">Режим команд VI: `<%>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-521">Vi command mode: `<%>`</span></span>

### <a name="vinextglob"></a><span data-ttu-id="cc43d-522">винекстглоб</span><span class="sxs-lookup"><span data-stu-id="cc43d-522">ViNextGlob</span></span>

<span data-ttu-id="cc43d-523">Переход к следующему слову с использованием только пробелов в качестве разделителя слов.</span><span class="sxs-lookup"><span data-stu-id="cc43d-523">Moves to the next word, using only white space as a word delimiter.</span></span>

- <span data-ttu-id="cc43d-524">Режим команд VI: `<W>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-524">Vi command mode: `<W>`</span></span>

### <a name="vinextword"></a><span data-ttu-id="cc43d-525">винекстворд</span><span class="sxs-lookup"><span data-stu-id="cc43d-525">ViNextWord</span></span>

<span data-ttu-id="cc43d-526">Переместить курсор вперед к началу следующего слова.</span><span class="sxs-lookup"><span data-stu-id="cc43d-526">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="cc43d-527">Границы слов определяются с помощью настраиваемого набора символов.</span><span class="sxs-lookup"><span data-stu-id="cc43d-527">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="cc43d-528">Режим команд VI: `<w>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-528">Vi command mode: `<w>`</span></span>

## <a name="history-functions"></a><span data-ttu-id="cc43d-529">Функции журнала</span><span class="sxs-lookup"><span data-stu-id="cc43d-529">History functions</span></span>

### <a name="beginningofhistory"></a><span data-ttu-id="cc43d-530">бегиннингофхистори</span><span class="sxs-lookup"><span data-stu-id="cc43d-530">BeginningOfHistory</span></span>

<span data-ttu-id="cc43d-531">Перейти к первому элементу в журнале.</span><span class="sxs-lookup"><span data-stu-id="cc43d-531">Move to the first item in the history.</span></span>

- <span data-ttu-id="cc43d-532">Emacs: `<Alt+`<>\`</span><span class="sxs-lookup"><span data-stu-id="cc43d-532">Emacs: `<Alt+`<>\`</span></span>

### <a name="clearhistory"></a><span data-ttu-id="cc43d-533">клеархистори</span><span class="sxs-lookup"><span data-stu-id="cc43d-533">ClearHistory</span></span>

<span data-ttu-id="cc43d-534">Очищает журнал в PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="cc43d-534">Clears history in PSReadLine.</span></span> <span data-ttu-id="cc43d-535">Это не влияет на журнал PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cc43d-535">This does not affect PowerShell history.</span></span>

- <span data-ttu-id="cc43d-536">Процессор `<Alt+F7>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-536">Cmd: `<Alt+F7>`</span></span>

### <a name="endofhistory"></a><span data-ttu-id="cc43d-537">ендофхистори</span><span class="sxs-lookup"><span data-stu-id="cc43d-537">EndOfHistory</span></span>

<span data-ttu-id="cc43d-538">Переход к последнему элементу (текущему входному объекту) в журнале.</span><span class="sxs-lookup"><span data-stu-id="cc43d-538">Move to the last item (the current input) in the history.</span></span>

- <span data-ttu-id="cc43d-539">Emacs: `<Alt+>>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-539">Emacs: `<Alt+>>`</span></span>

### <a name="forwardsearchhistory"></a><span data-ttu-id="cc43d-540">форвардсеарчхистори</span><span class="sxs-lookup"><span data-stu-id="cc43d-540">ForwardSearchHistory</span></span>

<span data-ttu-id="cc43d-541">Выполните добавочный поиск по журналу.</span><span class="sxs-lookup"><span data-stu-id="cc43d-541">Perform an incremental forward search through history.</span></span>

- <span data-ttu-id="cc43d-542">Процессор `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-542">Cmd: `<Ctrl+s>`</span></span>
- <span data-ttu-id="cc43d-543">Emacs: `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-543">Emacs: `<Ctrl+s>`</span></span>

### <a name="historysearchbackward"></a><span data-ttu-id="cc43d-544">хисторисеарчбакквард</span><span class="sxs-lookup"><span data-stu-id="cc43d-544">HistorySearchBackward</span></span>

<span data-ttu-id="cc43d-545">Замените текущие входные данные элементом "Previous" из журнала PSReadLine, который соответствует символам между началом и входом и курсором.</span><span class="sxs-lookup"><span data-stu-id="cc43d-545">Replace the current input with the 'previous' item from PSReadLine history that matches the characters between the start and the input and the cursor.</span></span>

- <span data-ttu-id="cc43d-546">Процессор `<F8>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-546">Cmd: `<F8>`</span></span>

### <a name="historysearchforward"></a><span data-ttu-id="cc43d-547">хисторисеарчфорвард</span><span class="sxs-lookup"><span data-stu-id="cc43d-547">HistorySearchForward</span></span>

<span data-ttu-id="cc43d-548">Замените текущие входные данные элементом "Next" из журнала PSReadLine, который соответствует символам между началом и входом и курсором.</span><span class="sxs-lookup"><span data-stu-id="cc43d-548">Replace the current input with the 'next' item from PSReadLine history that matches the characters between the start and the input and the cursor.</span></span>

- <span data-ttu-id="cc43d-549">Процессор `<Shift+F8>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-549">Cmd: `<Shift+F8>`</span></span>

### <a name="nexthistory"></a><span data-ttu-id="cc43d-550">некссистори</span><span class="sxs-lookup"><span data-stu-id="cc43d-550">NextHistory</span></span>

<span data-ttu-id="cc43d-551">Замените текущие входные данные на элемент "Next" из журнала PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="cc43d-551">Replace the current input with the 'next' item from PSReadLine history.</span></span>

- <span data-ttu-id="cc43d-552">Процессор `<DownArrow>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-552">Cmd: `<DownArrow>`</span></span>
- <span data-ttu-id="cc43d-553">Emacs: `<DownArrow>` , `<Ctrl+n>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-553">Emacs: `<DownArrow>`, `<Ctrl+n>`</span></span>
- <span data-ttu-id="cc43d-554">Режим вставки в VI: `<DownArrow>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-554">Vi insert mode: `<DownArrow>`</span></span>
- <span data-ttu-id="cc43d-555">Режим команд VI: `<DownArrow>` , `<j>` , `<+>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-555">Vi command mode: `<DownArrow>`, `<j>`, `<+>`</span></span>

### <a name="previoushistory"></a><span data-ttu-id="cc43d-556">превиаушистори</span><span class="sxs-lookup"><span data-stu-id="cc43d-556">PreviousHistory</span></span>

<span data-ttu-id="cc43d-557">Замените текущие входные данные элементом "Previous" из журнала PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="cc43d-557">Replace the current input with the 'previous' item from PSReadLine history.</span></span>

- <span data-ttu-id="cc43d-558">Процессор `<UpArrow>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-558">Cmd: `<UpArrow>`</span></span>
- <span data-ttu-id="cc43d-559">Emacs: `<UpArrow>` , `<Ctrl+p>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-559">Emacs: `<UpArrow>`, `<Ctrl+p>`</span></span>
- <span data-ttu-id="cc43d-560">Режим вставки в VI: `<UpArrow>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-560">Vi insert mode: `<UpArrow>`</span></span>
- <span data-ttu-id="cc43d-561">Режим команд VI: `<UpArrow>` , `<k>` , `<->`</span><span class="sxs-lookup"><span data-stu-id="cc43d-561">Vi command mode: `<UpArrow>`, `<k>`, `<->`</span></span>

### <a name="reversesearchhistory"></a><span data-ttu-id="cc43d-562">реверсесеарчхистори</span><span class="sxs-lookup"><span data-stu-id="cc43d-562">ReverseSearchHistory</span></span>

<span data-ttu-id="cc43d-563">Выполните добавочный поиск по журналу.</span><span class="sxs-lookup"><span data-stu-id="cc43d-563">Perform an incremental backward search through history.</span></span>

- <span data-ttu-id="cc43d-564">Процессор `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-564">Cmd: `<Ctrl+r>`</span></span>
- <span data-ttu-id="cc43d-565">Emacs: `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-565">Emacs: `<Ctrl+r>`</span></span>

### <a name="visearchhistorybackward"></a><span data-ttu-id="cc43d-566">висеарчхисторибакквард</span><span class="sxs-lookup"><span data-stu-id="cc43d-566">ViSearchHistoryBackward</span></span>

<span data-ttu-id="cc43d-567">Запрашивает строку поиска и инициирует поиск по запросу Акцептлине.</span><span class="sxs-lookup"><span data-stu-id="cc43d-567">Prompts for a search string and initiates search upon AcceptLine.</span></span>

- <span data-ttu-id="cc43d-568">Режим вставки в VI: `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-568">Vi insert mode: `<Ctrl+r>`</span></span>
- <span data-ttu-id="cc43d-569">Режим команд VI: `</>` , `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-569">Vi command mode: `</>`, `<Ctrl+r>`</span></span>

## <a name="completion-functions"></a><span data-ttu-id="cc43d-570">Функции завершения</span><span class="sxs-lookup"><span data-stu-id="cc43d-570">Completion functions</span></span>

### <a name="complete"></a><span data-ttu-id="cc43d-571">Завершить</span><span class="sxs-lookup"><span data-stu-id="cc43d-571">Complete</span></span>

<span data-ttu-id="cc43d-572">Попытка выполнить завершение в тексте, окружающем курсор.</span><span class="sxs-lookup"><span data-stu-id="cc43d-572">Attempt to perform completion on the text surrounding the cursor.</span></span> <span data-ttu-id="cc43d-573">Если существует несколько возможных завершений, для завершения используется самый длинный ненеоднозначный префикс.</span><span class="sxs-lookup"><span data-stu-id="cc43d-573">If there are multiple possible completions, the longest unambiguous prefix is used for completion.</span></span> <span data-ttu-id="cc43d-574">При попытке выполнить наибольшее неоднозначное Завершение отображается список возможных завершений.</span><span class="sxs-lookup"><span data-stu-id="cc43d-574">If trying to complete the longest unambiguous completion, a list of possible completions is displayed.</span></span>

- <span data-ttu-id="cc43d-575">Emacs: `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-575">Emacs: `<Tab>`</span></span>

### <a name="menucomplete"></a><span data-ttu-id="cc43d-576">менукомплете</span><span class="sxs-lookup"><span data-stu-id="cc43d-576">MenuComplete</span></span>

<span data-ttu-id="cc43d-577">Попытка выполнить завершение в тексте, окружающем курсор.</span><span class="sxs-lookup"><span data-stu-id="cc43d-577">Attempt to perform completion on the text surrounding the cursor.</span></span> <span data-ttu-id="cc43d-578">Если существует несколько возможных завершений, для завершения используется самый длинный ненеоднозначный префикс.</span><span class="sxs-lookup"><span data-stu-id="cc43d-578">If there are multiple possible completions, the longest unambiguous prefix is used for completion.</span></span> <span data-ttu-id="cc43d-579">При попытке выполнить наибольшее неоднозначное Завершение отображается список возможных завершений.</span><span class="sxs-lookup"><span data-stu-id="cc43d-579">If trying to complete the longest unambiguous completion, a list of possible completions is displayed.</span></span>

- <span data-ttu-id="cc43d-580">Процессор `<Ctrl+Space>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-580">Cmd: `<Ctrl+Space>`</span></span>
- <span data-ttu-id="cc43d-581">Emacs: `<Ctrl+Space>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-581">Emacs: `<Ctrl+Space>`</span></span>

### <a name="possiblecompletions"></a><span data-ttu-id="cc43d-582">поссиблекомплетионс</span><span class="sxs-lookup"><span data-stu-id="cc43d-582">PossibleCompletions</span></span>

<span data-ttu-id="cc43d-583">Отображение списка возможных завершений.</span><span class="sxs-lookup"><span data-stu-id="cc43d-583">Display the list of possible completions.</span></span>

- <span data-ttu-id="cc43d-584">Emacs: `<Alt+=>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-584">Emacs: `<Alt+=>`</span></span>
- <span data-ttu-id="cc43d-585">Режим вставки в VI: `<Ctrl+Space>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-585">Vi insert mode: `<Ctrl+Space>`</span></span>
- <span data-ttu-id="cc43d-586">Режим команд VI: `<Ctrl+Space>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-586">Vi command mode: `<Ctrl+Space>`</span></span>

### <a name="tabcompletenext"></a><span data-ttu-id="cc43d-587">табкомплетенекст</span><span class="sxs-lookup"><span data-stu-id="cc43d-587">TabCompleteNext</span></span>

<span data-ttu-id="cc43d-588">Попытайтесь завершить текст, окружающий курсор, с помощью следующего доступного завершения.</span><span class="sxs-lookup"><span data-stu-id="cc43d-588">Attempt to complete the text surrounding the cursor with the next available completion.</span></span>

- <span data-ttu-id="cc43d-589">Процессор `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-589">Cmd: `<Tab>`</span></span>
- <span data-ttu-id="cc43d-590">Режим команд VI: `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-590">Vi command mode: `<Tab>`</span></span>

### <a name="tabcompleteprevious"></a><span data-ttu-id="cc43d-591">табкомплетепревиаус</span><span class="sxs-lookup"><span data-stu-id="cc43d-591">TabCompletePrevious</span></span>

<span data-ttu-id="cc43d-592">Попытайтесь завершить текст, окружающий курсор, с предыдущим доступным завершением.</span><span class="sxs-lookup"><span data-stu-id="cc43d-592">Attempt to complete the text surrounding the cursor with the previous available completion.</span></span>

- <span data-ttu-id="cc43d-593">Процессор `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-593">Cmd: `<Shift+Tab>`</span></span>
- <span data-ttu-id="cc43d-594">Режим команд VI: `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-594">Vi command mode: `<Shift+Tab>`</span></span>

### <a name="vitabcompletenext"></a><span data-ttu-id="cc43d-595">витабкомплетенекст</span><span class="sxs-lookup"><span data-stu-id="cc43d-595">ViTabCompleteNext</span></span>

<span data-ttu-id="cc43d-596">При необходимости завершает текущую группу редактирования и вызывает Табкомплетенекст.</span><span class="sxs-lookup"><span data-stu-id="cc43d-596">Ends the current edit group, if needed, and invokes TabCompleteNext.</span></span>

- <span data-ttu-id="cc43d-597">Режим вставки в VI: `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-597">Vi insert mode: `<Tab>`</span></span>

### <a name="vitabcompleteprevious"></a><span data-ttu-id="cc43d-598">витабкомплетепревиаус</span><span class="sxs-lookup"><span data-stu-id="cc43d-598">ViTabCompletePrevious</span></span>

<span data-ttu-id="cc43d-599">При необходимости завершает текущую группу редактирования и вызывает Табкомплетепревиаус.</span><span class="sxs-lookup"><span data-stu-id="cc43d-599">Ends the current edit group, if needed, and invokes TabCompletePrevious.</span></span>

- <span data-ttu-id="cc43d-600">Режим вставки в VI: `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-600">Vi insert mode: `<Shift+Tab>`</span></span>

## <a name="miscellaneous-functions"></a><span data-ttu-id="cc43d-601">Прочие функции</span><span class="sxs-lookup"><span data-stu-id="cc43d-601">Miscellaneous functions</span></span>

### <a name="capturescreen"></a><span data-ttu-id="cc43d-602">каптурескрин</span><span class="sxs-lookup"><span data-stu-id="cc43d-602">CaptureScreen</span></span>

<span data-ttu-id="cc43d-603">Запуск интерактивной записи экрана — стрелки вверх и вниз выбор строк, ввод копирует выделенный текст в буфер обмена в виде текста и HTML.</span><span class="sxs-lookup"><span data-stu-id="cc43d-603">Start interactive screen capture - up/down arrows select lines, enter copies selected text to clipboard as text and html.</span></span>

- <span data-ttu-id="cc43d-604">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="cc43d-604">Function is unbound.</span></span>

### <a name="clearscreen"></a><span data-ttu-id="cc43d-605">клеарскрин</span><span class="sxs-lookup"><span data-stu-id="cc43d-605">ClearScreen</span></span>

<span data-ttu-id="cc43d-606">Очистить экран и нарисовать текущую строку в верхней части экрана.</span><span class="sxs-lookup"><span data-stu-id="cc43d-606">Clear the screen and draw the current line at the top of the screen.</span></span>

- <span data-ttu-id="cc43d-607">Процессор `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-607">Cmd: `<Ctrl+l>`</span></span>
- <span data-ttu-id="cc43d-608">Emacs: `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-608">Emacs: `<Ctrl+l>`</span></span>
- <span data-ttu-id="cc43d-609">Режим вставки в VI: `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-609">Vi insert mode: `<Ctrl+l>`</span></span>
- <span data-ttu-id="cc43d-610">Режим команд VI: `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-610">Vi command mode: `<Ctrl+l>`</span></span>

### <a name="digitargument"></a><span data-ttu-id="cc43d-611">дигитаргумент</span><span class="sxs-lookup"><span data-stu-id="cc43d-611">DigitArgument</span></span>

<span data-ttu-id="cc43d-612">Начните новый аргумент цифры для передачи другим функциям.</span><span class="sxs-lookup"><span data-stu-id="cc43d-612">Start a new digit argument to pass to other functions.</span></span>

- <span data-ttu-id="cc43d-613">Cmd: `<Alt+0>` , `<Alt+1>` , `<Alt+2>` , `<Alt+3>` , `<Alt+4>` , `<Alt+5>` , `<Alt+6>` , `<Alt+7>` , `<Alt+8>` , `<Alt+9>` , `<Alt+->`</span><span class="sxs-lookup"><span data-stu-id="cc43d-613">Cmd: `<Alt+0>`, `<Alt+1>`, `<Alt+2>`, `<Alt+3>`, `<Alt+4>`, `<Alt+5>`, `<Alt+6>`, `<Alt+7>`, `<Alt+8>`, `<Alt+9>`, `<Alt+->`</span></span>
- <span data-ttu-id="cc43d-614">Emacs: `<Alt+0>` , `<Alt+1>` , `<Alt+2>` , `<Alt+3>` , `<Alt+4>` , `<Alt+5>` , `<Alt+6>` , `<Alt+7>` , `<Alt+8>` , `<Alt+9>` , `<Alt+->`</span><span class="sxs-lookup"><span data-stu-id="cc43d-614">Emacs: `<Alt+0>`, `<Alt+1>`, `<Alt+2>`, `<Alt+3>`, `<Alt+4>`, `<Alt+5>`, `<Alt+6>`, `<Alt+7>`, `<Alt+8>`, `<Alt+9>`, `<Alt+->`</span></span>
- <span data-ttu-id="cc43d-615">Режим команд VI: `<0>` , `<1>` , `<2>` , `<3>` , `<4>` , `<5>` , `<6>` , `<7>` , `<8>` , `<9>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-615">Vi command mode: `<0>`, `<1>`, `<2>`, `<3>`, `<4>`, `<5>`, `<6>`, `<7>`, `<8>`, `<9>`</span></span>

### <a name="invokeprompt"></a><span data-ttu-id="cc43d-616">инвокепромпт</span><span class="sxs-lookup"><span data-stu-id="cc43d-616">InvokePrompt</span></span>

<span data-ttu-id="cc43d-617">Стирает текущий запрос и вызывает функцию Prompt для повторного вывода запроса.</span><span class="sxs-lookup"><span data-stu-id="cc43d-617">Erases the current prompt and calls the prompt function to redisplay the prompt.</span></span> <span data-ttu-id="cc43d-618">Полезен для обработчиков пользовательских ключей, изменяющих состояние, например для изменения текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="cc43d-618">Useful for custom key handlers that change state, e.g. change the current directory.</span></span>

- <span data-ttu-id="cc43d-619">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="cc43d-619">Function is unbound.</span></span>

### <a name="scrolldisplaydown"></a><span data-ttu-id="cc43d-620">скроллдисплайдовн</span><span class="sxs-lookup"><span data-stu-id="cc43d-620">ScrollDisplayDown</span></span>

<span data-ttu-id="cc43d-621">Прокрутите экран вниз на один экран.</span><span class="sxs-lookup"><span data-stu-id="cc43d-621">Scroll the display down one screen.</span></span>

- <span data-ttu-id="cc43d-622">Процессор `<PageDown>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-622">Cmd: `<PageDown>`</span></span>
- <span data-ttu-id="cc43d-623">Emacs: `<PageDown>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-623">Emacs: `<PageDown>`</span></span>

### <a name="scrolldisplaydownline"></a><span data-ttu-id="cc43d-624">скроллдисплайдовнлине</span><span class="sxs-lookup"><span data-stu-id="cc43d-624">ScrollDisplayDownLine</span></span>

<span data-ttu-id="cc43d-625">Прокрутите экран вниз на одну строку.</span><span class="sxs-lookup"><span data-stu-id="cc43d-625">Scroll the display down one line.</span></span>

- <span data-ttu-id="cc43d-626">Процессор `<Ctrl+PageDown>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-626">Cmd: `<Ctrl+PageDown>`</span></span>
- <span data-ttu-id="cc43d-627">Emacs: `<Ctrl+PageDown>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-627">Emacs: `<Ctrl+PageDown>`</span></span>

### <a name="scrolldisplaytocursor"></a><span data-ttu-id="cc43d-628">скроллдисплайтокурсор</span><span class="sxs-lookup"><span data-stu-id="cc43d-628">ScrollDisplayToCursor</span></span>

<span data-ttu-id="cc43d-629">Прокрутить экран до курсора.</span><span class="sxs-lookup"><span data-stu-id="cc43d-629">Scroll the display to the cursor.</span></span>

- <span data-ttu-id="cc43d-630">Emacs: `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-630">Emacs: `<Ctrl+End>`</span></span>

### <a name="scrolldisplaytop"></a><span data-ttu-id="cc43d-631">скроллдисплайтоп</span><span class="sxs-lookup"><span data-stu-id="cc43d-631">ScrollDisplayTop</span></span>

<span data-ttu-id="cc43d-632">Прокрутите экран до верха.</span><span class="sxs-lookup"><span data-stu-id="cc43d-632">Scroll the display to the top.</span></span>

- <span data-ttu-id="cc43d-633">Emacs: `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-633">Emacs: `<Ctrl+Home>`</span></span>

### <a name="scrolldisplayup"></a><span data-ttu-id="cc43d-634">скроллдисплайуп</span><span class="sxs-lookup"><span data-stu-id="cc43d-634">ScrollDisplayUp</span></span>

<span data-ttu-id="cc43d-635">Прокрутите экран вверх на один экран.</span><span class="sxs-lookup"><span data-stu-id="cc43d-635">Scroll the display up one screen.</span></span>

- <span data-ttu-id="cc43d-636">Процессор `<PageUp>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-636">Cmd: `<PageUp>`</span></span>
- <span data-ttu-id="cc43d-637">Emacs: `<PageUp>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-637">Emacs: `<PageUp>`</span></span>

### <a name="scrolldisplayupline"></a><span data-ttu-id="cc43d-638">скроллдисплайуплине</span><span class="sxs-lookup"><span data-stu-id="cc43d-638">ScrollDisplayUpLine</span></span>

<span data-ttu-id="cc43d-639">Прокрутите экран вверх на одну строку.</span><span class="sxs-lookup"><span data-stu-id="cc43d-639">Scroll the display up one line.</span></span>

- <span data-ttu-id="cc43d-640">Процессор `<Ctrl+PageUp>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-640">Cmd: `<Ctrl+PageUp>`</span></span>
- <span data-ttu-id="cc43d-641">Emacs: `<Ctrl+PageUp>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-641">Emacs: `<Ctrl+PageUp>`</span></span>

### <a name="selfinsert"></a><span data-ttu-id="cc43d-642">селфинсерт</span><span class="sxs-lookup"><span data-stu-id="cc43d-642">SelfInsert</span></span>

<span data-ttu-id="cc43d-643">Вставьте ключ.</span><span class="sxs-lookup"><span data-stu-id="cc43d-643">Insert the key.</span></span>

- <span data-ttu-id="cc43d-644">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="cc43d-644">Function is unbound.</span></span>

### <a name="showkeybindings"></a><span data-ttu-id="cc43d-645">шовкэйбиндингс</span><span class="sxs-lookup"><span data-stu-id="cc43d-645">ShowKeyBindings</span></span>

<span data-ttu-id="cc43d-646">Отображение всех связанных ключей.</span><span class="sxs-lookup"><span data-stu-id="cc43d-646">Show all bound keys.</span></span>

- <span data-ttu-id="cc43d-647">Процессор `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-647">Cmd: `<Ctrl+Alt+?>`</span></span>
- <span data-ttu-id="cc43d-648">Emacs: `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-648">Emacs: `<Ctrl+Alt+?>`</span></span>
- <span data-ttu-id="cc43d-649">Режим вставки в VI: `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-649">Vi insert mode: `<Ctrl+Alt+?>`</span></span>

### <a name="vicommandmode"></a><span data-ttu-id="cc43d-650">викоммандмоде</span><span class="sxs-lookup"><span data-stu-id="cc43d-650">ViCommandMode</span></span>

<span data-ttu-id="cc43d-651">Переключите текущий режим работы с Vi-Insert на VI-Command.</span><span class="sxs-lookup"><span data-stu-id="cc43d-651">Switch the current operating mode from Vi-Insert to Vi-Command.</span></span>

- <span data-ttu-id="cc43d-652">Режим вставки в VI: `<Escape>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-652">Vi insert mode: `<Escape>`</span></span>

### <a name="vidigitargumentinchord"></a><span data-ttu-id="cc43d-653">видигитаргументинчорд</span><span class="sxs-lookup"><span data-stu-id="cc43d-653">ViDigitArgumentInChord</span></span>

<span data-ttu-id="cc43d-654">Начните новый числовой аргумент, чтобы передать его другим функциям в одной из сочетаний VI.</span><span class="sxs-lookup"><span data-stu-id="cc43d-654">Start a new digit argument to pass to other functions while in one of vi's chords.</span></span>

- <span data-ttu-id="cc43d-655">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="cc43d-655">Function is unbound.</span></span>

### <a name="vieditvisually"></a><span data-ttu-id="cc43d-656">виедитвисуалли</span><span class="sxs-lookup"><span data-stu-id="cc43d-656">ViEditVisually</span></span>

<span data-ttu-id="cc43d-657">Измените командную строку в текстовом редакторе, заданном $env: EDITOR или $env: VISUAL.</span><span class="sxs-lookup"><span data-stu-id="cc43d-657">Edit the command line in a text editor specified by $env:EDITOR or $env:VISUAL.</span></span>

- <span data-ttu-id="cc43d-658">Emacs: `<Ctrl+x,Ctrl+e>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-658">Emacs: `<Ctrl+x,Ctrl+e>`</span></span>
- <span data-ttu-id="cc43d-659">Режим команд VI: `<v>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-659">Vi command mode: `<v>`</span></span>

### <a name="viexit"></a><span data-ttu-id="cc43d-660">виексит</span><span class="sxs-lookup"><span data-stu-id="cc43d-660">ViExit</span></span>

<span data-ttu-id="cc43d-661">Завершает работу оболочки.</span><span class="sxs-lookup"><span data-stu-id="cc43d-661">Exits the shell.</span></span>

- <span data-ttu-id="cc43d-662">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="cc43d-662">Function is unbound.</span></span>

### <a name="viinsertmode"></a><span data-ttu-id="cc43d-663">виинсертмоде</span><span class="sxs-lookup"><span data-stu-id="cc43d-663">ViInsertMode</span></span>

<span data-ttu-id="cc43d-664">Переключитесь в режим вставки.</span><span class="sxs-lookup"><span data-stu-id="cc43d-664">Switch to Insert mode.</span></span>

- <span data-ttu-id="cc43d-665">Режим команд VI: `<i>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-665">Vi command mode: `<i>`</span></span>

### <a name="whatiskey"></a><span data-ttu-id="cc43d-666">вхатискэй</span><span class="sxs-lookup"><span data-stu-id="cc43d-666">WhatIsKey</span></span>

<span data-ttu-id="cc43d-667">Прочитайте ключ и расскажите, к чему привязан ключ.</span><span class="sxs-lookup"><span data-stu-id="cc43d-667">Read a key and tell me what the key is bound to.</span></span>

- <span data-ttu-id="cc43d-668">Процессор `<Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-668">Cmd: `<Alt+?>`</span></span>
- <span data-ttu-id="cc43d-669">Emacs: `<Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-669">Emacs: `<Alt+?>`</span></span>

## <a name="selection-functions"></a><span data-ttu-id="cc43d-670">Функции выбора</span><span class="sxs-lookup"><span data-stu-id="cc43d-670">Selection functions</span></span>

### <a name="exchangepointandmark"></a><span data-ttu-id="cc43d-671">ексчанжепоинтандмарк</span><span class="sxs-lookup"><span data-stu-id="cc43d-671">ExchangePointAndMark</span></span>

<span data-ttu-id="cc43d-672">Курсор помещается в позицию метки, а метка перемещается в положение курсора.</span><span class="sxs-lookup"><span data-stu-id="cc43d-672">The cursor is placed at the location of the mark and the mark is moved to the location of the cursor.</span></span>

- <span data-ttu-id="cc43d-673">Emacs: `<Ctrl+x,Ctrl+x>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-673">Emacs: `<Ctrl+x,Ctrl+x>`</span></span>

### <a name="selectall"></a><span data-ttu-id="cc43d-674">SelectAll</span><span class="sxs-lookup"><span data-stu-id="cc43d-674">SelectAll</span></span>

<span data-ttu-id="cc43d-675">Выделите всю строку.</span><span class="sxs-lookup"><span data-stu-id="cc43d-675">Select the entire line.</span></span>

- <span data-ttu-id="cc43d-676">Процессор `<Ctrl+a>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-676">Cmd: `<Ctrl+a>`</span></span>

### <a name="selectbackwardchar"></a><span data-ttu-id="cc43d-677">селектбакквардчар</span><span class="sxs-lookup"><span data-stu-id="cc43d-677">SelectBackwardChar</span></span>

<span data-ttu-id="cc43d-678">Настройка текущего выделения для включения предыдущего символа.</span><span class="sxs-lookup"><span data-stu-id="cc43d-678">Adjust the current selection to include the previous character.</span></span>

- <span data-ttu-id="cc43d-679">Процессор `<Shift+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-679">Cmd: `<Shift+LeftArrow>`</span></span>
- <span data-ttu-id="cc43d-680">Emacs: `<Shift+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-680">Emacs: `<Shift+LeftArrow>`</span></span>

### <a name="selectbackwardsline"></a><span data-ttu-id="cc43d-681">селектбакквардслине</span><span class="sxs-lookup"><span data-stu-id="cc43d-681">SelectBackwardsLine</span></span>

<span data-ttu-id="cc43d-682">Изменить текущее выделение, чтобы включить его от курсора до начала строки.</span><span class="sxs-lookup"><span data-stu-id="cc43d-682">Adjust the current selection to include from the cursor to the start of the line.</span></span>

- <span data-ttu-id="cc43d-683">Процессор `<Shift+Home>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-683">Cmd: `<Shift+Home>`</span></span>
- <span data-ttu-id="cc43d-684">Emacs: `<Shift+Home>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-684">Emacs: `<Shift+Home>`</span></span>

### <a name="selectbackwardword"></a><span data-ttu-id="cc43d-685">селектбакквардворд</span><span class="sxs-lookup"><span data-stu-id="cc43d-685">SelectBackwardWord</span></span>

<span data-ttu-id="cc43d-686">Настройка текущего выделения для включения предыдущего слова.</span><span class="sxs-lookup"><span data-stu-id="cc43d-686">Adjust the current selection to include the previous word.</span></span>

- <span data-ttu-id="cc43d-687">Процессор `<Shift+Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-687">Cmd: `<Shift+Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="cc43d-688">Emacs: `<Alt+B>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-688">Emacs: `<Alt+B>`</span></span>

### <a name="selectforwardchar"></a><span data-ttu-id="cc43d-689">селектфорвардчар</span><span class="sxs-lookup"><span data-stu-id="cc43d-689">SelectForwardChar</span></span>

<span data-ttu-id="cc43d-690">Измените текущее выделение, чтобы включить следующий символ.</span><span class="sxs-lookup"><span data-stu-id="cc43d-690">Adjust the current selection to include the next character.</span></span>

- <span data-ttu-id="cc43d-691">Процессор `<Shift+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-691">Cmd: `<Shift+RightArrow>`</span></span>
- <span data-ttu-id="cc43d-692">Emacs: `<Shift+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-692">Emacs: `<Shift+RightArrow>`</span></span>

### <a name="selectforwardword"></a><span data-ttu-id="cc43d-693">селектфорвардворд</span><span class="sxs-lookup"><span data-stu-id="cc43d-693">SelectForwardWord</span></span>

<span data-ttu-id="cc43d-694">Измените текущее выделение, чтобы включить следующее слово с помощью Форвардворд.</span><span class="sxs-lookup"><span data-stu-id="cc43d-694">Adjust the current selection to include the next word using ForwardWord.</span></span>

- <span data-ttu-id="cc43d-695">Emacs: `<Alt+F>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-695">Emacs: `<Alt+F>`</span></span>

### <a name="selectline"></a><span data-ttu-id="cc43d-696">селектлине</span><span class="sxs-lookup"><span data-stu-id="cc43d-696">SelectLine</span></span>

<span data-ttu-id="cc43d-697">Настройка текущего выделения для включения курсора в конец строки.</span><span class="sxs-lookup"><span data-stu-id="cc43d-697">Adjust the current selection to include from the cursor to the end of the line.</span></span>

- <span data-ttu-id="cc43d-698">Процессор `<Shift+End>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-698">Cmd: `<Shift+End>`</span></span>
- <span data-ttu-id="cc43d-699">Emacs: `<Shift+End>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-699">Emacs: `<Shift+End>`</span></span>

### <a name="selectnextword"></a><span data-ttu-id="cc43d-700">селектнекстворд</span><span class="sxs-lookup"><span data-stu-id="cc43d-700">SelectNextWord</span></span>

<span data-ttu-id="cc43d-701">Настройка текущего выделения для включения следующего слова.</span><span class="sxs-lookup"><span data-stu-id="cc43d-701">Adjust the current selection to include the next word.</span></span>

- <span data-ttu-id="cc43d-702">Процессор `<Shift+Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-702">Cmd: `<Shift+Ctrl+RightArrow>`</span></span>

### <a name="selectshellbackwardword"></a><span data-ttu-id="cc43d-703">селектшеллбакквардворд</span><span class="sxs-lookup"><span data-stu-id="cc43d-703">SelectShellBackwardWord</span></span>

<span data-ttu-id="cc43d-704">Измените текущее выделение, чтобы включить предыдущее слово с помощью Шеллбакквардворд.</span><span class="sxs-lookup"><span data-stu-id="cc43d-704">Adjust the current selection to include the previous word using ShellBackwardWord.</span></span>

- <span data-ttu-id="cc43d-705">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="cc43d-705">Function is unbound.</span></span>

### <a name="selectshellforwardword"></a><span data-ttu-id="cc43d-706">селектшеллфорвардворд</span><span class="sxs-lookup"><span data-stu-id="cc43d-706">SelectShellForwardWord</span></span>

<span data-ttu-id="cc43d-707">Измените текущее выделение, чтобы включить следующее слово с помощью Шеллфорвардворд.</span><span class="sxs-lookup"><span data-stu-id="cc43d-707">Adjust the current selection to include the next word using ShellForwardWord.</span></span>

- <span data-ttu-id="cc43d-708">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="cc43d-708">Function is unbound.</span></span>

### <a name="selectshellnextword"></a><span data-ttu-id="cc43d-709">селектшеллнекстворд</span><span class="sxs-lookup"><span data-stu-id="cc43d-709">SelectShellNextWord</span></span>

<span data-ttu-id="cc43d-710">Измените текущее выделение, чтобы включить следующее слово с помощью Шеллнекстворд.</span><span class="sxs-lookup"><span data-stu-id="cc43d-710">Adjust the current selection to include the next word using ShellNextWord.</span></span>

- <span data-ttu-id="cc43d-711">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="cc43d-711">Function is unbound.</span></span>

### <a name="setmark"></a><span data-ttu-id="cc43d-712">сетмарк</span><span class="sxs-lookup"><span data-stu-id="cc43d-712">SetMark</span></span>

<span data-ttu-id="cc43d-713">Пометка текущего положения курсора для использования в последующей команде редактирования.</span><span class="sxs-lookup"><span data-stu-id="cc43d-713">Mark the current location of the cursor for use in a subsequent editing command.</span></span>

- <span data-ttu-id="cc43d-714">Emacs: `<Ctrl+`>\`</span><span class="sxs-lookup"><span data-stu-id="cc43d-714">Emacs: `<Ctrl+`>\`</span></span>

## <a name="search-functions"></a><span data-ttu-id="cc43d-715">Функции поиска</span><span class="sxs-lookup"><span data-stu-id="cc43d-715">Search functions</span></span>

### <a name="charactersearch"></a><span data-ttu-id="cc43d-716">чарактерсеарч</span><span class="sxs-lookup"><span data-stu-id="cc43d-716">CharacterSearch</span></span>

<span data-ttu-id="cc43d-717">Чтение символа и поиск вперед для следующего вхождения этого символа.</span><span class="sxs-lookup"><span data-stu-id="cc43d-717">Read a character and search forward for the next occurrence of that character.</span></span>
<span data-ttu-id="cc43d-718">Если указан аргумент, то для n-го вхождения выполните поиск вперед (или назад, если отрицательное).</span><span class="sxs-lookup"><span data-stu-id="cc43d-718">If an argument is specified, search forward (or backward if negative) for the nth occurrence.</span></span>

- <span data-ttu-id="cc43d-719">Процессор `<F3>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-719">Cmd: `<F3>`</span></span>
- <span data-ttu-id="cc43d-720">Emacs: `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-720">Emacs: `<Ctrl+]>`</span></span>
- <span data-ttu-id="cc43d-721">Режим вставки в VI: `<F3>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-721">Vi insert mode: `<F3>`</span></span>
- <span data-ttu-id="cc43d-722">Режим команд VI: `<F3>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-722">Vi command mode: `<F3>`</span></span>

### <a name="charactersearchbackward"></a><span data-ttu-id="cc43d-723">чарактерсеарчбакквард</span><span class="sxs-lookup"><span data-stu-id="cc43d-723">CharacterSearchBackward</span></span>

<span data-ttu-id="cc43d-724">Чтение символа и поиск следующего вхождения этого символа в обратном направлении.</span><span class="sxs-lookup"><span data-stu-id="cc43d-724">Read a character and search backward for the next occurrence of that character.</span></span> <span data-ttu-id="cc43d-725">Если аргумент указан, поиск в n-й последовательности осуществляется назад (или вперед, если отрицательное).</span><span class="sxs-lookup"><span data-stu-id="cc43d-725">If an argument is specified, search backward (or forward if negative) for the nth occurrence.</span></span>

- <span data-ttu-id="cc43d-726">Процессор `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-726">Cmd: `<Shift+F3>`</span></span>
- <span data-ttu-id="cc43d-727">Emacs: `<Ctrl+Alt+]>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-727">Emacs: `<Ctrl+Alt+]>`</span></span>
- <span data-ttu-id="cc43d-728">Режим вставки в VI: `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-728">Vi insert mode: `<Shift+F3>`</span></span>
- <span data-ttu-id="cc43d-729">Режим команд VI: `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-729">Vi command mode: `<Shift+F3>`</span></span>

### <a name="repeatlastcharsearch"></a><span data-ttu-id="cc43d-730">репеатластчарсеарч</span><span class="sxs-lookup"><span data-stu-id="cc43d-730">RepeatLastCharSearch</span></span>

<span data-ttu-id="cc43d-731">Повторите поиск последнего записанного символа.</span><span class="sxs-lookup"><span data-stu-id="cc43d-731">Repeat the last recorded character search.</span></span>

- <span data-ttu-id="cc43d-732">Режим команд VI: `<;>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-732">Vi command mode: `<;>`</span></span>

### <a name="repeatlastcharsearchbackwards"></a><span data-ttu-id="cc43d-733">репеатластчарсеарчбакквардс</span><span class="sxs-lookup"><span data-stu-id="cc43d-733">RepeatLastCharSearchBackwards</span></span>

<span data-ttu-id="cc43d-734">Повторите поиск последнего записанного символа, но в обратном направлении.</span><span class="sxs-lookup"><span data-stu-id="cc43d-734">Repeat the last recorded character search, but in the opposite direction.</span></span>

- <span data-ttu-id="cc43d-735">Режим команд VI: `<,>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-735">Vi command mode: `<,>`</span></span>

### <a name="repeatsearch"></a><span data-ttu-id="cc43d-736">репеатсеарч</span><span class="sxs-lookup"><span data-stu-id="cc43d-736">RepeatSearch</span></span>

<span data-ttu-id="cc43d-737">Повторите последний поиск в том же направлении, что и раньше.</span><span class="sxs-lookup"><span data-stu-id="cc43d-737">Repeat the last search in the same direction as before.</span></span>

- <span data-ttu-id="cc43d-738">Режим команд VI: `<n>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-738">Vi command mode: `<n>`</span></span>

### <a name="repeatsearchbackward"></a><span data-ttu-id="cc43d-739">репеатсеарчбакквард</span><span class="sxs-lookup"><span data-stu-id="cc43d-739">RepeatSearchBackward</span></span>

<span data-ttu-id="cc43d-740">Повторите последний поиск в том же направлении, что и раньше.</span><span class="sxs-lookup"><span data-stu-id="cc43d-740">Repeat the last search in the same direction as before.</span></span>

- <span data-ttu-id="cc43d-741">Режим команд VI: `<N>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-741">Vi command mode: `<N>`</span></span>

### <a name="searchchar"></a><span data-ttu-id="cc43d-742">сеарччар</span><span class="sxs-lookup"><span data-stu-id="cc43d-742">SearchChar</span></span>

<span data-ttu-id="cc43d-743">Прочитать следующий символ, затем найти его, перейти вперед, а затем отследить символ.</span><span class="sxs-lookup"><span data-stu-id="cc43d-743">Read the next character and then find it, going forward, and then back off a character.</span></span> <span data-ttu-id="cc43d-744">Это относится к функциональным возможностям.</span><span class="sxs-lookup"><span data-stu-id="cc43d-744">This is for 't' functionality.</span></span>

- <span data-ttu-id="cc43d-745">Режим команд VI: `<f>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-745">Vi command mode: `<f>`</span></span>

### <a name="searchcharbackward"></a><span data-ttu-id="cc43d-746">сеарччарбакквард</span><span class="sxs-lookup"><span data-stu-id="cc43d-746">SearchCharBackward</span></span>

<span data-ttu-id="cc43d-747">Прочитать следующий символ, а затем найти его, вернуться назад, а затем отследить символ.</span><span class="sxs-lookup"><span data-stu-id="cc43d-747">Read the next character and then find it, going backward, and then back off a character.</span></span> <span data-ttu-id="cc43d-748">Это относится к функциональным возможностям.</span><span class="sxs-lookup"><span data-stu-id="cc43d-748">This is for 'T' functionality.</span></span>

- <span data-ttu-id="cc43d-749">Режим команд VI: `<F>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-749">Vi command mode: `<F>`</span></span>

### <a name="searchcharbackwardwithbackoff"></a><span data-ttu-id="cc43d-750">сеарччарбакквардвисбаккофф</span><span class="sxs-lookup"><span data-stu-id="cc43d-750">SearchCharBackwardWithBackoff</span></span>

<span data-ttu-id="cc43d-751">Прочитать следующий символ, а затем найти его, вернуться назад, а затем отследить символ.</span><span class="sxs-lookup"><span data-stu-id="cc43d-751">Read the next character and then find it, going backward, and then back off a character.</span></span> <span data-ttu-id="cc43d-752">Это относится к функциональным возможностям.</span><span class="sxs-lookup"><span data-stu-id="cc43d-752">This is for 'T' functionality.</span></span>

- <span data-ttu-id="cc43d-753">Режим команд VI: `<T>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-753">Vi command mode: `<T>`</span></span>

### <a name="searchcharwithbackoff"></a><span data-ttu-id="cc43d-754">сеарччарвисбаккофф</span><span class="sxs-lookup"><span data-stu-id="cc43d-754">SearchCharWithBackoff</span></span>

<span data-ttu-id="cc43d-755">Прочитать следующий символ, затем найти его, перейти вперед, а затем отследить символ.</span><span class="sxs-lookup"><span data-stu-id="cc43d-755">Read the next character and then find it, going forward, and then back off a character.</span></span> <span data-ttu-id="cc43d-756">Это относится к функциональным возможностям.</span><span class="sxs-lookup"><span data-stu-id="cc43d-756">This is for 't' functionality.</span></span>

- <span data-ttu-id="cc43d-757">Режим команд VI: `<t>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-757">Vi command mode: `<t>`</span></span>

### <a name="searchforward"></a><span data-ttu-id="cc43d-758">сеарчфорвард</span><span class="sxs-lookup"><span data-stu-id="cc43d-758">SearchForward</span></span>

<span data-ttu-id="cc43d-759">Запрашивает строку поиска и инициирует поиск по запросу Акцептлине.</span><span class="sxs-lookup"><span data-stu-id="cc43d-759">Prompts for a search string and initiates search upon AcceptLine.</span></span>

- <span data-ttu-id="cc43d-760">Режим вставки в VI: `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-760">Vi insert mode: `<Ctrl+s>`</span></span>
- <span data-ttu-id="cc43d-761">Режим команд VI: `<?>` , `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="cc43d-761">Vi command mode: `<?>`, `<Ctrl+s>`</span></span>

## <a name="custom-key-bindings"></a><span data-ttu-id="cc43d-762">Пользовательские привязки клавиш</span><span class="sxs-lookup"><span data-stu-id="cc43d-762">Custom Key Bindings</span></span>

<span data-ttu-id="cc43d-763">PSReadLine поддерживает пользовательские привязки клавиш с помощью командлета `Set-PSReadLineKeyHandler` .</span><span class="sxs-lookup"><span data-stu-id="cc43d-763">PSReadLine supports custom key bindings using the cmdlet `Set-PSReadLineKeyHandler`.</span></span> <span data-ttu-id="cc43d-764">Большинство пользовательских привязок вызывают одну из приведенных выше функций, например</span><span class="sxs-lookup"><span data-stu-id="cc43d-764">Most custom key bindings call one of the above functions, for example</span></span>

```powershell
Set-PSReadLineKeyHandler -Key UpArrow -Function HistorySearchBackward
```

<span data-ttu-id="cc43d-765">Можно привязать ScriptBlock к ключу.</span><span class="sxs-lookup"><span data-stu-id="cc43d-765">You can bind a ScriptBlock to a key.</span></span> <span data-ttu-id="cc43d-766">Блок ScriptBlock может выполнять практически все необходимые действия.</span><span class="sxs-lookup"><span data-stu-id="cc43d-766">The ScriptBlock can do pretty much anything you want.</span></span> <span data-ttu-id="cc43d-767">Ниже приведены некоторые полезные примеры.</span><span class="sxs-lookup"><span data-stu-id="cc43d-767">Some useful examples include</span></span>

- <span data-ttu-id="cc43d-768">Изменение командной строки</span><span class="sxs-lookup"><span data-stu-id="cc43d-768">edit the command line</span></span>
- <span data-ttu-id="cc43d-769">Открытие нового окна (например, Справка)</span><span class="sxs-lookup"><span data-stu-id="cc43d-769">opening a new window (e.g. help)</span></span>
- <span data-ttu-id="cc43d-770">Изменение каталогов без изменения командной строки</span><span class="sxs-lookup"><span data-stu-id="cc43d-770">change directories without changing the command line</span></span>

<span data-ttu-id="cc43d-771">Блок ScriptBlock получает два аргумента:</span><span class="sxs-lookup"><span data-stu-id="cc43d-771">The ScriptBlock receives two arguments:</span></span>

- <span data-ttu-id="cc43d-772">`$key` — Объект **[консолекэйинфо]** , который является ключом, запускающим пользовательскую привязку.</span><span class="sxs-lookup"><span data-stu-id="cc43d-772">`$key` - A **[ConsoleKeyInfo]** object that is the key that triggered the custom binding.</span></span> <span data-ttu-id="cc43d-773">Если один и тот же блок сценария привязан к нескольким ключам и необходимо выполнять различные действия в зависимости от ключа, можно проверить $key.</span><span class="sxs-lookup"><span data-stu-id="cc43d-773">If you bind the same ScriptBlock to multiple keys and need to perform different actions depending on the key, you can check $key.</span></span> <span data-ttu-id="cc43d-774">Многие пользовательские привязки игнорируют этот аргумент.</span><span class="sxs-lookup"><span data-stu-id="cc43d-774">Many custom bindings ignore this argument.</span></span>

- <span data-ttu-id="cc43d-775">`$arg` — Произвольный аргумент.</span><span class="sxs-lookup"><span data-stu-id="cc43d-775">`$arg` - An arbitrary argument.</span></span> <span data-ttu-id="cc43d-776">Чаще всего это будет целочисленный аргумент, который пользователь передает из ключевых привязок Дигитаргумент.</span><span class="sxs-lookup"><span data-stu-id="cc43d-776">Most often, this would be an integer argument that the user passes from the key bindings DigitArgument.</span></span> <span data-ttu-id="cc43d-777">Если привязка не принимает аргументы, целесообразно проигнорировать этот аргумент.</span><span class="sxs-lookup"><span data-stu-id="cc43d-777">If your binding doesn't accept arguments, it's reasonable to ignore this argument.</span></span>

<span data-ttu-id="cc43d-778">Рассмотрим пример, который добавляет в журнал командную строку, не выполняя ее.</span><span class="sxs-lookup"><span data-stu-id="cc43d-778">Let's take a look at an example that adds a command line to history without executing it.</span></span> <span data-ttu-id="cc43d-779">Это полезно, если вы забыли сделать что-то, но не хотите повторно вводить уже введенную командную строку.</span><span class="sxs-lookup"><span data-stu-id="cc43d-779">This is useful when you realize you forgot to do something, but don't want to re-enter the command line you've already entered.</span></span>

```powershell
$parameters = @{
    Key = 'Alt+w'
    BriefDescription = 'SaveInHistory'
    LongDescription = 'Save current line in history but do not execute'
    ScriptBlock = {
      param($key, $arg)   # The arguments are ignored in this example

      # GetBufferState gives us the command line (with the cursor position)
      $line = $null
      $cursor = $null
      [Microsoft.PowerShell.PSConsoleReadLine]::GetBufferState([ref]$line,
        [ref]$cursor)

      # AddToHistory saves the line in history, but does not execute it.
      [Microsoft.PowerShell.PSConsoleReadLine]::AddToHistory($line)

      # RevertLine is like pressing Escape.
      [Microsoft.PowerShell.PSConsoleReadLine]::RevertLine()
  }
}
Set-PSReadLineKeyHandler @parameters
```

<span data-ttu-id="cc43d-780">В файле, `SamplePSReadLineProfile.ps1` который устанавливается в папку модуля PSReadLine, можно увидеть много других примеров.</span><span class="sxs-lookup"><span data-stu-id="cc43d-780">You can see many more examples in the file `SamplePSReadLineProfile.ps1` which is installed in the PSReadLine module folder.</span></span>

<span data-ttu-id="cc43d-781">Большинство ключевых привязок используют некоторые вспомогательные функции для редактирования командной строки.</span><span class="sxs-lookup"><span data-stu-id="cc43d-781">Most key bindings use some helper functions for editing the command line.</span></span>
<span data-ttu-id="cc43d-782">Эти API-интерфейсы описаны в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="cc43d-782">Those APIs are documented in the next section.</span></span>

## <a name="custom-key-binding-support-apis"></a><span data-ttu-id="cc43d-783">API поддержки пользовательского сочетания клавиш</span><span class="sxs-lookup"><span data-stu-id="cc43d-783">Custom Key Binding Support APIs</span></span>

<span data-ttu-id="cc43d-784">Следующие функции являются открытыми в Microsoft. PowerShell. Псконсолереадлине, но не могут быть напрямую привязаны к ключу.</span><span class="sxs-lookup"><span data-stu-id="cc43d-784">The following functions are public in Microsoft.PowerShell.PSConsoleReadLine, but cannot be directly bound to a key.</span></span> <span data-ttu-id="cc43d-785">Большинство из них удобно использовать в пользовательских привязках клавиш.</span><span class="sxs-lookup"><span data-stu-id="cc43d-785">Most are useful in custom key bindings.</span></span>

```csharp
void AddToHistory(string command)
```

<span data-ttu-id="cc43d-786">Добавьте командную строку в журнал, не выполняя ее.</span><span class="sxs-lookup"><span data-stu-id="cc43d-786">Add a command line to history without executing it.</span></span>

```csharp
void ClearKillRing()
```

<span data-ttu-id="cc43d-787">Снимите флажок Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="cc43d-787">Clear the kill-ring.</span></span>  <span data-ttu-id="cc43d-788">Это в основном используется для тестирования.</span><span class="sxs-lookup"><span data-stu-id="cc43d-788">This is mostly used for testing.</span></span>

```csharp
void Delete(int start, int length)
```

<span data-ttu-id="cc43d-789">Удалить символы длины из Start.</span><span class="sxs-lookup"><span data-stu-id="cc43d-789">Delete length characters from start.</span></span>  <span data-ttu-id="cc43d-790">Эта операция поддерживает операцию отмены и повтора.</span><span class="sxs-lookup"><span data-stu-id="cc43d-790">This operation supports undo/redo.</span></span>

```csharp
void Ding()
```

<span data-ttu-id="cc43d-791">Выполните действие DING, основанное на предпочтениях пользователей.</span><span class="sxs-lookup"><span data-stu-id="cc43d-791">Perform the Ding action based on the users preference.</span></span>

```csharp
void GetBufferState([ref] string input, [ref] int cursor)
void GetBufferState([ref] Ast ast, [ref] Token[] tokens,
  [ref] ParseError[] parseErrors, [ref] int cursor)
```

<span data-ttu-id="cc43d-792">Эти две функции извлекают полезную информацию о текущем состоянии входного буфера.</span><span class="sxs-lookup"><span data-stu-id="cc43d-792">These two functions retrieve useful information about the current state of the input buffer.</span></span>  <span data-ttu-id="cc43d-793">Первый из них чаще всего используется в простых случаях.</span><span class="sxs-lookup"><span data-stu-id="cc43d-793">The first is more commonly used for simple cases.</span></span>  <span data-ttu-id="cc43d-794">Второй используется, если привязка делает что-то более сложное с AST.</span><span class="sxs-lookup"><span data-stu-id="cc43d-794">The second is used if your binding is doing something more advanced with the Ast.</span></span>

```csharp
IEnumerable[Microsoft.PowerShell.KeyHandler]
  GetKeyHandlers(bool includeBound, bool includeUnbound)

```

<span data-ttu-id="cc43d-795">Эта функция используется Get-PSReadLineKeyHandler и, возможно, не полезна в пользовательской привязке ключа.</span><span class="sxs-lookup"><span data-stu-id="cc43d-795">This function is used by Get-PSReadLineKeyHandler and probably isn't useful in a custom key binding.</span></span>

```csharp
Microsoft.PowerShell.PSConsoleReadLineOptions GetOptions()
```

<span data-ttu-id="cc43d-796">Эта функция используется Get-PSReadLineOption и, возможно, не слишком полезна в пользовательской привязке ключа.</span><span class="sxs-lookup"><span data-stu-id="cc43d-796">This function is used by Get-PSReadLineOption and probably isn't too useful in a custom key binding.</span></span>

```csharp
void GetSelectionState([ref] int start, [ref] int length)
```

<span data-ttu-id="cc43d-797">Если в командной строке ничего не выбрано, значение-1 будет возвращено как в начале, так и в длине.</span><span class="sxs-lookup"><span data-stu-id="cc43d-797">If there is no selection on the command line, -1 will be returned in both start and length.</span></span> <span data-ttu-id="cc43d-798">Если в командной строке имеется выделенный фрагмент, то начинается и длина выбора возвращается.</span><span class="sxs-lookup"><span data-stu-id="cc43d-798">If there is a selection on the command line, the start and length of the selection are returned.</span></span>

```csharp
void Insert(char c)
void Insert(string s)
```

<span data-ttu-id="cc43d-799">Вставка символа или строки в курсоре.</span><span class="sxs-lookup"><span data-stu-id="cc43d-799">Insert a character or string at the cursor.</span></span>  <span data-ttu-id="cc43d-800">Эта операция поддерживает операцию отмены и повтора.</span><span class="sxs-lookup"><span data-stu-id="cc43d-800">This operation supports undo/redo.</span></span>

```csharp
string ReadLine(runspace remoteRunspace,
  System.Management.Automation.EngineIntrinsics engineIntrinsics)
```

<span data-ttu-id="cc43d-801">Это Главная точка входа для PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="cc43d-801">This is the main entry point to PSReadLine.</span></span> <span data-ttu-id="cc43d-802">Она не поддерживает рекурсию, поэтому она не полезна в пользовательской привязке ключа.</span><span class="sxs-lookup"><span data-stu-id="cc43d-802">It does not support recursion, so is not useful in a custom key binding.</span></span>

```csharp
void RemoveKeyHandler(string[] key)
```

<span data-ttu-id="cc43d-803">Эта функция используется Remove-PSReadLineKeyHandler и, возможно, не слишком полезна в пользовательской привязке ключа.</span><span class="sxs-lookup"><span data-stu-id="cc43d-803">This function is used by Remove-PSReadLineKeyHandler and probably isn't too useful in a custom key binding.</span></span>

```csharp
void Replace(int start, int length, string replacement)
```

<span data-ttu-id="cc43d-804">Замените некоторые входные данные.</span><span class="sxs-lookup"><span data-stu-id="cc43d-804">Replace some of the input.</span></span> <span data-ttu-id="cc43d-805">Эта операция поддерживает операцию отмены и повтора.</span><span class="sxs-lookup"><span data-stu-id="cc43d-805">This operation supports undo/redo.</span></span> <span data-ttu-id="cc43d-806">Это предпочтительнее удаление с последующим вставкой, так как оно обрабатывается как одно действие для отмены.</span><span class="sxs-lookup"><span data-stu-id="cc43d-806">This is preferred over Delete followed by Insert because it is treated as a single action for undo.</span></span>

```csharp
void SetCursorPosition(int cursor)
```

<span data-ttu-id="cc43d-807">Переместить курсор к заданному смещению.</span><span class="sxs-lookup"><span data-stu-id="cc43d-807">Move the cursor to the given offset.</span></span> <span data-ttu-id="cc43d-808">Перемещение курсора не ведется для отмены.</span><span class="sxs-lookup"><span data-stu-id="cc43d-808">Cursor movement is not tracked for undo.</span></span>

```csharp
void SetOptions(Microsoft.PowerShell.SetPSReadLineOption options)
```

<span data-ttu-id="cc43d-809">Эта функция является вспомогательным методом, используемым командлетом Set-PSReadLineOption, но может быть полезен для пользовательской привязки ключа, которая хочет временно изменить параметр.</span><span class="sxs-lookup"><span data-stu-id="cc43d-809">This function is a helper method used by the cmdlet Set-PSReadLineOption, but might be useful to a custom key binding that wants to temporarily change a setting.</span></span>

```csharp
bool TryGetArgAsInt(System.Object arg, [ref] int numericArg,
  int defaultNumericArg)
```

<span data-ttu-id="cc43d-810">Этот вспомогательный метод используется для пользовательских привязок, которые учитывают Дигитаргумент.</span><span class="sxs-lookup"><span data-stu-id="cc43d-810">This helper method is used for custom bindings that honor DigitArgument.</span></span> <span data-ttu-id="cc43d-811">Обычный вызов выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="cc43d-811">A typical call looks like</span></span>

```powershell
[int]$numericArg = 0
[Microsoft.PowerShell.PSConsoleReadLine]::TryGetArgAsInt($arg,
  [ref]$numericArg, 1)
```

## <a name="note"></a><span data-ttu-id="cc43d-812">ПРИМЕЧАНИЕ</span><span class="sxs-lookup"><span data-stu-id="cc43d-812">NOTE</span></span>

### <a name="powershell-compatibility"></a><span data-ttu-id="cc43d-813">СОВМЕСТИМОСТЬ С POWERSHELL</span><span class="sxs-lookup"><span data-stu-id="cc43d-813">POWERSHELL COMPATIBILITY</span></span>

<span data-ttu-id="cc43d-814">Для PSReadLine требуется PowerShell 3,0, более поздней версии и узел консоли.</span><span class="sxs-lookup"><span data-stu-id="cc43d-814">PSReadLine requires PowerShell 3.0, or newer, and the console host.</span></span> <span data-ttu-id="cc43d-815">Он не работает в интегрированной среде сценариев PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cc43d-815">It does not work in PowerShell ISE.</span></span> <span data-ttu-id="cc43d-816">Она работает в консоли Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="cc43d-816">It does work in the console of Visual Studio Code.</span></span>

### <a name="command-history"></a><span data-ttu-id="cc43d-817">ЖУРНАЛ КОМАНД</span><span class="sxs-lookup"><span data-stu-id="cc43d-817">COMMAND HISTORY</span></span>

<span data-ttu-id="cc43d-818">PSReadLine поддерживает файл журнала, содержащий все команды и данные, введенные из командной строки.</span><span class="sxs-lookup"><span data-stu-id="cc43d-818">PSReadLine maintains a history file containing all the commands and data you have entered from the command line.</span></span> <span data-ttu-id="cc43d-819">Это может быть конфиденциальные данные, включая пароли.</span><span class="sxs-lookup"><span data-stu-id="cc43d-819">This may contain sensitive data including passwords.</span></span> <span data-ttu-id="cc43d-820">Например, при использовании `ConvertTo-SecureString` командлета пароль заносится в файл журнала в виде обычного текста.</span><span class="sxs-lookup"><span data-stu-id="cc43d-820">For example, if you use the `ConvertTo-SecureString` cmdlet the password is logged in the history file as plain text.</span></span> <span data-ttu-id="cc43d-821">Файлы журнала — это файл с именем `$($host.Name)_history.txt` .</span><span class="sxs-lookup"><span data-stu-id="cc43d-821">The history files is a file named `$($host.Name)_history.txt`.</span></span> <span data-ttu-id="cc43d-822">В системах Windows файл журнала хранится в файле `$env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine` .</span><span class="sxs-lookup"><span data-stu-id="cc43d-822">On Windows systems the history file is stored at `$env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine`.</span></span>

### <a name="feedback--contributing-to-psreadline"></a><span data-ttu-id="cc43d-823">ОБРАТная связь & участие в PSReadLine</span><span class="sxs-lookup"><span data-stu-id="cc43d-823">FEEDBACK & CONTRIBUTING TO PSReadLine</span></span>

[<span data-ttu-id="cc43d-824">PSReadLine на GitHub</span><span class="sxs-lookup"><span data-stu-id="cc43d-824">PSReadLine on GitHub</span></span>](https://github.com/PowerShell/PSReadLine)

<span data-ttu-id="cc43d-825">Вы можете отправить запрос на вытягивание или отправить отзыв на страницу GitHub.</span><span class="sxs-lookup"><span data-stu-id="cc43d-825">Feel free to submit a pull request or submit feedback on the GitHub page.</span></span>

## <a name="see-also"></a><span data-ttu-id="cc43d-826">СМ. ТАКЖЕ</span><span class="sxs-lookup"><span data-stu-id="cc43d-826">SEE ALSO</span></span>

<span data-ttu-id="cc43d-827">На PSReadLine сильно влияют библиотеки GNU [ReadLine](https://tiswww.case.edu/php/chet/readline/rltop.html) .</span><span class="sxs-lookup"><span data-stu-id="cc43d-827">PSReadLine is heavily influenced by the GNU [readline](https://tiswww.case.edu/php/chet/readline/rltop.html) library.</span></span>
