---
description: PSReadLine предоставляет улучшенные возможности редактирования командной строки в консоли PowerShell.
keywords: powershell
Locale: en-US
ms.date: 11/16/2020
online version: https://docs.microsoft.com/powershell/module/psreadline/about/about_psreadline?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: О PSReadLine
ms.openlocfilehash: 25fc3a9a814728057b1ebc7e721d3fba84ae72c2
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "94692315"
---
# <a name="psreadline"></a><span data-ttu-id="8c299-104">PSReadLine</span><span class="sxs-lookup"><span data-stu-id="8c299-104">PSReadLine</span></span>

## <a name="about_psreadline"></a><span data-ttu-id="8c299-105">about_PSReadLine</span><span class="sxs-lookup"><span data-stu-id="8c299-105">about_PSReadLine</span></span>

## <a name="short-description"></a><span data-ttu-id="8c299-106">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="8c299-106">Short Description</span></span>

<span data-ttu-id="8c299-107">PSReadLine предоставляет улучшенные возможности редактирования командной строки в консоли PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8c299-107">PSReadLine provides an improved command-line editing experience in the PowerShell console.</span></span>

## <a name="long-description"></a><span data-ttu-id="8c299-108">Полное описание</span><span class="sxs-lookup"><span data-stu-id="8c299-108">Long Description</span></span>

<span data-ttu-id="8c299-109">PSReadLine 2,0 предоставляет широкие возможности редактирования командной строки для консоли PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8c299-109">PSReadLine 2.0 provides a powerful command-line editing experience for the PowerShell console.</span></span> <span data-ttu-id="8c299-110">Консоль предоставляет следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="8c299-110">It provides:</span></span>

- <span data-ttu-id="8c299-111">Цветовое выделение синтаксиса командной строки</span><span class="sxs-lookup"><span data-stu-id="8c299-111">Syntax coloring of the command line</span></span>
- <span data-ttu-id="8c299-112">Визуальное обозначение синтаксических ошибок</span><span class="sxs-lookup"><span data-stu-id="8c299-112">A visual indication of syntax errors</span></span>
- <span data-ttu-id="8c299-113">Более эффективный многострочный интерфейс (как редактирование, так и журнал)</span><span class="sxs-lookup"><span data-stu-id="8c299-113">A better multi-line experience (both editing and history)</span></span>
- <span data-ttu-id="8c299-114">Настраиваемые сочетания клавиш</span><span class="sxs-lookup"><span data-stu-id="8c299-114">Customizable key bindings</span></span>
- <span data-ttu-id="8c299-115">Режимы работы cmd и Emacs</span><span class="sxs-lookup"><span data-stu-id="8c299-115">Cmd and Emacs modes</span></span>
- <span data-ttu-id="8c299-116">Множество параметров конфигурации</span><span class="sxs-lookup"><span data-stu-id="8c299-116">Many configuration options</span></span>
- <span data-ttu-id="8c299-117">Завершение стиля bash (необязательно в режиме cmd, по умолчанию в режиме Emacs)</span><span class="sxs-lookup"><span data-stu-id="8c299-117">Bash style completion (optional in Cmd mode, default in Emacs mode)</span></span>
- <span data-ttu-id="8c299-118">Emacs: Янк/Kill-Ring</span><span class="sxs-lookup"><span data-stu-id="8c299-118">Emacs yank/kill-ring</span></span>
- <span data-ttu-id="8c299-119">Перемещение и уничтожение токена PowerShell на основе маркеров "Word"</span><span class="sxs-lookup"><span data-stu-id="8c299-119">PowerShell token based "word" movement and kill</span></span>

<span data-ttu-id="8c299-120">Для PSReadLine требуется PowerShell 3,0, более поздней версии и узел консоли.</span><span class="sxs-lookup"><span data-stu-id="8c299-120">PSReadLine requires PowerShell 3.0, or newer, and the console host.</span></span> <span data-ttu-id="8c299-121">Он не работает в интегрированной среде сценариев PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8c299-121">It does not work in PowerShell ISE.</span></span> <span data-ttu-id="8c299-122">Она работает в консоли Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="8c299-122">It does work in the console of Visual Studio Code.</span></span>

<span data-ttu-id="8c299-123">В классе **[Microsoft. PowerShell. псконсолереадлине]** доступны следующие функции.</span><span class="sxs-lookup"><span data-stu-id="8c299-123">The following functions are available in the class **[Microsoft.PowerShell.PSConsoleReadLine]**.</span></span>

## <a name="basic-editing-functions"></a><span data-ttu-id="8c299-124">Базовые функции редактирования</span><span class="sxs-lookup"><span data-stu-id="8c299-124">Basic editing functions</span></span>

### <a name="abort"></a><span data-ttu-id="8c299-125">Прерывание</span><span class="sxs-lookup"><span data-stu-id="8c299-125">Abort</span></span>

<span data-ttu-id="8c299-126">Прервать текущее действие, например добавочный поиск по журналу.</span><span class="sxs-lookup"><span data-stu-id="8c299-126">Abort current action, e.g. incremental history search.</span></span>

- <span data-ttu-id="8c299-127">Emacs: `<Ctrl+g>`</span><span class="sxs-lookup"><span data-stu-id="8c299-127">Emacs: `<Ctrl+g>`</span></span>

### <a name="acceptandgetnext"></a><span data-ttu-id="8c299-128">акцептанджетнекст</span><span class="sxs-lookup"><span data-stu-id="8c299-128">AcceptAndGetNext</span></span>

<span data-ttu-id="8c299-129">Попытка выполнить текущий вход.</span><span class="sxs-lookup"><span data-stu-id="8c299-129">Attempt to execute the current input.</span></span> <span data-ttu-id="8c299-130">Если его можно выполнить (например, Акцептлине), то следует отозвать следующий элемент из журнала при следующем вызове метода ReadLine.</span><span class="sxs-lookup"><span data-stu-id="8c299-130">If it can be executed (like AcceptLine), then recall the next item from history the next time ReadLine is called.</span></span>

- <span data-ttu-id="8c299-131">Emacs: `<Ctrl+o>`</span><span class="sxs-lookup"><span data-stu-id="8c299-131">Emacs: `<Ctrl+o>`</span></span>

### <a name="acceptline"></a><span data-ttu-id="8c299-132">акцептлине</span><span class="sxs-lookup"><span data-stu-id="8c299-132">AcceptLine</span></span>

<span data-ttu-id="8c299-133">Попытка выполнить текущий вход.</span><span class="sxs-lookup"><span data-stu-id="8c299-133">Attempt to execute the current input.</span></span> <span data-ttu-id="8c299-134">Если текущий ввод неполон (например, отсутствует закрывающая круглая скобка, квадратная скобка или кавычка, запрос продолжения отображается на следующей строке, а PSReadLine ожидает ввода ключей для изменения текущих входных данных.</span><span class="sxs-lookup"><span data-stu-id="8c299-134">If the current input is incomplete (for example there is a missing closing parenthesis, bracket, or quote, then the continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span>

- <span data-ttu-id="8c299-135">Процессор `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="8c299-135">Cmd: `<Enter>`</span></span>
- <span data-ttu-id="8c299-136">Emacs: `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="8c299-136">Emacs: `<Enter>`</span></span>
- <span data-ttu-id="8c299-137">Режим вставки в VI: `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="8c299-137">Vi insert mode: `<Enter>`</span></span>

### <a name="addline"></a><span data-ttu-id="8c299-138">аддлине</span><span class="sxs-lookup"><span data-stu-id="8c299-138">AddLine</span></span>

<span data-ttu-id="8c299-139">Запрос продолжения отображается на следующей строке, а PSReadLine ожидает ввода ключей для изменения текущих входных данных.</span><span class="sxs-lookup"><span data-stu-id="8c299-139">The continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span> <span data-ttu-id="8c299-140">Это полезно для ввода многострочных входных данных в виде одной команды, даже если одна строка завершается самим вводом.</span><span class="sxs-lookup"><span data-stu-id="8c299-140">This is useful to enter multi-line input as a single command even when a single line is complete input by itself.</span></span>

- <span data-ttu-id="8c299-141">Процессор `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="8c299-141">Cmd: `<Shift+Enter>`</span></span>
- <span data-ttu-id="8c299-142">Emacs: `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="8c299-142">Emacs: `<Shift+Enter>`</span></span>
- <span data-ttu-id="8c299-143">Режим вставки в VI: `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="8c299-143">Vi insert mode: `<Shift+Enter>`</span></span>
- <span data-ttu-id="8c299-144">Режим команд VI: `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="8c299-144">Vi command mode: `<Shift+Enter>`</span></span>

### <a name="backwarddeletechar"></a><span data-ttu-id="8c299-145">бакквардделетечар</span><span class="sxs-lookup"><span data-stu-id="8c299-145">BackwardDeleteChar</span></span>

<span data-ttu-id="8c299-146">Удалить символ перед курсором.</span><span class="sxs-lookup"><span data-stu-id="8c299-146">Delete the character before the cursor.</span></span>

- <span data-ttu-id="8c299-147">Cmd: `<Backspace>` , `<Ctrl+h>`</span><span class="sxs-lookup"><span data-stu-id="8c299-147">Cmd: `<Backspace>`, `<Ctrl+h>`</span></span>
- <span data-ttu-id="8c299-148">Emacs: `<Backspace>` , `<Ctrl+Backspace>` , `<Ctrl+h>`</span><span class="sxs-lookup"><span data-stu-id="8c299-148">Emacs: `<Backspace>`, `<Ctrl+Backspace>`, `<Ctrl+h>`</span></span>
- <span data-ttu-id="8c299-149">Режим вставки в VI: `<Backspace>`</span><span class="sxs-lookup"><span data-stu-id="8c299-149">Vi insert mode: `<Backspace>`</span></span>
- <span data-ttu-id="8c299-150">Режим команд VI: `<X>` , `<d,h>`</span><span class="sxs-lookup"><span data-stu-id="8c299-150">Vi command mode: `<X>`, `<d,h>`</span></span>

### <a name="backwarddeleteline"></a><span data-ttu-id="8c299-151">бакквардделетелине</span><span class="sxs-lookup"><span data-stu-id="8c299-151">BackwardDeleteLine</span></span>

<span data-ttu-id="8c299-152">Like Бакквардкилллине — удаляет текст с точки до начала строки, но не помещает удаленный текст в инструкцию KILL-Ring.</span><span class="sxs-lookup"><span data-stu-id="8c299-152">Like BackwardKillLine - deletes text from the point to the start of the line, but does not put the deleted text in the kill-ring.</span></span>

- <span data-ttu-id="8c299-153">Процессор `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="8c299-153">Cmd: `<Ctrl+Home>`</span></span>
- <span data-ttu-id="8c299-154">Режим вставки в VI: `<Ctrl+u>` , `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="8c299-154">Vi insert mode: `<Ctrl+u>`, `<Ctrl+Home>`</span></span>
- <span data-ttu-id="8c299-155">Режим команд VI: `<Ctrl+u>` , `<Ctrl+Home>` , `<d,0>`</span><span class="sxs-lookup"><span data-stu-id="8c299-155">Vi command mode: `<Ctrl+u>`, `<Ctrl+Home>`, `<d,0>`</span></span>

### <a name="backwarddeleteword"></a><span data-ttu-id="8c299-156">бакквардделетеворд</span><span class="sxs-lookup"><span data-stu-id="8c299-156">BackwardDeleteWord</span></span>

<span data-ttu-id="8c299-157">Удаляет предыдущее слово.</span><span class="sxs-lookup"><span data-stu-id="8c299-157">Deletes the previous word.</span></span>

- <span data-ttu-id="8c299-158">Режим команд VI: `<Ctrl+w>` , `<d,b>`</span><span class="sxs-lookup"><span data-stu-id="8c299-158">Vi command mode: `<Ctrl+w>`, `<d,b>`</span></span>

### <a name="backwardkillline"></a><span data-ttu-id="8c299-159">бакквардкилллине</span><span class="sxs-lookup"><span data-stu-id="8c299-159">BackwardKillLine</span></span>

<span data-ttu-id="8c299-160">Очистить входные данные от начала ввода до курсора.</span><span class="sxs-lookup"><span data-stu-id="8c299-160">Clear the input from the start of the input to the cursor.</span></span> <span data-ttu-id="8c299-161">Очистка текста помещается в буфер Kill.</span><span class="sxs-lookup"><span data-stu-id="8c299-161">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="8c299-162">Emacs: `<Ctrl+u>` , `<Ctrl+x,Backspace>`</span><span class="sxs-lookup"><span data-stu-id="8c299-162">Emacs: `<Ctrl+u>`, `<Ctrl+x,Backspace>`</span></span>

### <a name="backwardkillword"></a><span data-ttu-id="8c299-163">бакквардкиллворд</span><span class="sxs-lookup"><span data-stu-id="8c299-163">BackwardKillWord</span></span>

<span data-ttu-id="8c299-164">Очистить ввод от начала текущего слова до курсора.</span><span class="sxs-lookup"><span data-stu-id="8c299-164">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="8c299-165">Если курсор находится между словами, входные данные очищаются от начала предыдущего слова до курсора.</span><span class="sxs-lookup"><span data-stu-id="8c299-165">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="8c299-166">Очистка текста помещается в буфер Kill.</span><span class="sxs-lookup"><span data-stu-id="8c299-166">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="8c299-167">Процессор `<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="8c299-167">Cmd: `<Ctrl+Backspace>`</span></span>
- <span data-ttu-id="8c299-168">Emacs: `<Alt+Backspace>` , `<Escape,Backspace>`</span><span class="sxs-lookup"><span data-stu-id="8c299-168">Emacs: `<Alt+Backspace>`, `<Escape,Backspace>`</span></span>
- <span data-ttu-id="8c299-169">Режим вставки в VI: `<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="8c299-169">Vi insert mode: `<Ctrl+Backspace>`</span></span>
- <span data-ttu-id="8c299-170">Режим команд VI: `<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="8c299-170">Vi command mode: `<Ctrl+Backspace>`</span></span>

### <a name="cancelline"></a><span data-ttu-id="8c299-171">канцеллине</span><span class="sxs-lookup"><span data-stu-id="8c299-171">CancelLine</span></span>

<span data-ttu-id="8c299-172">Отмена текущих входных данных с выходом на экран, но возврат к узлу, чтобы снова выполнить оценку запроса.</span><span class="sxs-lookup"><span data-stu-id="8c299-172">Cancel the current input, leaving the input on the screen, but returns back to the host so the prompt is evaluated again.</span></span>

- <span data-ttu-id="8c299-173">Режим вставки в VI: `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="8c299-173">Vi insert mode: `<Ctrl+c>`</span></span>
- <span data-ttu-id="8c299-174">Режим команд VI: `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="8c299-174">Vi command mode: `<Ctrl+c>`</span></span>

### <a name="copy"></a><span data-ttu-id="8c299-175">Копировать</span><span class="sxs-lookup"><span data-stu-id="8c299-175">Copy</span></span>

<span data-ttu-id="8c299-176">Копировать выбранный регион в буфер обмена системы.</span><span class="sxs-lookup"><span data-stu-id="8c299-176">Copy selected region to the system clipboard.</span></span> <span data-ttu-id="8c299-177">Если регион не выбран, скопируйте всю строку.</span><span class="sxs-lookup"><span data-stu-id="8c299-177">If no region is selected, copy the whole line.</span></span>

- <span data-ttu-id="8c299-178">Процессор `<Ctrl+C>`</span><span class="sxs-lookup"><span data-stu-id="8c299-178">Cmd: `<Ctrl+C>`</span></span>

### <a name="copyorcancelline"></a><span data-ttu-id="8c299-179">копйорканцеллине</span><span class="sxs-lookup"><span data-stu-id="8c299-179">CopyOrCancelLine</span></span>

<span data-ttu-id="8c299-180">Если выбран текст, скопируйте в буфер обмена, в противном случае отмените строку.</span><span class="sxs-lookup"><span data-stu-id="8c299-180">If text is selected, copy to the clipboard, otherwise cancel the line.</span></span>

- <span data-ttu-id="8c299-181">Процессор `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="8c299-181">Cmd: `<Ctrl+c>`</span></span>
- <span data-ttu-id="8c299-182">Emacs: `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="8c299-182">Emacs: `<Ctrl+c>`</span></span>

### <a name="cut"></a><span data-ttu-id="8c299-183">Вырезать</span><span class="sxs-lookup"><span data-stu-id="8c299-183">Cut</span></span>

<span data-ttu-id="8c299-184">Удалить выбранный регион, поместив удаленный текст в системный буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="8c299-184">Delete selected region placing deleted text in the system clipboard.</span></span>

- <span data-ttu-id="8c299-185">Процессор `<Ctrl+x>`</span><span class="sxs-lookup"><span data-stu-id="8c299-185">Cmd: `<Ctrl+x>`</span></span>

### <a name="deletechar"></a><span data-ttu-id="8c299-186">делетечар</span><span class="sxs-lookup"><span data-stu-id="8c299-186">DeleteChar</span></span>

<span data-ttu-id="8c299-187">Удалите символ под курсором.</span><span class="sxs-lookup"><span data-stu-id="8c299-187">Delete the character under the cursor.</span></span>

- <span data-ttu-id="8c299-188">Процессор `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="8c299-188">Cmd: `<Delete>`</span></span>
- <span data-ttu-id="8c299-189">Emacs: `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="8c299-189">Emacs: `<Delete>`</span></span>
- <span data-ttu-id="8c299-190">Режим вставки в VI: `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="8c299-190">Vi insert mode: `<Delete>`</span></span>
- <span data-ttu-id="8c299-191">Режим команд VI: `<Delete>` , `<x>` , `<d,l>` , `<d,Space>`</span><span class="sxs-lookup"><span data-stu-id="8c299-191">Vi command mode: `<Delete>`, `<x>`, `<d,l>`, `<d,Space>`</span></span>

### <a name="deletecharorexit"></a><span data-ttu-id="8c299-192">делетечарорексит</span><span class="sxs-lookup"><span data-stu-id="8c299-192">DeleteCharOrExit</span></span>

<span data-ttu-id="8c299-193">Удалите символ под курсором или, если строка пуста, завершите процесс.</span><span class="sxs-lookup"><span data-stu-id="8c299-193">Delete the character under the cursor, or if the line is empty, exit the process.</span></span>

- <span data-ttu-id="8c299-194">Emacs: `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="8c299-194">Emacs: `<Ctrl+d>`</span></span>

### <a name="deleteendofword"></a><span data-ttu-id="8c299-195">делетиндофворд</span><span class="sxs-lookup"><span data-stu-id="8c299-195">DeleteEndOfWord</span></span>

<span data-ttu-id="8c299-196">Удалить до конца слова.</span><span class="sxs-lookup"><span data-stu-id="8c299-196">Delete to the end of the word.</span></span>

- <span data-ttu-id="8c299-197">Режим команд VI: `<d,e>`</span><span class="sxs-lookup"><span data-stu-id="8c299-197">Vi command mode: `<d,e>`</span></span>

### <a name="deleteline"></a><span data-ttu-id="8c299-198">Сбой deleteline</span><span class="sxs-lookup"><span data-stu-id="8c299-198">DeleteLine</span></span>

<span data-ttu-id="8c299-199">Удаляет текущую строку, включая отмену.</span><span class="sxs-lookup"><span data-stu-id="8c299-199">Deletes the current line, enabling undo.</span></span>

- <span data-ttu-id="8c299-200">Режим команд VI: `<d,d>`</span><span class="sxs-lookup"><span data-stu-id="8c299-200">Vi command mode: `<d,d>`</span></span>

### <a name="deletelinetofirstchar"></a><span data-ttu-id="8c299-201">делетелинетофирстчар</span><span class="sxs-lookup"><span data-stu-id="8c299-201">DeleteLineToFirstChar</span></span>

<span data-ttu-id="8c299-202">Удаляет текст из курсора на первый символ строки, отличный от пробела.</span><span class="sxs-lookup"><span data-stu-id="8c299-202">Deletes text from the cursor to the first non-blank character of the line.</span></span>

- <span data-ttu-id="8c299-203">Режим команд VI: `<d,^>`</span><span class="sxs-lookup"><span data-stu-id="8c299-203">Vi command mode: `<d,^>`</span></span>

### <a name="deletetoend"></a><span data-ttu-id="8c299-204">делететоенд</span><span class="sxs-lookup"><span data-stu-id="8c299-204">DeleteToEnd</span></span>

<span data-ttu-id="8c299-205">Удалить до конца строки.</span><span class="sxs-lookup"><span data-stu-id="8c299-205">Delete to the end of the line.</span></span>

- <span data-ttu-id="8c299-206">Режим команд VI: `<D>` , `<d,$>`</span><span class="sxs-lookup"><span data-stu-id="8c299-206">Vi command mode: `<D>`, `<d,$>`</span></span>

### <a name="deleteword"></a><span data-ttu-id="8c299-207">DeleteWord</span><span class="sxs-lookup"><span data-stu-id="8c299-207">DeleteWord</span></span>

<span data-ttu-id="8c299-208">Удалить следующее слово.</span><span class="sxs-lookup"><span data-stu-id="8c299-208">Delete the next word.</span></span>

- <span data-ttu-id="8c299-209">Режим команд VI: `<d,w>`</span><span class="sxs-lookup"><span data-stu-id="8c299-209">Vi command mode: `<d,w>`</span></span>

### <a name="forwarddeleteline"></a><span data-ttu-id="8c299-210">форвардделетелине</span><span class="sxs-lookup"><span data-stu-id="8c299-210">ForwardDeleteLine</span></span>

<span data-ttu-id="8c299-211">Как и Форвардкилллине — удаляет текст с точки до конца строки, но не помещает удаленный текст в инструкцию KILL-Ring.</span><span class="sxs-lookup"><span data-stu-id="8c299-211">Like ForwardKillLine - deletes text from the point to the end of the line, but does not put the deleted text in the kill-ring.</span></span>

- <span data-ttu-id="8c299-212">Процессор `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="8c299-212">Cmd: `<Ctrl+End>`</span></span>
- <span data-ttu-id="8c299-213">Режим вставки в VI: `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="8c299-213">Vi insert mode: `<Ctrl+End>`</span></span>
- <span data-ttu-id="8c299-214">Режим команд VI: `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="8c299-214">Vi command mode: `<Ctrl+End>`</span></span>

### <a name="insertlineabove"></a><span data-ttu-id="8c299-215">инсертлинеабове</span><span class="sxs-lookup"><span data-stu-id="8c299-215">InsertLineAbove</span></span>

<span data-ttu-id="8c299-216">Новая пустая строка создается над текущей строкой, независимо от того, где находится курсор на текущей строке.</span><span class="sxs-lookup"><span data-stu-id="8c299-216">A new empty line is created above the current line regardless of where the cursor is on the current line.</span></span> <span data-ttu-id="8c299-217">Курсор переместится в начало новой строки.</span><span class="sxs-lookup"><span data-stu-id="8c299-217">The cursor moves to the beginning of the new line.</span></span>

- <span data-ttu-id="8c299-218">Процессор `<Ctrl+Enter>`</span><span class="sxs-lookup"><span data-stu-id="8c299-218">Cmd: `<Ctrl+Enter>`</span></span>

### <a name="insertlinebelow"></a><span data-ttu-id="8c299-219">инсертлинебелов</span><span class="sxs-lookup"><span data-stu-id="8c299-219">InsertLineBelow</span></span>

<span data-ttu-id="8c299-220">Новая пустая строка создается под текущей строкой независимо от того, где находится курсор на текущей строке.</span><span class="sxs-lookup"><span data-stu-id="8c299-220">A new empty line is created below the current line regardless of where the cursor is on the current line.</span></span> <span data-ttu-id="8c299-221">Курсор переместится в начало новой строки.</span><span class="sxs-lookup"><span data-stu-id="8c299-221">The cursor moves to the beginning of the new line.</span></span>

- <span data-ttu-id="8c299-222">Процессор `<Shift+Ctrl+Enter>`</span><span class="sxs-lookup"><span data-stu-id="8c299-222">Cmd: `<Shift+Ctrl+Enter>`</span></span>

### <a name="invertcase"></a><span data-ttu-id="8c299-223">инверткасе</span><span class="sxs-lookup"><span data-stu-id="8c299-223">InvertCase</span></span>

<span data-ttu-id="8c299-224">Инвертировать регистр текущего символа и перейти к следующему.</span><span class="sxs-lookup"><span data-stu-id="8c299-224">Invert the case of the current character and move to the next one.</span></span>

- <span data-ttu-id="8c299-225">Режим команд VI: `<~>`</span><span class="sxs-lookup"><span data-stu-id="8c299-225">Vi command mode: `<~>`</span></span>

### <a name="killline"></a><span data-ttu-id="8c299-226">килллине</span><span class="sxs-lookup"><span data-stu-id="8c299-226">KillLine</span></span>

<span data-ttu-id="8c299-227">Очистить входные данные от курсора до конца входных данных.</span><span class="sxs-lookup"><span data-stu-id="8c299-227">Clear the input from the cursor to the end of the input.</span></span> <span data-ttu-id="8c299-228">Очистка текста помещается в буфер Kill.</span><span class="sxs-lookup"><span data-stu-id="8c299-228">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="8c299-229">Emacs: `<Ctrl+k>`</span><span class="sxs-lookup"><span data-stu-id="8c299-229">Emacs: `<Ctrl+k>`</span></span>

### <a name="killregion"></a><span data-ttu-id="8c299-230">киллрегион</span><span class="sxs-lookup"><span data-stu-id="8c299-230">KillRegion</span></span>

<span data-ttu-id="8c299-231">Удалить текст между курсором и меткой.</span><span class="sxs-lookup"><span data-stu-id="8c299-231">Kill the text between the cursor and the mark.</span></span>

- <span data-ttu-id="8c299-232">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="8c299-232">Function is unbound.</span></span>

### <a name="killword"></a><span data-ttu-id="8c299-233">киллворд</span><span class="sxs-lookup"><span data-stu-id="8c299-233">KillWord</span></span>

<span data-ttu-id="8c299-234">Очистить ввод от курсора до конца текущего слова.</span><span class="sxs-lookup"><span data-stu-id="8c299-234">Clear the input from the cursor to the end of the current word.</span></span> <span data-ttu-id="8c299-235">Если курсор находится между словами, входные данные очищаются от курсора до конца следующего слова.</span><span class="sxs-lookup"><span data-stu-id="8c299-235">If the cursor is between words, the input is cleared from the cursor to the end of the next word.</span></span> <span data-ttu-id="8c299-236">Очистка текста помещается в буфер Kill.</span><span class="sxs-lookup"><span data-stu-id="8c299-236">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="8c299-237">Процессор `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="8c299-237">Cmd: `<Ctrl+Delete>`</span></span>
- <span data-ttu-id="8c299-238">Emacs: `<Alt+d>` , `<Escape,d>`</span><span class="sxs-lookup"><span data-stu-id="8c299-238">Emacs: `<Alt+d>`, `<Escape,d>`</span></span>
- <span data-ttu-id="8c299-239">Режим вставки в VI: `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="8c299-239">Vi insert mode: `<Ctrl+Delete>`</span></span>
- <span data-ttu-id="8c299-240">Режим команд VI: `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="8c299-240">Vi command mode: `<Ctrl+Delete>`</span></span>

### <a name="paste"></a><span data-ttu-id="8c299-241">Вставить</span><span class="sxs-lookup"><span data-stu-id="8c299-241">Paste</span></span>

<span data-ttu-id="8c299-242">Вставка текста из буфера обмена системы.</span><span class="sxs-lookup"><span data-stu-id="8c299-242">Paste text from the system clipboard.</span></span>

- <span data-ttu-id="8c299-243">Cmd: `<Ctrl+v>` , `<Shift+Insert>`</span><span class="sxs-lookup"><span data-stu-id="8c299-243">Cmd: `<Ctrl+v>`, `<Shift+Insert>`</span></span>
- <span data-ttu-id="8c299-244">Режим вставки в VI: `<Ctrl+v>`</span><span class="sxs-lookup"><span data-stu-id="8c299-244">Vi insert mode: `<Ctrl+v>`</span></span>
- <span data-ttu-id="8c299-245">Режим команд VI: `<Ctrl+v>`</span><span class="sxs-lookup"><span data-stu-id="8c299-245">Vi command mode: `<Ctrl+v>`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8c299-246">При использовании функции **вставки** все содержимое буфера буфера обмена вставляется во входной буфер PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="8c299-246">When using the **Paste** function, the entire contents of the clipboard buffer is pasted into the input buffer of PSReadLine.</span></span> <span data-ttu-id="8c299-247">Затем входной буфер передается средству синтаксического анализа PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8c299-247">The input buffer is then passed to the PowerShell parser.</span></span> <span data-ttu-id="8c299-248">Вход, вставленный с помощью консольного приложения, щелкните **правой кнопкой мыши** метод вставки, скопированный во входной буфер по одному символу за раз.</span><span class="sxs-lookup"><span data-stu-id="8c299-248">Input pasted using the console application's **right-click** paste method is copied to the input buffer one character at a time.</span></span> <span data-ttu-id="8c299-249">Входной буфер передается средству синтаксического анализа при копировании символа новой строки.</span><span class="sxs-lookup"><span data-stu-id="8c299-249">The input buffer is passed to the parser when a newline character is copied.</span></span> <span data-ttu-id="8c299-250">Поэтому входные данные анализируются по одной строке за раз.</span><span class="sxs-lookup"><span data-stu-id="8c299-250">Therefore, the input is parsed one line at a time.</span></span> <span data-ttu-id="8c299-251">Различие между методами вставки приводит к различному поведению при выполнении.</span><span class="sxs-lookup"><span data-stu-id="8c299-251">The difference between paste methods results in different execution behavior.</span></span>

### <a name="pasteafter"></a><span data-ttu-id="8c299-252">пастеафтер</span><span class="sxs-lookup"><span data-stu-id="8c299-252">PasteAfter</span></span>

<span data-ttu-id="8c299-253">Вставьте буфер обмена после курсора, переместив курсор в конец вставленного текста.</span><span class="sxs-lookup"><span data-stu-id="8c299-253">Paste the clipboard after the cursor, moving the cursor to the end of the pasted text.</span></span>

- <span data-ttu-id="8c299-254">Режим команд VI: `<p>`</span><span class="sxs-lookup"><span data-stu-id="8c299-254">Vi command mode: `<p>`</span></span>

### <a name="pastebefore"></a><span data-ttu-id="8c299-255">пастебефоре</span><span class="sxs-lookup"><span data-stu-id="8c299-255">PasteBefore</span></span>

<span data-ttu-id="8c299-256">Вставьте буфер обмена перед курсором, переместив курсор в конец вставленного текста.</span><span class="sxs-lookup"><span data-stu-id="8c299-256">Paste the clipboard before the cursor, moving the cursor to the end of the pasted text.</span></span>

- <span data-ttu-id="8c299-257">Режим команд VI: `<P>`</span><span class="sxs-lookup"><span data-stu-id="8c299-257">Vi command mode: `<P>`</span></span>

### <a name="prependandaccept"></a><span data-ttu-id="8c299-258">препендандакцепт</span><span class="sxs-lookup"><span data-stu-id="8c299-258">PrependAndAccept</span></span>

<span data-ttu-id="8c299-259">Добавьте в начало "#" и примите строку.</span><span class="sxs-lookup"><span data-stu-id="8c299-259">Prepend a '#' and accept the line.</span></span>

- <span data-ttu-id="8c299-260">Режим команд VI: `<#>`</span><span class="sxs-lookup"><span data-stu-id="8c299-260">Vi command mode: `<#>`</span></span>

### <a name="redo"></a><span data-ttu-id="8c299-261">Повторить</span><span class="sxs-lookup"><span data-stu-id="8c299-261">Redo</span></span>

<span data-ttu-id="8c299-262">Отмена отмены.</span><span class="sxs-lookup"><span data-stu-id="8c299-262">Undo an undo.</span></span>

- <span data-ttu-id="8c299-263">Процессор `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="8c299-263">Cmd: `<Ctrl+y>`</span></span>
- <span data-ttu-id="8c299-264">Режим вставки в VI: `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="8c299-264">Vi insert mode: `<Ctrl+y>`</span></span>
- <span data-ttu-id="8c299-265">Режим команд VI: `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="8c299-265">Vi command mode: `<Ctrl+y>`</span></span>

### <a name="repeatlastcommand"></a><span data-ttu-id="8c299-266">репеатласткомманд</span><span class="sxs-lookup"><span data-stu-id="8c299-266">RepeatLastCommand</span></span>

<span data-ttu-id="8c299-267">Повторите Последнее изменение текста.</span><span class="sxs-lookup"><span data-stu-id="8c299-267">Repeat the last text modification.</span></span>

- <span data-ttu-id="8c299-268">Режим команд VI: `<.>`</span><span class="sxs-lookup"><span data-stu-id="8c299-268">Vi command mode: `<.>`</span></span>

### <a name="revertline"></a><span data-ttu-id="8c299-269">ревертлине</span><span class="sxs-lookup"><span data-stu-id="8c299-269">RevertLine</span></span>

<span data-ttu-id="8c299-270">Меняет все входные данные на текущие входные данные.</span><span class="sxs-lookup"><span data-stu-id="8c299-270">Reverts all of the input to the current input.</span></span>

- <span data-ttu-id="8c299-271">Процессор `<Escape>`</span><span class="sxs-lookup"><span data-stu-id="8c299-271">Cmd: `<Escape>`</span></span>
- <span data-ttu-id="8c299-272">Emacs: `<Alt+r>` , `<Escape,r>`</span><span class="sxs-lookup"><span data-stu-id="8c299-272">Emacs: `<Alt+r>`, `<Escape,r>`</span></span>

### <a name="shellbackwardkillword"></a><span data-ttu-id="8c299-273">шеллбакквардкиллворд</span><span class="sxs-lookup"><span data-stu-id="8c299-273">ShellBackwardKillWord</span></span>

<span data-ttu-id="8c299-274">Очистить ввод от начала текущего слова до курсора.</span><span class="sxs-lookup"><span data-stu-id="8c299-274">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="8c299-275">Если курсор находится между словами, входные данные очищаются от начала предыдущего слова до курсора.</span><span class="sxs-lookup"><span data-stu-id="8c299-275">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="8c299-276">Очистка текста помещается в буфер Kill.</span><span class="sxs-lookup"><span data-stu-id="8c299-276">The cleared text is placed in the kill-ring.</span></span>

<span data-ttu-id="8c299-277">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="8c299-277">Function is unbound.</span></span>

### <a name="shellkillword"></a><span data-ttu-id="8c299-278">шеллкиллворд</span><span class="sxs-lookup"><span data-stu-id="8c299-278">ShellKillWord</span></span>

<span data-ttu-id="8c299-279">Очистить ввод от курсора до конца текущего слова.</span><span class="sxs-lookup"><span data-stu-id="8c299-279">Clear the input from the cursor to the end of the current word.</span></span> <span data-ttu-id="8c299-280">Если курсор находится между словами, входные данные очищаются от курсора до конца следующего слова.</span><span class="sxs-lookup"><span data-stu-id="8c299-280">If the cursor is between words, the input is cleared from the cursor to the end of the next word.</span></span> <span data-ttu-id="8c299-281">Очистка текста помещается в буфер Kill.</span><span class="sxs-lookup"><span data-stu-id="8c299-281">The cleared text is placed in the kill-ring.</span></span>

<span data-ttu-id="8c299-282">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="8c299-282">Function is unbound.</span></span>

### <a name="swapcharacters"></a><span data-ttu-id="8c299-283">свапчарактерс</span><span class="sxs-lookup"><span data-stu-id="8c299-283">SwapCharacters</span></span>

<span data-ttu-id="8c299-284">Поменять местами текущий и тот же символ.</span><span class="sxs-lookup"><span data-stu-id="8c299-284">Swap the current character and the one before it.</span></span>

- <span data-ttu-id="8c299-285">Emacs: `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="8c299-285">Emacs: `<Ctrl+t>`</span></span>
- <span data-ttu-id="8c299-286">Режим вставки в VI: `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="8c299-286">Vi insert mode: `<Ctrl+t>`</span></span>
- <span data-ttu-id="8c299-287">Режим команд VI: `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="8c299-287">Vi command mode: `<Ctrl+t>`</span></span>

### <a name="undo"></a><span data-ttu-id="8c299-288">Отменить</span><span class="sxs-lookup"><span data-stu-id="8c299-288">Undo</span></span>

<span data-ttu-id="8c299-289">Отмена предыдущего изменения.</span><span class="sxs-lookup"><span data-stu-id="8c299-289">Undo a previous edit.</span></span>

- <span data-ttu-id="8c299-290">Процессор `<Ctrl+z>`</span><span class="sxs-lookup"><span data-stu-id="8c299-290">Cmd: `<Ctrl+z>`</span></span>
- <span data-ttu-id="8c299-291">Emacs: `<Ctrl+_>` , `<Ctrl+x,Ctrl+u>`</span><span class="sxs-lookup"><span data-stu-id="8c299-291">Emacs: `<Ctrl+_>`, `<Ctrl+x,Ctrl+u>`</span></span>
- <span data-ttu-id="8c299-292">Режим вставки в VI: `<Ctrl+z>`</span><span class="sxs-lookup"><span data-stu-id="8c299-292">Vi insert mode: `<Ctrl+z>`</span></span>
- <span data-ttu-id="8c299-293">Режим команд VI: `<Ctrl+z>` , `<u>`</span><span class="sxs-lookup"><span data-stu-id="8c299-293">Vi command mode: `<Ctrl+z>`, `<u>`</span></span>

### <a name="undoall"></a><span data-ttu-id="8c299-294">ундоалл</span><span class="sxs-lookup"><span data-stu-id="8c299-294">UndoAll</span></span>

<span data-ttu-id="8c299-295">Отмена всех предыдущих изменений для строки.</span><span class="sxs-lookup"><span data-stu-id="8c299-295">Undo all previous edits for line.</span></span>

- <span data-ttu-id="8c299-296">Режим команд VI: `<U>`</span><span class="sxs-lookup"><span data-stu-id="8c299-296">Vi command mode: `<U>`</span></span>

### <a name="unixwordrubout"></a><span data-ttu-id="8c299-297">униксвордрубаут</span><span class="sxs-lookup"><span data-stu-id="8c299-297">UnixWordRubout</span></span>

<span data-ttu-id="8c299-298">Очистить ввод от начала текущего слова до курсора.</span><span class="sxs-lookup"><span data-stu-id="8c299-298">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="8c299-299">Если курсор находится между словами, входные данные очищаются от начала предыдущего слова до курсора.</span><span class="sxs-lookup"><span data-stu-id="8c299-299">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="8c299-300">Очистка текста помещается в буфер Kill.</span><span class="sxs-lookup"><span data-stu-id="8c299-300">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="8c299-301">Emacs: `<Ctrl+w>`</span><span class="sxs-lookup"><span data-stu-id="8c299-301">Emacs: `<Ctrl+w>`</span></span>

### <a name="validateandacceptline"></a><span data-ttu-id="8c299-302">валидатеандакцептлине</span><span class="sxs-lookup"><span data-stu-id="8c299-302">ValidateAndAcceptLine</span></span>

<span data-ttu-id="8c299-303">Попытка выполнить текущий вход.</span><span class="sxs-lookup"><span data-stu-id="8c299-303">Attempt to execute the current input.</span></span> <span data-ttu-id="8c299-304">Если текущий ввод неполон (например, отсутствует закрывающая круглая скобка, квадратная скобка или кавычка, запрос продолжения отображается на следующей строке, а PSReadLine ожидает ввода ключей для изменения текущих входных данных.</span><span class="sxs-lookup"><span data-stu-id="8c299-304">If the current input is incomplete (for example there is a missing closing parenthesis, bracket, or quote, then the continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span>

- <span data-ttu-id="8c299-305">Emacs: `<Ctrl+m>`</span><span class="sxs-lookup"><span data-stu-id="8c299-305">Emacs: `<Ctrl+m>`</span></span>

### <a name="viacceptline"></a><span data-ttu-id="8c299-306">виакцептлине</span><span class="sxs-lookup"><span data-stu-id="8c299-306">ViAcceptLine</span></span>

<span data-ttu-id="8c299-307">Примите строку и переключитесь в режим вставки.</span><span class="sxs-lookup"><span data-stu-id="8c299-307">Accept the line and switch to Insert mode.</span></span>

- <span data-ttu-id="8c299-308">Режим команд VI: `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="8c299-308">Vi command mode: `<Enter>`</span></span>

### <a name="viacceptlineorexit"></a><span data-ttu-id="8c299-309">виакцептлинеорексит</span><span class="sxs-lookup"><span data-stu-id="8c299-309">ViAcceptLineOrExit</span></span>

<span data-ttu-id="8c299-310">Как и Делетечарорексит в режиме Emacs, но принимает строку вместо удаления символа.</span><span class="sxs-lookup"><span data-stu-id="8c299-310">Like DeleteCharOrExit in Emacs mode, but accepts the line instead of deleting a character.</span></span>

- <span data-ttu-id="8c299-311">Режим вставки в VI: `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="8c299-311">Vi insert mode: `<Ctrl+d>`</span></span>
- <span data-ttu-id="8c299-312">Режим команд VI: `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="8c299-312">Vi command mode: `<Ctrl+d>`</span></span>

### <a name="viappendline"></a><span data-ttu-id="8c299-313">виаппендлине</span><span class="sxs-lookup"><span data-stu-id="8c299-313">ViAppendLine</span></span>

<span data-ttu-id="8c299-314">Новая строка вставляется под текущей строкой.</span><span class="sxs-lookup"><span data-stu-id="8c299-314">A new line is inserted below the current line.</span></span>

- <span data-ttu-id="8c299-315">Режим команд VI: `<o>`</span><span class="sxs-lookup"><span data-stu-id="8c299-315">Vi command mode: `<o>`</span></span>

### <a name="vibackwarddeleteglob"></a><span data-ttu-id="8c299-316">вибакквардделетеглоб</span><span class="sxs-lookup"><span data-stu-id="8c299-316">ViBackwardDeleteGlob</span></span>

<span data-ttu-id="8c299-317">Удаляет предыдущее слово, используя только пробелы в качестве разделителя слов.</span><span class="sxs-lookup"><span data-stu-id="8c299-317">Deletes the previous word, using only white space as the word delimiter.</span></span>

- <span data-ttu-id="8c299-318">Режим команд VI: `<d,B>`</span><span class="sxs-lookup"><span data-stu-id="8c299-318">Vi command mode: `<d,B>`</span></span>

### <a name="vibackwardglob"></a><span data-ttu-id="8c299-319">вибакквардглоб</span><span class="sxs-lookup"><span data-stu-id="8c299-319">ViBackwardGlob</span></span>

<span data-ttu-id="8c299-320">Перемещает курсор назад к началу предыдущего слова, используя только пробелы в качестве разделителей.</span><span class="sxs-lookup"><span data-stu-id="8c299-320">Moves the cursor back to the beginning of the previous word, using only white space as delimiters.</span></span>

- <span data-ttu-id="8c299-321">Режим команд VI: `<B>`</span><span class="sxs-lookup"><span data-stu-id="8c299-321">Vi command mode: `<B>`</span></span>

### <a name="videletebrace"></a><span data-ttu-id="8c299-322">виделетебраце</span><span class="sxs-lookup"><span data-stu-id="8c299-322">ViDeleteBrace</span></span>

<span data-ttu-id="8c299-323">Найдите парную фигурную скобку, круглую скобку или квадратную скобку и удалите все содержимое внутри, включая фигурную скобку.</span><span class="sxs-lookup"><span data-stu-id="8c299-323">Find the matching brace, parenthesis, or square bracket and delete all contents within, including the brace.</span></span>

- <span data-ttu-id="8c299-324">Режим команд VI: `<d,%>`</span><span class="sxs-lookup"><span data-stu-id="8c299-324">Vi command mode: `<d,%>`</span></span>

### <a name="videleteendofglob"></a><span data-ttu-id="8c299-325">виделетиндофглоб</span><span class="sxs-lookup"><span data-stu-id="8c299-325">ViDeleteEndOfGlob</span></span>

<span data-ttu-id="8c299-326">Удалить до конца слова.</span><span class="sxs-lookup"><span data-stu-id="8c299-326">Delete to the end of the word.</span></span>

- <span data-ttu-id="8c299-327">Режим команд VI: `<d,E>`</span><span class="sxs-lookup"><span data-stu-id="8c299-327">Vi command mode: `<d,E>`</span></span>

### <a name="videleteglob"></a><span data-ttu-id="8c299-328">виделетеглоб</span><span class="sxs-lookup"><span data-stu-id="8c299-328">ViDeleteGlob</span></span>

<span data-ttu-id="8c299-329">Удалите следующий стандартная маска (слово, разделенное пробелами).</span><span class="sxs-lookup"><span data-stu-id="8c299-329">Delete the next glob (white space delimited word).</span></span>

- <span data-ttu-id="8c299-330">Режим команд VI: `<d,W>`</span><span class="sxs-lookup"><span data-stu-id="8c299-330">Vi command mode: `<d,W>`</span></span>

### <a name="videletetobeforechar"></a><span data-ttu-id="8c299-331">виделететобефоречар</span><span class="sxs-lookup"><span data-stu-id="8c299-331">ViDeleteToBeforeChar</span></span>

<span data-ttu-id="8c299-332">Удаляет до заданного символа.</span><span class="sxs-lookup"><span data-stu-id="8c299-332">Deletes until given character.</span></span>

- <span data-ttu-id="8c299-333">Режим команд VI: `<d,t>`</span><span class="sxs-lookup"><span data-stu-id="8c299-333">Vi command mode: `<d,t>`</span></span>

### <a name="videletetobeforecharbackward"></a><span data-ttu-id="8c299-334">виделететобефоречарбакквард</span><span class="sxs-lookup"><span data-stu-id="8c299-334">ViDeleteToBeforeCharBackward</span></span>

<span data-ttu-id="8c299-335">Удаляет до заданного символа.</span><span class="sxs-lookup"><span data-stu-id="8c299-335">Deletes until given character.</span></span>

- <span data-ttu-id="8c299-336">Режим команд VI: `<d,T>`</span><span class="sxs-lookup"><span data-stu-id="8c299-336">Vi command mode: `<d,T>`</span></span>

### <a name="videletetochar"></a><span data-ttu-id="8c299-337">виделететочар</span><span class="sxs-lookup"><span data-stu-id="8c299-337">ViDeleteToChar</span></span>

<span data-ttu-id="8c299-338">Удаляет до заданного символа.</span><span class="sxs-lookup"><span data-stu-id="8c299-338">Deletes until given character.</span></span>

- <span data-ttu-id="8c299-339">Режим команд VI: `<d,f>`</span><span class="sxs-lookup"><span data-stu-id="8c299-339">Vi command mode: `<d,f>`</span></span>

### <a name="videletetocharbackward"></a><span data-ttu-id="8c299-340">виделететочарбакквард</span><span class="sxs-lookup"><span data-stu-id="8c299-340">ViDeleteToCharBackward</span></span>

<span data-ttu-id="8c299-341">Удаляет обратную сторону до заданного символа.</span><span class="sxs-lookup"><span data-stu-id="8c299-341">Deletes backwards until given character.</span></span>

- <span data-ttu-id="8c299-342">Режим команд VI: `<d,F>`</span><span class="sxs-lookup"><span data-stu-id="8c299-342">Vi command mode: `<d,F>`</span></span>

### <a name="viinsertatbegining"></a><span data-ttu-id="8c299-343">виинсертатбегининг</span><span class="sxs-lookup"><span data-stu-id="8c299-343">ViInsertAtBegining</span></span>

<span data-ttu-id="8c299-344">Переключитесь в режим вставки и поместите курсор в начало строки.</span><span class="sxs-lookup"><span data-stu-id="8c299-344">Switch to Insert mode and position the cursor at the beginning of the line.</span></span>

- <span data-ttu-id="8c299-345">Режим команд VI: `<I>`</span><span class="sxs-lookup"><span data-stu-id="8c299-345">Vi command mode: `<I>`</span></span>

### <a name="viinsertatend"></a><span data-ttu-id="8c299-346">виинсертатенд</span><span class="sxs-lookup"><span data-stu-id="8c299-346">ViInsertAtEnd</span></span>

<span data-ttu-id="8c299-347">Переключитесь в режим вставки и поместите курсор в конец строки.</span><span class="sxs-lookup"><span data-stu-id="8c299-347">Switch to Insert mode and position the cursor at the end of the line.</span></span>

- <span data-ttu-id="8c299-348">Режим команд VI: `<A>`</span><span class="sxs-lookup"><span data-stu-id="8c299-348">Vi command mode: `<A>`</span></span>

### <a name="viinsertline"></a><span data-ttu-id="8c299-349">виинсертлине</span><span class="sxs-lookup"><span data-stu-id="8c299-349">ViInsertLine</span></span>

<span data-ttu-id="8c299-350">Новая строка вставляется над текущей строкой.</span><span class="sxs-lookup"><span data-stu-id="8c299-350">A new line is inserted above the current line.</span></span>

- <span data-ttu-id="8c299-351">Режим команд VI: `<O>`</span><span class="sxs-lookup"><span data-stu-id="8c299-351">Vi command mode: `<O>`</span></span>

### <a name="viinsertwithappend"></a><span data-ttu-id="8c299-352">виинсертвисаппенд</span><span class="sxs-lookup"><span data-stu-id="8c299-352">ViInsertWithAppend</span></span>

<span data-ttu-id="8c299-353">Добавление из текущей позицией строки.</span><span class="sxs-lookup"><span data-stu-id="8c299-353">Append from the current line position.</span></span>

- <span data-ttu-id="8c299-354">Режим команд VI: `<a>`</span><span class="sxs-lookup"><span data-stu-id="8c299-354">Vi command mode: `<a>`</span></span>

### <a name="viinsertwithdelete"></a><span data-ttu-id="8c299-355">виинсертвисделете</span><span class="sxs-lookup"><span data-stu-id="8c299-355">ViInsertWithDelete</span></span>

<span data-ttu-id="8c299-356">Удалите текущий символ и переключитесь в режим вставки.</span><span class="sxs-lookup"><span data-stu-id="8c299-356">Delete the current character and switch to Insert mode.</span></span>

- <span data-ttu-id="8c299-357">Режим команд VI: `<s>`</span><span class="sxs-lookup"><span data-stu-id="8c299-357">Vi command mode: `<s>`</span></span>

### <a name="vijoinlines"></a><span data-ttu-id="8c299-358">вижоинлинес</span><span class="sxs-lookup"><span data-stu-id="8c299-358">ViJoinLines</span></span>

<span data-ttu-id="8c299-359">Объединяет текущую строку и следующую строку.</span><span class="sxs-lookup"><span data-stu-id="8c299-359">Joins the current line and the next line.</span></span>

- <span data-ttu-id="8c299-360">Режим команд VI: `<J>`</span><span class="sxs-lookup"><span data-stu-id="8c299-360">Vi command mode: `<J>`</span></span>

### <a name="vireplaceline"></a><span data-ttu-id="8c299-361">виреплацелине</span><span class="sxs-lookup"><span data-stu-id="8c299-361">ViReplaceLine</span></span>

<span data-ttu-id="8c299-362">Очистить всю командную строку.</span><span class="sxs-lookup"><span data-stu-id="8c299-362">Erase the entire command line.</span></span>

- <span data-ttu-id="8c299-363">Режим команд VI: `<S>` , `<c,c>`</span><span class="sxs-lookup"><span data-stu-id="8c299-363">Vi command mode: `<S>`, `<c,c>`</span></span>

### <a name="vireplacetobeforechar"></a><span data-ttu-id="8c299-364">виреплацетобефоречар</span><span class="sxs-lookup"><span data-stu-id="8c299-364">ViReplaceToBeforeChar</span></span>

<span data-ttu-id="8c299-365">Заменяет заданный символ.</span><span class="sxs-lookup"><span data-stu-id="8c299-365">Replaces until given character.</span></span>

- <span data-ttu-id="8c299-366">Режим команд VI: `<c,t>`</span><span class="sxs-lookup"><span data-stu-id="8c299-366">Vi command mode: `<c,t>`</span></span>

### <a name="vireplacetobeforecharbackward"></a><span data-ttu-id="8c299-367">виреплацетобефоречарбакквард</span><span class="sxs-lookup"><span data-stu-id="8c299-367">ViReplaceToBeforeCharBackward</span></span>

<span data-ttu-id="8c299-368">Заменяет заданный символ.</span><span class="sxs-lookup"><span data-stu-id="8c299-368">Replaces until given character.</span></span>

- <span data-ttu-id="8c299-369">Режим команд VI: `<c,T>`</span><span class="sxs-lookup"><span data-stu-id="8c299-369">Vi command mode: `<c,T>`</span></span>

### <a name="vireplacetochar"></a><span data-ttu-id="8c299-370">виреплацеточар</span><span class="sxs-lookup"><span data-stu-id="8c299-370">ViReplaceToChar</span></span>

<span data-ttu-id="8c299-371">Удаляет до заданного символа.</span><span class="sxs-lookup"><span data-stu-id="8c299-371">Deletes until given character.</span></span>

- <span data-ttu-id="8c299-372">Режим команд VI: `<c,f>`</span><span class="sxs-lookup"><span data-stu-id="8c299-372">Vi command mode: `<c,f>`</span></span>

### <a name="vireplacetocharbackward"></a><span data-ttu-id="8c299-373">виреплацеточарбакквард</span><span class="sxs-lookup"><span data-stu-id="8c299-373">ViReplaceToCharBackward</span></span>

<span data-ttu-id="8c299-374">Заменяет заданный символ.</span><span class="sxs-lookup"><span data-stu-id="8c299-374">Replaces until given character.</span></span>

- <span data-ttu-id="8c299-375">Режим команд VI: `<c,F>`</span><span class="sxs-lookup"><span data-stu-id="8c299-375">Vi command mode: `<c,F>`</span></span>

### <a name="viyankbeginningofline"></a><span data-ttu-id="8c299-376">вийанкбегиннингофлине</span><span class="sxs-lookup"><span data-stu-id="8c299-376">ViYankBeginningOfLine</span></span>

<span data-ttu-id="8c299-377">Янк от начала буфера до курсора.</span><span class="sxs-lookup"><span data-stu-id="8c299-377">Yank from the beginning of the buffer to the cursor.</span></span>

- <span data-ttu-id="8c299-378">Режим команд VI: `<y,0>`</span><span class="sxs-lookup"><span data-stu-id="8c299-378">Vi command mode: `<y,0>`</span></span>

### <a name="viyankendofglob"></a><span data-ttu-id="8c299-379">вийанкендофглоб</span><span class="sxs-lookup"><span data-stu-id="8c299-379">ViYankEndOfGlob</span></span>

<span data-ttu-id="8c299-380">Янк от курсора до конца слова.</span><span class="sxs-lookup"><span data-stu-id="8c299-380">Yank from the cursor to the end of the WORD(s).</span></span>

- <span data-ttu-id="8c299-381">Режим команд VI: `<y,E>`</span><span class="sxs-lookup"><span data-stu-id="8c299-381">Vi command mode: `<y,E>`</span></span>

### <a name="viyankendofword"></a><span data-ttu-id="8c299-382">вийанкендофворд</span><span class="sxs-lookup"><span data-stu-id="8c299-382">ViYankEndOfWord</span></span>

<span data-ttu-id="8c299-383">Янк от курсора до конца слова.</span><span class="sxs-lookup"><span data-stu-id="8c299-383">Yank from the cursor to the end of the word(s).</span></span>

- <span data-ttu-id="8c299-384">Режим команд VI: `<y,e>`</span><span class="sxs-lookup"><span data-stu-id="8c299-384">Vi command mode: `<y,e>`</span></span>

### <a name="viyankleft"></a><span data-ttu-id="8c299-385">вийанклефт</span><span class="sxs-lookup"><span data-stu-id="8c299-385">ViYankLeft</span></span>

<span data-ttu-id="8c299-386">Янк символы слева от курсора.</span><span class="sxs-lookup"><span data-stu-id="8c299-386">Yank character(s) to the left of the cursor.</span></span>

- <span data-ttu-id="8c299-387">Режим команд VI: `<y,h>`</span><span class="sxs-lookup"><span data-stu-id="8c299-387">Vi command mode: `<y,h>`</span></span>

### <a name="viyankline"></a><span data-ttu-id="8c299-388">вийанклине</span><span class="sxs-lookup"><span data-stu-id="8c299-388">ViYankLine</span></span>

<span data-ttu-id="8c299-389">Янк весь буфер.</span><span class="sxs-lookup"><span data-stu-id="8c299-389">Yank the entire buffer.</span></span>

- <span data-ttu-id="8c299-390">Режим команд VI: `<y,y>`</span><span class="sxs-lookup"><span data-stu-id="8c299-390">Vi command mode: `<y,y>`</span></span>

### <a name="viyanknextglob"></a><span data-ttu-id="8c299-391">вийанкнекстглоб</span><span class="sxs-lookup"><span data-stu-id="8c299-391">ViYankNextGlob</span></span>

<span data-ttu-id="8c299-392">Янк от курсора до начала следующего слова.</span><span class="sxs-lookup"><span data-stu-id="8c299-392">Yank from cursor to the start of the next WORD(s).</span></span>

- <span data-ttu-id="8c299-393">Режим команд VI: `<y,W>`</span><span class="sxs-lookup"><span data-stu-id="8c299-393">Vi command mode: `<y,W>`</span></span>

### <a name="viyanknextword"></a><span data-ttu-id="8c299-394">вийанкнекстворд</span><span class="sxs-lookup"><span data-stu-id="8c299-394">ViYankNextWord</span></span>

<span data-ttu-id="8c299-395">Янк слова после курсора.</span><span class="sxs-lookup"><span data-stu-id="8c299-395">Yank the word(s) after the cursor.</span></span>

- <span data-ttu-id="8c299-396">Режим команд VI: `<y,w>`</span><span class="sxs-lookup"><span data-stu-id="8c299-396">Vi command mode: `<y,w>`</span></span>

### <a name="viyankpercent"></a><span data-ttu-id="8c299-397">вийанкперцент</span><span class="sxs-lookup"><span data-stu-id="8c299-397">ViYankPercent</span></span>

<span data-ttu-id="8c299-398">Янк в парную фигурную скобку.</span><span class="sxs-lookup"><span data-stu-id="8c299-398">Yank to/from matching brace.</span></span>

- <span data-ttu-id="8c299-399">Режим команд VI: `<y,%>`</span><span class="sxs-lookup"><span data-stu-id="8c299-399">Vi command mode: `<y,%>`</span></span>

### <a name="viyankpreviousglob"></a><span data-ttu-id="8c299-400">вийанкпревиаусглоб</span><span class="sxs-lookup"><span data-stu-id="8c299-400">ViYankPreviousGlob</span></span>

<span data-ttu-id="8c299-401">Янк от начала слов до курсора.</span><span class="sxs-lookup"><span data-stu-id="8c299-401">Yank from beginning of the WORD(s) to cursor.</span></span>

- <span data-ttu-id="8c299-402">Режим команд VI: `<y,B>`</span><span class="sxs-lookup"><span data-stu-id="8c299-402">Vi command mode: `<y,B>`</span></span>

### <a name="viyankpreviousword"></a><span data-ttu-id="8c299-403">вийанкпревиаусворд</span><span class="sxs-lookup"><span data-stu-id="8c299-403">ViYankPreviousWord</span></span>

<span data-ttu-id="8c299-404">Янк слова перед курсором.</span><span class="sxs-lookup"><span data-stu-id="8c299-404">Yank the word(s) before the cursor.</span></span>

- <span data-ttu-id="8c299-405">Режим команд VI: `<y,b>`</span><span class="sxs-lookup"><span data-stu-id="8c299-405">Vi command mode: `<y,b>`</span></span>

### <a name="viyankright"></a><span data-ttu-id="8c299-406">вийанкригхт</span><span class="sxs-lookup"><span data-stu-id="8c299-406">ViYankRight</span></span>

<span data-ttu-id="8c299-407">Янк символы в положении и справа от курсора.</span><span class="sxs-lookup"><span data-stu-id="8c299-407">Yank character(s) under and to the right of the cursor.</span></span>

- <span data-ttu-id="8c299-408">Режим команд VI: `<y,l>` , `<y,Space>`</span><span class="sxs-lookup"><span data-stu-id="8c299-408">Vi command mode: `<y,l>`, `<y,Space>`</span></span>

### <a name="viyanktoendofline"></a><span data-ttu-id="8c299-409">вийанктоендофлине</span><span class="sxs-lookup"><span data-stu-id="8c299-409">ViYankToEndOfLine</span></span>

<span data-ttu-id="8c299-410">Янк от курсора до конца буфера.</span><span class="sxs-lookup"><span data-stu-id="8c299-410">Yank from the cursor to the end of the buffer.</span></span>

- <span data-ttu-id="8c299-411">Режим команд VI: `<y,$>`</span><span class="sxs-lookup"><span data-stu-id="8c299-411">Vi command mode: `<y,$>`</span></span>

### <a name="viyanktofirstchar"></a><span data-ttu-id="8c299-412">вийанктофирстчар</span><span class="sxs-lookup"><span data-stu-id="8c299-412">ViYankToFirstChar</span></span>

<span data-ttu-id="8c299-413">Янк от первого символа, отличного от пробела, к курсору.</span><span class="sxs-lookup"><span data-stu-id="8c299-413">Yank from the first non-whitespace character to the cursor.</span></span>

- <span data-ttu-id="8c299-414">Режим команд VI: `<y,^>`</span><span class="sxs-lookup"><span data-stu-id="8c299-414">Vi command mode: `<y,^>`</span></span>

### <a name="yank"></a><span data-ttu-id="8c299-415">янк</span><span class="sxs-lookup"><span data-stu-id="8c299-415">Yank</span></span>

<span data-ttu-id="8c299-416">Добавление последнего недавнего текста во входные данные.</span><span class="sxs-lookup"><span data-stu-id="8c299-416">Add the most recently killed text to the input.</span></span>

- <span data-ttu-id="8c299-417">Emacs: `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="8c299-417">Emacs: `<Ctrl+y>`</span></span>

### <a name="yanklastarg"></a><span data-ttu-id="8c299-418">янкластарг</span><span class="sxs-lookup"><span data-stu-id="8c299-418">YankLastArg</span></span>

<span data-ttu-id="8c299-419">Янк последний аргумент из предыдущей строки журнала.</span><span class="sxs-lookup"><span data-stu-id="8c299-419">Yank the last argument from the previous history line.</span></span> <span data-ttu-id="8c299-420">С аргументом при первом вызове он ведет себя так же, как Янкнсарг.</span><span class="sxs-lookup"><span data-stu-id="8c299-420">With an argument, the first time it is invoked, behaves just like YankNthArg.</span></span> <span data-ttu-id="8c299-421">Если вызывается несколько раз, вместо этого выполняется итерация по журналу, а аргумент устанавливает направление (отрицательно меняет направление на противоположное).</span><span class="sxs-lookup"><span data-stu-id="8c299-421">If invoked multiple times, instead it iterates through history and arg sets the direction (negative reverses the direction.)</span></span>

- <span data-ttu-id="8c299-422">Процессор `<Alt+.>`</span><span class="sxs-lookup"><span data-stu-id="8c299-422">Cmd: `<Alt+.>`</span></span>
- <span data-ttu-id="8c299-423">Emacs: `<Alt+.>` , `<Alt+_>` , `<Escape,.>` , `<Escape,_>`</span><span class="sxs-lookup"><span data-stu-id="8c299-423">Emacs: `<Alt+.>`, `<Alt+_>`, `<Escape,.>`, `<Escape,_>`</span></span>

### <a name="yankntharg"></a><span data-ttu-id="8c299-424">янкнсарг</span><span class="sxs-lookup"><span data-stu-id="8c299-424">YankNthArg</span></span>

<span data-ttu-id="8c299-425">Янк первый аргумент (после команды) из предыдущей строки журнала.</span><span class="sxs-lookup"><span data-stu-id="8c299-425">Yank the first argument (after the command) from the previous history line.</span></span>
<span data-ttu-id="8c299-426">При использовании аргумента Янк аргумент n (начиная с 0), если аргумент является отрицательным, начните с последнего аргумента.</span><span class="sxs-lookup"><span data-stu-id="8c299-426">With an argument, yank the nth argument (starting from 0), if the argument is negative, start from the last argument.</span></span>

- <span data-ttu-id="8c299-427">Emacs: `<Ctrl+Alt+y>` , `<Escape,Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="8c299-427">Emacs: `<Ctrl+Alt+y>`, `<Escape,Ctrl+y>`</span></span>

### <a name="yankpop"></a><span data-ttu-id="8c299-428">янкпоп</span><span class="sxs-lookup"><span data-stu-id="8c299-428">YankPop</span></span>

<span data-ttu-id="8c299-429">Если предыдущая операция была Янк или Янкпоп, замените ранее янкед текст следующим уничтоженным текстом из Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="8c299-429">If the previous operation was Yank or YankPop, replace the previously yanked text with the next killed text from the kill-ring.</span></span>

- <span data-ttu-id="8c299-430">Emacs: `<Alt+y>` , `<Escape,y>`</span><span class="sxs-lookup"><span data-stu-id="8c299-430">Emacs: `<Alt+y>`, `<Escape,y>`</span></span>

## <a name="cursor-movement-functions"></a><span data-ttu-id="8c299-431">Функции перемещения курсора</span><span class="sxs-lookup"><span data-stu-id="8c299-431">Cursor movement functions</span></span>

### <a name="backwardchar"></a><span data-ttu-id="8c299-432">бакквардчар</span><span class="sxs-lookup"><span data-stu-id="8c299-432">BackwardChar</span></span>

<span data-ttu-id="8c299-433">Переместить курсор на один символ влево.</span><span class="sxs-lookup"><span data-stu-id="8c299-433">Move the cursor one character to the left.</span></span> <span data-ttu-id="8c299-434">Это может переместить курсор к предыдущей строке многострочного ввода.</span><span class="sxs-lookup"><span data-stu-id="8c299-434">This may move the cursor to the previous line of multi-line input.</span></span>

- <span data-ttu-id="8c299-435">Процессор `<LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="8c299-435">Cmd: `<LeftArrow>`</span></span>
- <span data-ttu-id="8c299-436">Emacs: `<LeftArrow>` , `<Ctrl+b>`</span><span class="sxs-lookup"><span data-stu-id="8c299-436">Emacs: `<LeftArrow>`, `<Ctrl+b>`</span></span>
- <span data-ttu-id="8c299-437">Режим вставки в VI: `<LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="8c299-437">Vi insert mode: `<LeftArrow>`</span></span>
- <span data-ttu-id="8c299-438">Режим команд VI: `<LeftArrow>` , `<Backspace>` , `<h>`</span><span class="sxs-lookup"><span data-stu-id="8c299-438">Vi command mode: `<LeftArrow>`, `<Backspace>`, `<h>`</span></span>

### <a name="backwardword"></a><span data-ttu-id="8c299-439">бакквардворд</span><span class="sxs-lookup"><span data-stu-id="8c299-439">BackwardWord</span></span>

<span data-ttu-id="8c299-440">Перемещение курсора назад к началу текущего слова или между словами, с начала предыдущего слова.</span><span class="sxs-lookup"><span data-stu-id="8c299-440">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="8c299-441">Границы слов определяются с помощью настраиваемого набора символов.</span><span class="sxs-lookup"><span data-stu-id="8c299-441">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="8c299-442">Процессор `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="8c299-442">Cmd: `<Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="8c299-443">Emacs: `<Alt+b>` , `<Escape,b>`</span><span class="sxs-lookup"><span data-stu-id="8c299-443">Emacs: `<Alt+b>`, `<Escape,b>`</span></span>
- <span data-ttu-id="8c299-444">Режим вставки в VI: `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="8c299-444">Vi insert mode: `<Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="8c299-445">Режим команд VI: `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="8c299-445">Vi command mode: `<Ctrl+LeftArrow>`</span></span>

### <a name="beginningofline"></a><span data-ttu-id="8c299-446">бегиннингофлине</span><span class="sxs-lookup"><span data-stu-id="8c299-446">BeginningOfLine</span></span>

<span data-ttu-id="8c299-447">Если входные данные имеют несколько строк, переместитесь в начало текущей строки или, если они уже находятся в начале строки, перейдите к началу входного элемента.</span><span class="sxs-lookup"><span data-stu-id="8c299-447">If the input has multiple lines, move to the start of the current line, or if already at the start of the line, move to the start of the input.</span></span> <span data-ttu-id="8c299-448">Если входные данные имеют одну строку, переходите к началу входных данных.</span><span class="sxs-lookup"><span data-stu-id="8c299-448">If the input has a single line, move to the start of the input.</span></span>

- <span data-ttu-id="8c299-449">Процессор `<Home>`</span><span class="sxs-lookup"><span data-stu-id="8c299-449">Cmd: `<Home>`</span></span>
- <span data-ttu-id="8c299-450">Emacs: `<Home>` , `<Ctrl+a>`</span><span class="sxs-lookup"><span data-stu-id="8c299-450">Emacs: `<Home>`, `<Ctrl+a>`</span></span>
- <span data-ttu-id="8c299-451">Режим вставки в VI: `<Home>`</span><span class="sxs-lookup"><span data-stu-id="8c299-451">Vi insert mode: `<Home>`</span></span>
- <span data-ttu-id="8c299-452">Режим команд VI: `<Home>`</span><span class="sxs-lookup"><span data-stu-id="8c299-452">Vi command mode: `<Home>`</span></span>

### <a name="endofline"></a><span data-ttu-id="8c299-453">ендофлине</span><span class="sxs-lookup"><span data-stu-id="8c299-453">EndOfLine</span></span>

<span data-ttu-id="8c299-454">Если входные данные имеют несколько строк, переместитесь в конец текущей строки или, если они уже находятся в конце строки, перейдите к концу входных данных.</span><span class="sxs-lookup"><span data-stu-id="8c299-454">If the input has multiple lines, move to the end of the current line, or if already at the end of the line, move to the end of the input.</span></span> <span data-ttu-id="8c299-455">Если входные данные имеют одну строку, переходите к концу входных данных.</span><span class="sxs-lookup"><span data-stu-id="8c299-455">If the input has a single line, move to the end of the input.</span></span>

- <span data-ttu-id="8c299-456">Процессор `<End>`</span><span class="sxs-lookup"><span data-stu-id="8c299-456">Cmd: `<End>`</span></span>
- <span data-ttu-id="8c299-457">Emacs: `<End>` , `<Ctrl+e>`</span><span class="sxs-lookup"><span data-stu-id="8c299-457">Emacs: `<End>`, `<Ctrl+e>`</span></span>
- <span data-ttu-id="8c299-458">Режим вставки в VI: `<End>`</span><span class="sxs-lookup"><span data-stu-id="8c299-458">Vi insert mode: `<End>`</span></span>

### <a name="forwardchar"></a><span data-ttu-id="8c299-459">форвардчар</span><span class="sxs-lookup"><span data-stu-id="8c299-459">ForwardChar</span></span>

<span data-ttu-id="8c299-460">Переместить курсор на один символ вправо.</span><span class="sxs-lookup"><span data-stu-id="8c299-460">Move the cursor one character to the right.</span></span> <span data-ttu-id="8c299-461">Это может переместить курсор на следующую строку многострочного ввода.</span><span class="sxs-lookup"><span data-stu-id="8c299-461">This may move the cursor to the next line of multi-line input.</span></span>

- <span data-ttu-id="8c299-462">Процессор `<RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="8c299-462">Cmd: `<RightArrow>`</span></span>
- <span data-ttu-id="8c299-463">Emacs: `<RightArrow>` , `<Ctrl+f>`</span><span class="sxs-lookup"><span data-stu-id="8c299-463">Emacs: `<RightArrow>`, `<Ctrl+f>`</span></span>
- <span data-ttu-id="8c299-464">Режим вставки в VI: `<RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="8c299-464">Vi insert mode: `<RightArrow>`</span></span>
- <span data-ttu-id="8c299-465">Режим команд VI: `<RightArrow>` , `<Space>` , `<l>`</span><span class="sxs-lookup"><span data-stu-id="8c299-465">Vi command mode: `<RightArrow>`, `<Space>`, `<l>`</span></span>

### <a name="forwardword"></a><span data-ttu-id="8c299-466">форвардворд</span><span class="sxs-lookup"><span data-stu-id="8c299-466">ForwardWord</span></span>

<span data-ttu-id="8c299-467">Переместить курсор вперед к концу текущего слова или между словами, до конца следующего слова.</span><span class="sxs-lookup"><span data-stu-id="8c299-467">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="8c299-468">Границы слов определяются с помощью настраиваемого набора символов.</span><span class="sxs-lookup"><span data-stu-id="8c299-468">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="8c299-469">Emacs: `<Alt+f>` , `<Escape,f>`</span><span class="sxs-lookup"><span data-stu-id="8c299-469">Emacs: `<Alt+f>`, `<Escape,f>`</span></span>

### <a name="gotobrace"></a><span data-ttu-id="8c299-470">GotoBrace</span><span class="sxs-lookup"><span data-stu-id="8c299-470">GotoBrace</span></span>

<span data-ttu-id="8c299-471">Перейдите к парной фигурной скобке, круглой скобке или квадратной скобке.</span><span class="sxs-lookup"><span data-stu-id="8c299-471">Go to the matching brace, parenthesis, or square bracket.</span></span>

- <span data-ttu-id="8c299-472">Процессор `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="8c299-472">Cmd: `<Ctrl+]>`</span></span>
- <span data-ttu-id="8c299-473">Режим вставки в VI: `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="8c299-473">Vi insert mode: `<Ctrl+]>`</span></span>
- <span data-ttu-id="8c299-474">Режим команд VI: `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="8c299-474">Vi command mode: `<Ctrl+]>`</span></span>

### <a name="gotocolumn"></a><span data-ttu-id="8c299-475">готоколумн</span><span class="sxs-lookup"><span data-stu-id="8c299-475">GotoColumn</span></span>

<span data-ttu-id="8c299-476">Переход к столбцу, указанному аргументом arg.</span><span class="sxs-lookup"><span data-stu-id="8c299-476">Move to the column indicated by arg.</span></span>

- <span data-ttu-id="8c299-477">Режим команд VI: `<|>`</span><span class="sxs-lookup"><span data-stu-id="8c299-477">Vi command mode: `<|>`</span></span>

### <a name="gotofirstnonblankofline"></a><span data-ttu-id="8c299-478">готофирстнонбланкофлине</span><span class="sxs-lookup"><span data-stu-id="8c299-478">GotoFirstNonBlankOfLine</span></span>

<span data-ttu-id="8c299-479">Переместить курсор к первому непустому символу в строке.</span><span class="sxs-lookup"><span data-stu-id="8c299-479">Move the cursor to the first non-blank character in the line.</span></span>

- <span data-ttu-id="8c299-480">Режим команд VI: `<^>`</span><span class="sxs-lookup"><span data-stu-id="8c299-480">Vi command mode: `<^>`</span></span>

### <a name="movetoendofline"></a><span data-ttu-id="8c299-481">моветоендофлине</span><span class="sxs-lookup"><span data-stu-id="8c299-481">MoveToEndOfLine</span></span>

<span data-ttu-id="8c299-482">Переместить курсор в конец входных данных.</span><span class="sxs-lookup"><span data-stu-id="8c299-482">Move the cursor to the end of the input.</span></span>

- <span data-ttu-id="8c299-483">Режим команд VI: `<End>` , `<$>`</span><span class="sxs-lookup"><span data-stu-id="8c299-483">Vi command mode: `<End>`, `<$>`</span></span>

### <a name="nextline"></a><span data-ttu-id="8c299-484">некстлине</span><span class="sxs-lookup"><span data-stu-id="8c299-484">NextLine</span></span>

<span data-ttu-id="8c299-485">Переместить курсор на следующую строку.</span><span class="sxs-lookup"><span data-stu-id="8c299-485">Move the cursor to the next line.</span></span>

- <span data-ttu-id="8c299-486">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="8c299-486">Function is unbound.</span></span>

### <a name="nextword"></a><span data-ttu-id="8c299-487">некстворд</span><span class="sxs-lookup"><span data-stu-id="8c299-487">NextWord</span></span>

<span data-ttu-id="8c299-488">Переместить курсор вперед к началу следующего слова.</span><span class="sxs-lookup"><span data-stu-id="8c299-488">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="8c299-489">Границы слов определяются с помощью настраиваемого набора символов.</span><span class="sxs-lookup"><span data-stu-id="8c299-489">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="8c299-490">Процессор `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="8c299-490">Cmd: `<Ctrl+RightArrow>`</span></span>
- <span data-ttu-id="8c299-491">Режим вставки в VI: `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="8c299-491">Vi insert mode: `<Ctrl+RightArrow>`</span></span>
- <span data-ttu-id="8c299-492">Режим команд VI: `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="8c299-492">Vi command mode: `<Ctrl+RightArrow>`</span></span>

### <a name="nextwordend"></a><span data-ttu-id="8c299-493">некстворденд</span><span class="sxs-lookup"><span data-stu-id="8c299-493">NextWordEnd</span></span>

<span data-ttu-id="8c299-494">Переместить курсор вперед к концу текущего слова или между словами, до конца следующего слова.</span><span class="sxs-lookup"><span data-stu-id="8c299-494">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="8c299-495">Границы слов определяются с помощью настраиваемого набора символов.</span><span class="sxs-lookup"><span data-stu-id="8c299-495">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="8c299-496">Режим команд VI: `<e>`</span><span class="sxs-lookup"><span data-stu-id="8c299-496">Vi command mode: `<e>`</span></span>

### <a name="previousline"></a><span data-ttu-id="8c299-497">превиауслине</span><span class="sxs-lookup"><span data-stu-id="8c299-497">PreviousLine</span></span>

<span data-ttu-id="8c299-498">Переместить курсор на предыдущую строку.</span><span class="sxs-lookup"><span data-stu-id="8c299-498">Move the cursor to the previous line.</span></span>

- <span data-ttu-id="8c299-499">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="8c299-499">Function is unbound.</span></span>

### <a name="shellbackwardword"></a><span data-ttu-id="8c299-500">шеллбакквардворд</span><span class="sxs-lookup"><span data-stu-id="8c299-500">ShellBackwardWord</span></span>

<span data-ttu-id="8c299-501">Перемещение курсора назад к началу текущего слова или между словами, с начала предыдущего слова.</span><span class="sxs-lookup"><span data-stu-id="8c299-501">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="8c299-502">Границы слов определяются токенами PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8c299-502">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="8c299-503">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="8c299-503">Function is unbound.</span></span>

### <a name="shellforwardword"></a><span data-ttu-id="8c299-504">шеллфорвардворд</span><span class="sxs-lookup"><span data-stu-id="8c299-504">ShellForwardWord</span></span>

<span data-ttu-id="8c299-505">Переместить курсор вперед к началу следующего слова.</span><span class="sxs-lookup"><span data-stu-id="8c299-505">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="8c299-506">Границы слов определяются токенами PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8c299-506">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="8c299-507">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="8c299-507">Function is unbound.</span></span>

### <a name="shellnextword"></a><span data-ttu-id="8c299-508">шеллнекстворд</span><span class="sxs-lookup"><span data-stu-id="8c299-508">ShellNextWord</span></span>

<span data-ttu-id="8c299-509">Переместить курсор вперед к концу текущего слова или между словами, до конца следующего слова.</span><span class="sxs-lookup"><span data-stu-id="8c299-509">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="8c299-510">Границы слов определяются токенами PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8c299-510">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="8c299-511">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="8c299-511">Function is unbound.</span></span>

### <a name="vibackwardword"></a><span data-ttu-id="8c299-512">вибакквардворд</span><span class="sxs-lookup"><span data-stu-id="8c299-512">ViBackwardWord</span></span>

<span data-ttu-id="8c299-513">Перемещение курсора назад к началу текущего слова или между словами, с начала предыдущего слова.</span><span class="sxs-lookup"><span data-stu-id="8c299-513">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="8c299-514">Границы слов определяются с помощью настраиваемого набора символов.</span><span class="sxs-lookup"><span data-stu-id="8c299-514">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="8c299-515">Режим команд VI: `<b>`</span><span class="sxs-lookup"><span data-stu-id="8c299-515">Vi command mode: `<b>`</span></span>

### <a name="viendofglob"></a><span data-ttu-id="8c299-516">виендофглоб</span><span class="sxs-lookup"><span data-stu-id="8c299-516">ViEndOfGlob</span></span>

<span data-ttu-id="8c299-517">Перемещает курсор в конец слова, используя только пробелы в качестве разделителей.</span><span class="sxs-lookup"><span data-stu-id="8c299-517">Moves the cursor to the end of the word, using only white space as delimiters.</span></span>

- <span data-ttu-id="8c299-518">Режим команд VI: `<E>`</span><span class="sxs-lookup"><span data-stu-id="8c299-518">Vi command mode: `<E>`</span></span>

### <a name="viendofpreviousglob"></a><span data-ttu-id="8c299-519">виендофпревиаусглоб</span><span class="sxs-lookup"><span data-stu-id="8c299-519">ViEndOfPreviousGlob</span></span>

<span data-ttu-id="8c299-520">Переход к концу предыдущего слова с использованием только пробелов в качестве разделителя слов.</span><span class="sxs-lookup"><span data-stu-id="8c299-520">Moves to the end of the previous word, using only white space as a word delimiter.</span></span>

- <span data-ttu-id="8c299-521">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="8c299-521">Function is unbound.</span></span>

### <a name="vigotobrace"></a><span data-ttu-id="8c299-522">виготобраце</span><span class="sxs-lookup"><span data-stu-id="8c299-522">ViGotoBrace</span></span>

<span data-ttu-id="8c299-523">Аналогичен Готобраце, но является символом, а не основан на токене.</span><span class="sxs-lookup"><span data-stu-id="8c299-523">Similar to GotoBrace, but is character based instead of token based.</span></span>

- <span data-ttu-id="8c299-524">Режим команд VI: `<%>`</span><span class="sxs-lookup"><span data-stu-id="8c299-524">Vi command mode: `<%>`</span></span>

### <a name="vinextglob"></a><span data-ttu-id="8c299-525">винекстглоб</span><span class="sxs-lookup"><span data-stu-id="8c299-525">ViNextGlob</span></span>

<span data-ttu-id="8c299-526">Переход к следующему слову с использованием только пробелов в качестве разделителя слов.</span><span class="sxs-lookup"><span data-stu-id="8c299-526">Moves to the next word, using only white space as a word delimiter.</span></span>

- <span data-ttu-id="8c299-527">Режим команд VI: `<W>`</span><span class="sxs-lookup"><span data-stu-id="8c299-527">Vi command mode: `<W>`</span></span>

### <a name="vinextword"></a><span data-ttu-id="8c299-528">винекстворд</span><span class="sxs-lookup"><span data-stu-id="8c299-528">ViNextWord</span></span>

<span data-ttu-id="8c299-529">Переместить курсор вперед к началу следующего слова.</span><span class="sxs-lookup"><span data-stu-id="8c299-529">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="8c299-530">Границы слов определяются с помощью настраиваемого набора символов.</span><span class="sxs-lookup"><span data-stu-id="8c299-530">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="8c299-531">Режим команд VI: `<w>`</span><span class="sxs-lookup"><span data-stu-id="8c299-531">Vi command mode: `<w>`</span></span>

## <a name="history-functions"></a><span data-ttu-id="8c299-532">Функции журнала</span><span class="sxs-lookup"><span data-stu-id="8c299-532">History functions</span></span>

### <a name="beginningofhistory"></a><span data-ttu-id="8c299-533">бегиннингофхистори</span><span class="sxs-lookup"><span data-stu-id="8c299-533">BeginningOfHistory</span></span>

<span data-ttu-id="8c299-534">Перейти к первому элементу в журнале.</span><span class="sxs-lookup"><span data-stu-id="8c299-534">Move to the first item in the history.</span></span>

- <span data-ttu-id="8c299-535">Emacs: `<Alt+`<>\`</span><span class="sxs-lookup"><span data-stu-id="8c299-535">Emacs: `<Alt+`<>\`</span></span>

### <a name="clearhistory"></a><span data-ttu-id="8c299-536">клеархистори</span><span class="sxs-lookup"><span data-stu-id="8c299-536">ClearHistory</span></span>

<span data-ttu-id="8c299-537">Очищает журнал в PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="8c299-537">Clears history in PSReadLine.</span></span> <span data-ttu-id="8c299-538">Это не влияет на журнал PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8c299-538">This does not affect PowerShell history.</span></span>

- <span data-ttu-id="8c299-539">Процессор `<Alt+F7>`</span><span class="sxs-lookup"><span data-stu-id="8c299-539">Cmd: `<Alt+F7>`</span></span>

### <a name="endofhistory"></a><span data-ttu-id="8c299-540">ендофхистори</span><span class="sxs-lookup"><span data-stu-id="8c299-540">EndOfHistory</span></span>

<span data-ttu-id="8c299-541">Переход к последнему элементу (текущему входному объекту) в журнале.</span><span class="sxs-lookup"><span data-stu-id="8c299-541">Move to the last item (the current input) in the history.</span></span>

- <span data-ttu-id="8c299-542">Emacs: `<Alt+>>`</span><span class="sxs-lookup"><span data-stu-id="8c299-542">Emacs: `<Alt+>>`</span></span>

### <a name="forwardsearchhistory"></a><span data-ttu-id="8c299-543">форвардсеарчхистори</span><span class="sxs-lookup"><span data-stu-id="8c299-543">ForwardSearchHistory</span></span>

<span data-ttu-id="8c299-544">Выполните добавочный поиск по журналу.</span><span class="sxs-lookup"><span data-stu-id="8c299-544">Perform an incremental forward search through history.</span></span>

- <span data-ttu-id="8c299-545">Процессор `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="8c299-545">Cmd: `<Ctrl+s>`</span></span>
- <span data-ttu-id="8c299-546">Emacs: `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="8c299-546">Emacs: `<Ctrl+s>`</span></span>

### <a name="historysearchbackward"></a><span data-ttu-id="8c299-547">хисторисеарчбакквард</span><span class="sxs-lookup"><span data-stu-id="8c299-547">HistorySearchBackward</span></span>

<span data-ttu-id="8c299-548">Замените текущие входные данные элементом "Previous" из журнала PSReadLine, который соответствует символам между началом и входом и курсором.</span><span class="sxs-lookup"><span data-stu-id="8c299-548">Replace the current input with the 'previous' item from PSReadLine history that matches the characters between the start and the input and the cursor.</span></span>

- <span data-ttu-id="8c299-549">Процессор `<F8>`</span><span class="sxs-lookup"><span data-stu-id="8c299-549">Cmd: `<F8>`</span></span>

### <a name="historysearchforward"></a><span data-ttu-id="8c299-550">хисторисеарчфорвард</span><span class="sxs-lookup"><span data-stu-id="8c299-550">HistorySearchForward</span></span>

<span data-ttu-id="8c299-551">Замените текущие входные данные элементом "Next" из журнала PSReadLine, который соответствует символам между началом и входом и курсором.</span><span class="sxs-lookup"><span data-stu-id="8c299-551">Replace the current input with the 'next' item from PSReadLine history that matches the characters between the start and the input and the cursor.</span></span>

- <span data-ttu-id="8c299-552">Процессор `<Shift+F8>`</span><span class="sxs-lookup"><span data-stu-id="8c299-552">Cmd: `<Shift+F8>`</span></span>

### <a name="nexthistory"></a><span data-ttu-id="8c299-553">некссистори</span><span class="sxs-lookup"><span data-stu-id="8c299-553">NextHistory</span></span>

<span data-ttu-id="8c299-554">Замените текущие входные данные на элемент "Next" из журнала PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="8c299-554">Replace the current input with the 'next' item from PSReadLine history.</span></span>

- <span data-ttu-id="8c299-555">Процессор `<DownArrow>`</span><span class="sxs-lookup"><span data-stu-id="8c299-555">Cmd: `<DownArrow>`</span></span>
- <span data-ttu-id="8c299-556">Emacs: `<DownArrow>` , `<Ctrl+n>`</span><span class="sxs-lookup"><span data-stu-id="8c299-556">Emacs: `<DownArrow>`, `<Ctrl+n>`</span></span>
- <span data-ttu-id="8c299-557">Режим вставки в VI: `<DownArrow>`</span><span class="sxs-lookup"><span data-stu-id="8c299-557">Vi insert mode: `<DownArrow>`</span></span>
- <span data-ttu-id="8c299-558">Режим команд VI: `<DownArrow>` , `<j>` , `<+>`</span><span class="sxs-lookup"><span data-stu-id="8c299-558">Vi command mode: `<DownArrow>`, `<j>`, `<+>`</span></span>

### <a name="previoushistory"></a><span data-ttu-id="8c299-559">превиаушистори</span><span class="sxs-lookup"><span data-stu-id="8c299-559">PreviousHistory</span></span>

<span data-ttu-id="8c299-560">Замените текущие входные данные элементом "Previous" из журнала PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="8c299-560">Replace the current input with the 'previous' item from PSReadLine history.</span></span>

- <span data-ttu-id="8c299-561">Процессор `<UpArrow>`</span><span class="sxs-lookup"><span data-stu-id="8c299-561">Cmd: `<UpArrow>`</span></span>
- <span data-ttu-id="8c299-562">Emacs: `<UpArrow>` , `<Ctrl+p>`</span><span class="sxs-lookup"><span data-stu-id="8c299-562">Emacs: `<UpArrow>`, `<Ctrl+p>`</span></span>
- <span data-ttu-id="8c299-563">Режим вставки в VI: `<UpArrow>`</span><span class="sxs-lookup"><span data-stu-id="8c299-563">Vi insert mode: `<UpArrow>`</span></span>
- <span data-ttu-id="8c299-564">Режим команд VI: `<UpArrow>` , `<k>` , `<->`</span><span class="sxs-lookup"><span data-stu-id="8c299-564">Vi command mode: `<UpArrow>`, `<k>`, `<->`</span></span>

### <a name="reversesearchhistory"></a><span data-ttu-id="8c299-565">реверсесеарчхистори</span><span class="sxs-lookup"><span data-stu-id="8c299-565">ReverseSearchHistory</span></span>

<span data-ttu-id="8c299-566">Выполните добавочный поиск по журналу.</span><span class="sxs-lookup"><span data-stu-id="8c299-566">Perform an incremental backward search through history.</span></span>

- <span data-ttu-id="8c299-567">Процессор `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="8c299-567">Cmd: `<Ctrl+r>`</span></span>
- <span data-ttu-id="8c299-568">Emacs: `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="8c299-568">Emacs: `<Ctrl+r>`</span></span>

### <a name="visearchhistorybackward"></a><span data-ttu-id="8c299-569">висеарчхисторибакквард</span><span class="sxs-lookup"><span data-stu-id="8c299-569">ViSearchHistoryBackward</span></span>

<span data-ttu-id="8c299-570">Запрашивает строку поиска и инициирует поиск по запросу Акцептлине.</span><span class="sxs-lookup"><span data-stu-id="8c299-570">Prompts for a search string and initiates search upon AcceptLine.</span></span>

- <span data-ttu-id="8c299-571">Режим вставки в VI: `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="8c299-571">Vi insert mode: `<Ctrl+r>`</span></span>
- <span data-ttu-id="8c299-572">Режим команд VI: `</>` , `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="8c299-572">Vi command mode: `</>`, `<Ctrl+r>`</span></span>

## <a name="completion-functions"></a><span data-ttu-id="8c299-573">Функции завершения</span><span class="sxs-lookup"><span data-stu-id="8c299-573">Completion functions</span></span>

### <a name="complete"></a><span data-ttu-id="8c299-574">Завершить</span><span class="sxs-lookup"><span data-stu-id="8c299-574">Complete</span></span>

<span data-ttu-id="8c299-575">Попытка выполнить завершение в тексте, окружающем курсор.</span><span class="sxs-lookup"><span data-stu-id="8c299-575">Attempt to perform completion on the text surrounding the cursor.</span></span> <span data-ttu-id="8c299-576">Если существует несколько возможных завершений, для завершения используется самый длинный ненеоднозначный префикс.</span><span class="sxs-lookup"><span data-stu-id="8c299-576">If there are multiple possible completions, the longest unambiguous prefix is used for completion.</span></span> <span data-ttu-id="8c299-577">При попытке выполнить наибольшее неоднозначное Завершение отображается список возможных завершений.</span><span class="sxs-lookup"><span data-stu-id="8c299-577">If trying to complete the longest unambiguous completion, a list of possible completions is displayed.</span></span>

- <span data-ttu-id="8c299-578">Emacs: `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="8c299-578">Emacs: `<Tab>`</span></span>

### <a name="menucomplete"></a><span data-ttu-id="8c299-579">менукомплете</span><span class="sxs-lookup"><span data-stu-id="8c299-579">MenuComplete</span></span>

<span data-ttu-id="8c299-580">Попытка выполнить завершение в тексте, окружающем курсор.</span><span class="sxs-lookup"><span data-stu-id="8c299-580">Attempt to perform completion on the text surrounding the cursor.</span></span> <span data-ttu-id="8c299-581">Если существует несколько возможных завершений, для завершения используется самый длинный ненеоднозначный префикс.</span><span class="sxs-lookup"><span data-stu-id="8c299-581">If there are multiple possible completions, the longest unambiguous prefix is used for completion.</span></span> <span data-ttu-id="8c299-582">При попытке выполнить наибольшее неоднозначное Завершение отображается список возможных завершений.</span><span class="sxs-lookup"><span data-stu-id="8c299-582">If trying to complete the longest unambiguous completion, a list of possible completions is displayed.</span></span>

- <span data-ttu-id="8c299-583">Процессор `<Ctrl+Space>`</span><span class="sxs-lookup"><span data-stu-id="8c299-583">Cmd: `<Ctrl+Space>`</span></span>
- <span data-ttu-id="8c299-584">Emacs: `<Ctrl+Space>`</span><span class="sxs-lookup"><span data-stu-id="8c299-584">Emacs: `<Ctrl+Space>`</span></span>

### <a name="possiblecompletions"></a><span data-ttu-id="8c299-585">поссиблекомплетионс</span><span class="sxs-lookup"><span data-stu-id="8c299-585">PossibleCompletions</span></span>

<span data-ttu-id="8c299-586">Отображение списка возможных завершений.</span><span class="sxs-lookup"><span data-stu-id="8c299-586">Display the list of possible completions.</span></span>

- <span data-ttu-id="8c299-587">Emacs: `<Alt+=>`</span><span class="sxs-lookup"><span data-stu-id="8c299-587">Emacs: `<Alt+=>`</span></span>
- <span data-ttu-id="8c299-588">Режим вставки в VI: `<Ctrl+Space>`</span><span class="sxs-lookup"><span data-stu-id="8c299-588">Vi insert mode: `<Ctrl+Space>`</span></span>
- <span data-ttu-id="8c299-589">Режим команд VI: `<Ctrl+Space>`</span><span class="sxs-lookup"><span data-stu-id="8c299-589">Vi command mode: `<Ctrl+Space>`</span></span>

### <a name="tabcompletenext"></a><span data-ttu-id="8c299-590">табкомплетенекст</span><span class="sxs-lookup"><span data-stu-id="8c299-590">TabCompleteNext</span></span>

<span data-ttu-id="8c299-591">Попытайтесь завершить текст, окружающий курсор, с помощью следующего доступного завершения.</span><span class="sxs-lookup"><span data-stu-id="8c299-591">Attempt to complete the text surrounding the cursor with the next available completion.</span></span>

- <span data-ttu-id="8c299-592">Процессор `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="8c299-592">Cmd: `<Tab>`</span></span>
- <span data-ttu-id="8c299-593">Режим команд VI: `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="8c299-593">Vi command mode: `<Tab>`</span></span>

### <a name="tabcompleteprevious"></a><span data-ttu-id="8c299-594">табкомплетепревиаус</span><span class="sxs-lookup"><span data-stu-id="8c299-594">TabCompletePrevious</span></span>

<span data-ttu-id="8c299-595">Попытайтесь завершить текст, окружающий курсор, с предыдущим доступным завершением.</span><span class="sxs-lookup"><span data-stu-id="8c299-595">Attempt to complete the text surrounding the cursor with the previous available completion.</span></span>

- <span data-ttu-id="8c299-596">Процессор `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="8c299-596">Cmd: `<Shift+Tab>`</span></span>
- <span data-ttu-id="8c299-597">Режим команд VI: `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="8c299-597">Vi command mode: `<Shift+Tab>`</span></span>

### <a name="vitabcompletenext"></a><span data-ttu-id="8c299-598">витабкомплетенекст</span><span class="sxs-lookup"><span data-stu-id="8c299-598">ViTabCompleteNext</span></span>

<span data-ttu-id="8c299-599">При необходимости завершает текущую группу редактирования и вызывает Табкомплетенекст.</span><span class="sxs-lookup"><span data-stu-id="8c299-599">Ends the current edit group, if needed, and invokes TabCompleteNext.</span></span>

- <span data-ttu-id="8c299-600">Режим вставки в VI: `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="8c299-600">Vi insert mode: `<Tab>`</span></span>

### <a name="vitabcompleteprevious"></a><span data-ttu-id="8c299-601">витабкомплетепревиаус</span><span class="sxs-lookup"><span data-stu-id="8c299-601">ViTabCompletePrevious</span></span>

<span data-ttu-id="8c299-602">При необходимости завершает текущую группу редактирования и вызывает Табкомплетепревиаус.</span><span class="sxs-lookup"><span data-stu-id="8c299-602">Ends the current edit group, if needed, and invokes TabCompletePrevious.</span></span>

- <span data-ttu-id="8c299-603">Режим вставки в VI: `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="8c299-603">Vi insert mode: `<Shift+Tab>`</span></span>

## <a name="miscellaneous-functions"></a><span data-ttu-id="8c299-604">Прочие функции</span><span class="sxs-lookup"><span data-stu-id="8c299-604">Miscellaneous functions</span></span>

### <a name="capturescreen"></a><span data-ttu-id="8c299-605">каптурескрин</span><span class="sxs-lookup"><span data-stu-id="8c299-605">CaptureScreen</span></span>

<span data-ttu-id="8c299-606">Запуск интерактивной записи экрана — стрелки вверх и вниз выбор строк, ввод копирует выделенный текст в буфер обмена в виде текста и HTML.</span><span class="sxs-lookup"><span data-stu-id="8c299-606">Start interactive screen capture - up/down arrows select lines, enter copies selected text to clipboard as text and html.</span></span>

- <span data-ttu-id="8c299-607">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="8c299-607">Function is unbound.</span></span>

### <a name="clearscreen"></a><span data-ttu-id="8c299-608">клеарскрин</span><span class="sxs-lookup"><span data-stu-id="8c299-608">ClearScreen</span></span>

<span data-ttu-id="8c299-609">Очистить экран и нарисовать текущую строку в верхней части экрана.</span><span class="sxs-lookup"><span data-stu-id="8c299-609">Clear the screen and draw the current line at the top of the screen.</span></span>

- <span data-ttu-id="8c299-610">Процессор `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="8c299-610">Cmd: `<Ctrl+l>`</span></span>
- <span data-ttu-id="8c299-611">Emacs: `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="8c299-611">Emacs: `<Ctrl+l>`</span></span>
- <span data-ttu-id="8c299-612">Режим вставки в VI: `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="8c299-612">Vi insert mode: `<Ctrl+l>`</span></span>
- <span data-ttu-id="8c299-613">Режим команд VI: `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="8c299-613">Vi command mode: `<Ctrl+l>`</span></span>

### <a name="digitargument"></a><span data-ttu-id="8c299-614">дигитаргумент</span><span class="sxs-lookup"><span data-stu-id="8c299-614">DigitArgument</span></span>

<span data-ttu-id="8c299-615">Начните новый аргумент цифры для передачи другим функциям.</span><span class="sxs-lookup"><span data-stu-id="8c299-615">Start a new digit argument to pass to other functions.</span></span>

- <span data-ttu-id="8c299-616">Cmd: `<Alt+0>` , `<Alt+1>` , `<Alt+2>` , `<Alt+3>` , `<Alt+4>` , `<Alt+5>` , `<Alt+6>` , `<Alt+7>` , `<Alt+8>` , `<Alt+9>` , `<Alt+->`</span><span class="sxs-lookup"><span data-stu-id="8c299-616">Cmd: `<Alt+0>`, `<Alt+1>`, `<Alt+2>`, `<Alt+3>`, `<Alt+4>`, `<Alt+5>`, `<Alt+6>`, `<Alt+7>`, `<Alt+8>`, `<Alt+9>`, `<Alt+->`</span></span>
- <span data-ttu-id="8c299-617">Emacs: `<Alt+0>` , `<Alt+1>` , `<Alt+2>` , `<Alt+3>` , `<Alt+4>` , `<Alt+5>` , `<Alt+6>` , `<Alt+7>` , `<Alt+8>` , `<Alt+9>` , `<Alt+->`</span><span class="sxs-lookup"><span data-stu-id="8c299-617">Emacs: `<Alt+0>`, `<Alt+1>`, `<Alt+2>`, `<Alt+3>`, `<Alt+4>`, `<Alt+5>`, `<Alt+6>`, `<Alt+7>`, `<Alt+8>`, `<Alt+9>`, `<Alt+->`</span></span>
- <span data-ttu-id="8c299-618">Режим команд VI: `<0>` , `<1>` , `<2>` , `<3>` , `<4>` , `<5>` , `<6>` , `<7>` , `<8>` , `<9>`</span><span class="sxs-lookup"><span data-stu-id="8c299-618">Vi command mode: `<0>`, `<1>`, `<2>`, `<3>`, `<4>`, `<5>`, `<6>`, `<7>`, `<8>`, `<9>`</span></span>

### <a name="invokeprompt"></a><span data-ttu-id="8c299-619">инвокепромпт</span><span class="sxs-lookup"><span data-stu-id="8c299-619">InvokePrompt</span></span>

<span data-ttu-id="8c299-620">Стирает текущий запрос и вызывает функцию Prompt для повторного вывода запроса.</span><span class="sxs-lookup"><span data-stu-id="8c299-620">Erases the current prompt and calls the prompt function to redisplay the prompt.</span></span> <span data-ttu-id="8c299-621">Полезен для обработчиков пользовательских ключей, изменяющих состояние, например для изменения текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="8c299-621">Useful for custom key handlers that change state, e.g. change the current directory.</span></span>

- <span data-ttu-id="8c299-622">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="8c299-622">Function is unbound.</span></span>

### <a name="scrolldisplaydown"></a><span data-ttu-id="8c299-623">скроллдисплайдовн</span><span class="sxs-lookup"><span data-stu-id="8c299-623">ScrollDisplayDown</span></span>

<span data-ttu-id="8c299-624">Прокрутите экран вниз на один экран.</span><span class="sxs-lookup"><span data-stu-id="8c299-624">Scroll the display down one screen.</span></span>

- <span data-ttu-id="8c299-625">Процессор `<PageDown>`</span><span class="sxs-lookup"><span data-stu-id="8c299-625">Cmd: `<PageDown>`</span></span>
- <span data-ttu-id="8c299-626">Emacs: `<PageDown>`</span><span class="sxs-lookup"><span data-stu-id="8c299-626">Emacs: `<PageDown>`</span></span>

### <a name="scrolldisplaydownline"></a><span data-ttu-id="8c299-627">скроллдисплайдовнлине</span><span class="sxs-lookup"><span data-stu-id="8c299-627">ScrollDisplayDownLine</span></span>

<span data-ttu-id="8c299-628">Прокрутите экран вниз на одну строку.</span><span class="sxs-lookup"><span data-stu-id="8c299-628">Scroll the display down one line.</span></span>

- <span data-ttu-id="8c299-629">Процессор `<Ctrl+PageDown>`</span><span class="sxs-lookup"><span data-stu-id="8c299-629">Cmd: `<Ctrl+PageDown>`</span></span>
- <span data-ttu-id="8c299-630">Emacs: `<Ctrl+PageDown>`</span><span class="sxs-lookup"><span data-stu-id="8c299-630">Emacs: `<Ctrl+PageDown>`</span></span>

### <a name="scrolldisplaytocursor"></a><span data-ttu-id="8c299-631">скроллдисплайтокурсор</span><span class="sxs-lookup"><span data-stu-id="8c299-631">ScrollDisplayToCursor</span></span>

<span data-ttu-id="8c299-632">Прокрутить экран до курсора.</span><span class="sxs-lookup"><span data-stu-id="8c299-632">Scroll the display to the cursor.</span></span>

- <span data-ttu-id="8c299-633">Emacs: `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="8c299-633">Emacs: `<Ctrl+End>`</span></span>

### <a name="scrolldisplaytop"></a><span data-ttu-id="8c299-634">скроллдисплайтоп</span><span class="sxs-lookup"><span data-stu-id="8c299-634">ScrollDisplayTop</span></span>

<span data-ttu-id="8c299-635">Прокрутите экран до верха.</span><span class="sxs-lookup"><span data-stu-id="8c299-635">Scroll the display to the top.</span></span>

- <span data-ttu-id="8c299-636">Emacs: `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="8c299-636">Emacs: `<Ctrl+Home>`</span></span>

### <a name="scrolldisplayup"></a><span data-ttu-id="8c299-637">скроллдисплайуп</span><span class="sxs-lookup"><span data-stu-id="8c299-637">ScrollDisplayUp</span></span>

<span data-ttu-id="8c299-638">Прокрутите экран вверх на один экран.</span><span class="sxs-lookup"><span data-stu-id="8c299-638">Scroll the display up one screen.</span></span>

- <span data-ttu-id="8c299-639">Процессор `<PageUp>`</span><span class="sxs-lookup"><span data-stu-id="8c299-639">Cmd: `<PageUp>`</span></span>
- <span data-ttu-id="8c299-640">Emacs: `<PageUp>`</span><span class="sxs-lookup"><span data-stu-id="8c299-640">Emacs: `<PageUp>`</span></span>

### <a name="scrolldisplayupline"></a><span data-ttu-id="8c299-641">скроллдисплайуплине</span><span class="sxs-lookup"><span data-stu-id="8c299-641">ScrollDisplayUpLine</span></span>

<span data-ttu-id="8c299-642">Прокрутите экран вверх на одну строку.</span><span class="sxs-lookup"><span data-stu-id="8c299-642">Scroll the display up one line.</span></span>

- <span data-ttu-id="8c299-643">Процессор `<Ctrl+PageUp>`</span><span class="sxs-lookup"><span data-stu-id="8c299-643">Cmd: `<Ctrl+PageUp>`</span></span>
- <span data-ttu-id="8c299-644">Emacs: `<Ctrl+PageUp>`</span><span class="sxs-lookup"><span data-stu-id="8c299-644">Emacs: `<Ctrl+PageUp>`</span></span>

### <a name="selfinsert"></a><span data-ttu-id="8c299-645">селфинсерт</span><span class="sxs-lookup"><span data-stu-id="8c299-645">SelfInsert</span></span>

<span data-ttu-id="8c299-646">Вставьте ключ.</span><span class="sxs-lookup"><span data-stu-id="8c299-646">Insert the key.</span></span>

- <span data-ttu-id="8c299-647">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="8c299-647">Function is unbound.</span></span>

### <a name="showkeybindings"></a><span data-ttu-id="8c299-648">шовкэйбиндингс</span><span class="sxs-lookup"><span data-stu-id="8c299-648">ShowKeyBindings</span></span>

<span data-ttu-id="8c299-649">Отображение всех связанных ключей.</span><span class="sxs-lookup"><span data-stu-id="8c299-649">Show all bound keys.</span></span>

- <span data-ttu-id="8c299-650">Процессор `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="8c299-650">Cmd: `<Ctrl+Alt+?>`</span></span>
- <span data-ttu-id="8c299-651">Emacs: `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="8c299-651">Emacs: `<Ctrl+Alt+?>`</span></span>
- <span data-ttu-id="8c299-652">Режим вставки в VI: `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="8c299-652">Vi insert mode: `<Ctrl+Alt+?>`</span></span>

### <a name="vicommandmode"></a><span data-ttu-id="8c299-653">викоммандмоде</span><span class="sxs-lookup"><span data-stu-id="8c299-653">ViCommandMode</span></span>

<span data-ttu-id="8c299-654">Переключите текущий режим работы с Vi-Insert на VI-Command.</span><span class="sxs-lookup"><span data-stu-id="8c299-654">Switch the current operating mode from Vi-Insert to Vi-Command.</span></span>

- <span data-ttu-id="8c299-655">Режим вставки в VI: `<Escape>`</span><span class="sxs-lookup"><span data-stu-id="8c299-655">Vi insert mode: `<Escape>`</span></span>

### <a name="vidigitargumentinchord"></a><span data-ttu-id="8c299-656">видигитаргументинчорд</span><span class="sxs-lookup"><span data-stu-id="8c299-656">ViDigitArgumentInChord</span></span>

<span data-ttu-id="8c299-657">Начните новый числовой аргумент, чтобы передать его другим функциям в одной из сочетаний VI.</span><span class="sxs-lookup"><span data-stu-id="8c299-657">Start a new digit argument to pass to other functions while in one of vi's chords.</span></span>

- <span data-ttu-id="8c299-658">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="8c299-658">Function is unbound.</span></span>

### <a name="vieditvisually"></a><span data-ttu-id="8c299-659">виедитвисуалли</span><span class="sxs-lookup"><span data-stu-id="8c299-659">ViEditVisually</span></span>

<span data-ttu-id="8c299-660">Измените командную строку в текстовом редакторе, заданном $env: EDITOR или $env: VISUAL.</span><span class="sxs-lookup"><span data-stu-id="8c299-660">Edit the command line in a text editor specified by $env:EDITOR or $env:VISUAL.</span></span>

- <span data-ttu-id="8c299-661">Emacs: `<Ctrl+x,Ctrl+e>`</span><span class="sxs-lookup"><span data-stu-id="8c299-661">Emacs: `<Ctrl+x,Ctrl+e>`</span></span>
- <span data-ttu-id="8c299-662">Режим команд VI: `<v>`</span><span class="sxs-lookup"><span data-stu-id="8c299-662">Vi command mode: `<v>`</span></span>

### <a name="viexit"></a><span data-ttu-id="8c299-663">виексит</span><span class="sxs-lookup"><span data-stu-id="8c299-663">ViExit</span></span>

<span data-ttu-id="8c299-664">Завершает работу оболочки.</span><span class="sxs-lookup"><span data-stu-id="8c299-664">Exits the shell.</span></span>

- <span data-ttu-id="8c299-665">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="8c299-665">Function is unbound.</span></span>

### <a name="viinsertmode"></a><span data-ttu-id="8c299-666">виинсертмоде</span><span class="sxs-lookup"><span data-stu-id="8c299-666">ViInsertMode</span></span>

<span data-ttu-id="8c299-667">Переключитесь в режим вставки.</span><span class="sxs-lookup"><span data-stu-id="8c299-667">Switch to Insert mode.</span></span>

- <span data-ttu-id="8c299-668">Режим команд VI: `<i>`</span><span class="sxs-lookup"><span data-stu-id="8c299-668">Vi command mode: `<i>`</span></span>

### <a name="whatiskey"></a><span data-ttu-id="8c299-669">вхатискэй</span><span class="sxs-lookup"><span data-stu-id="8c299-669">WhatIsKey</span></span>

<span data-ttu-id="8c299-670">Прочитайте ключ и расскажите, к чему привязан ключ.</span><span class="sxs-lookup"><span data-stu-id="8c299-670">Read a key and tell me what the key is bound to.</span></span>

- <span data-ttu-id="8c299-671">Процессор `<Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="8c299-671">Cmd: `<Alt+?>`</span></span>
- <span data-ttu-id="8c299-672">Emacs: `<Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="8c299-672">Emacs: `<Alt+?>`</span></span>

## <a name="selection-functions"></a><span data-ttu-id="8c299-673">Функции выбора</span><span class="sxs-lookup"><span data-stu-id="8c299-673">Selection functions</span></span>

### <a name="exchangepointandmark"></a><span data-ttu-id="8c299-674">ексчанжепоинтандмарк</span><span class="sxs-lookup"><span data-stu-id="8c299-674">ExchangePointAndMark</span></span>

<span data-ttu-id="8c299-675">Курсор помещается в позицию метки, а метка перемещается в положение курсора.</span><span class="sxs-lookup"><span data-stu-id="8c299-675">The cursor is placed at the location of the mark and the mark is moved to the location of the cursor.</span></span>

- <span data-ttu-id="8c299-676">Emacs: `<Ctrl+x,Ctrl+x>`</span><span class="sxs-lookup"><span data-stu-id="8c299-676">Emacs: `<Ctrl+x,Ctrl+x>`</span></span>

### <a name="selectall"></a><span data-ttu-id="8c299-677">SelectAll</span><span class="sxs-lookup"><span data-stu-id="8c299-677">SelectAll</span></span>

<span data-ttu-id="8c299-678">Выделите всю строку.</span><span class="sxs-lookup"><span data-stu-id="8c299-678">Select the entire line.</span></span>

- <span data-ttu-id="8c299-679">Процессор `<Ctrl+a>`</span><span class="sxs-lookup"><span data-stu-id="8c299-679">Cmd: `<Ctrl+a>`</span></span>

### <a name="selectbackwardchar"></a><span data-ttu-id="8c299-680">селектбакквардчар</span><span class="sxs-lookup"><span data-stu-id="8c299-680">SelectBackwardChar</span></span>

<span data-ttu-id="8c299-681">Настройка текущего выделения для включения предыдущего символа.</span><span class="sxs-lookup"><span data-stu-id="8c299-681">Adjust the current selection to include the previous character.</span></span>

- <span data-ttu-id="8c299-682">Процессор `<Shift+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="8c299-682">Cmd: `<Shift+LeftArrow>`</span></span>
- <span data-ttu-id="8c299-683">Emacs: `<Shift+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="8c299-683">Emacs: `<Shift+LeftArrow>`</span></span>

### <a name="selectbackwardsline"></a><span data-ttu-id="8c299-684">селектбакквардслине</span><span class="sxs-lookup"><span data-stu-id="8c299-684">SelectBackwardsLine</span></span>

<span data-ttu-id="8c299-685">Изменить текущее выделение, чтобы включить его от курсора до начала строки.</span><span class="sxs-lookup"><span data-stu-id="8c299-685">Adjust the current selection to include from the cursor to the start of the line.</span></span>

- <span data-ttu-id="8c299-686">Процессор `<Shift+Home>`</span><span class="sxs-lookup"><span data-stu-id="8c299-686">Cmd: `<Shift+Home>`</span></span>
- <span data-ttu-id="8c299-687">Emacs: `<Shift+Home>`</span><span class="sxs-lookup"><span data-stu-id="8c299-687">Emacs: `<Shift+Home>`</span></span>

### <a name="selectbackwardword"></a><span data-ttu-id="8c299-688">селектбакквардворд</span><span class="sxs-lookup"><span data-stu-id="8c299-688">SelectBackwardWord</span></span>

<span data-ttu-id="8c299-689">Настройка текущего выделения для включения предыдущего слова.</span><span class="sxs-lookup"><span data-stu-id="8c299-689">Adjust the current selection to include the previous word.</span></span>

- <span data-ttu-id="8c299-690">Процессор `<Shift+Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="8c299-690">Cmd: `<Shift+Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="8c299-691">Emacs: `<Alt+B>`</span><span class="sxs-lookup"><span data-stu-id="8c299-691">Emacs: `<Alt+B>`</span></span>

### <a name="selectforwardchar"></a><span data-ttu-id="8c299-692">селектфорвардчар</span><span class="sxs-lookup"><span data-stu-id="8c299-692">SelectForwardChar</span></span>

<span data-ttu-id="8c299-693">Измените текущее выделение, чтобы включить следующий символ.</span><span class="sxs-lookup"><span data-stu-id="8c299-693">Adjust the current selection to include the next character.</span></span>

- <span data-ttu-id="8c299-694">Процессор `<Shift+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="8c299-694">Cmd: `<Shift+RightArrow>`</span></span>
- <span data-ttu-id="8c299-695">Emacs: `<Shift+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="8c299-695">Emacs: `<Shift+RightArrow>`</span></span>

### <a name="selectforwardword"></a><span data-ttu-id="8c299-696">селектфорвардворд</span><span class="sxs-lookup"><span data-stu-id="8c299-696">SelectForwardWord</span></span>

<span data-ttu-id="8c299-697">Измените текущее выделение, чтобы включить следующее слово с помощью Форвардворд.</span><span class="sxs-lookup"><span data-stu-id="8c299-697">Adjust the current selection to include the next word using ForwardWord.</span></span>

- <span data-ttu-id="8c299-698">Emacs: `<Alt+F>`</span><span class="sxs-lookup"><span data-stu-id="8c299-698">Emacs: `<Alt+F>`</span></span>

### <a name="selectline"></a><span data-ttu-id="8c299-699">селектлине</span><span class="sxs-lookup"><span data-stu-id="8c299-699">SelectLine</span></span>

<span data-ttu-id="8c299-700">Настройка текущего выделения для включения курсора в конец строки.</span><span class="sxs-lookup"><span data-stu-id="8c299-700">Adjust the current selection to include from the cursor to the end of the line.</span></span>

- <span data-ttu-id="8c299-701">Процессор `<Shift+End>`</span><span class="sxs-lookup"><span data-stu-id="8c299-701">Cmd: `<Shift+End>`</span></span>
- <span data-ttu-id="8c299-702">Emacs: `<Shift+End>`</span><span class="sxs-lookup"><span data-stu-id="8c299-702">Emacs: `<Shift+End>`</span></span>

### <a name="selectnextword"></a><span data-ttu-id="8c299-703">селектнекстворд</span><span class="sxs-lookup"><span data-stu-id="8c299-703">SelectNextWord</span></span>

<span data-ttu-id="8c299-704">Настройка текущего выделения для включения следующего слова.</span><span class="sxs-lookup"><span data-stu-id="8c299-704">Adjust the current selection to include the next word.</span></span>

- <span data-ttu-id="8c299-705">Процессор `<Shift+Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="8c299-705">Cmd: `<Shift+Ctrl+RightArrow>`</span></span>

### <a name="selectshellbackwardword"></a><span data-ttu-id="8c299-706">селектшеллбакквардворд</span><span class="sxs-lookup"><span data-stu-id="8c299-706">SelectShellBackwardWord</span></span>

<span data-ttu-id="8c299-707">Измените текущее выделение, чтобы включить предыдущее слово с помощью Шеллбакквардворд.</span><span class="sxs-lookup"><span data-stu-id="8c299-707">Adjust the current selection to include the previous word using ShellBackwardWord.</span></span>

- <span data-ttu-id="8c299-708">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="8c299-708">Function is unbound.</span></span>

### <a name="selectshellforwardword"></a><span data-ttu-id="8c299-709">селектшеллфорвардворд</span><span class="sxs-lookup"><span data-stu-id="8c299-709">SelectShellForwardWord</span></span>

<span data-ttu-id="8c299-710">Измените текущее выделение, чтобы включить следующее слово с помощью Шеллфорвардворд.</span><span class="sxs-lookup"><span data-stu-id="8c299-710">Adjust the current selection to include the next word using ShellForwardWord.</span></span>

- <span data-ttu-id="8c299-711">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="8c299-711">Function is unbound.</span></span>

### <a name="selectshellnextword"></a><span data-ttu-id="8c299-712">селектшеллнекстворд</span><span class="sxs-lookup"><span data-stu-id="8c299-712">SelectShellNextWord</span></span>

<span data-ttu-id="8c299-713">Измените текущее выделение, чтобы включить следующее слово с помощью Шеллнекстворд.</span><span class="sxs-lookup"><span data-stu-id="8c299-713">Adjust the current selection to include the next word using ShellNextWord.</span></span>

- <span data-ttu-id="8c299-714">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="8c299-714">Function is unbound.</span></span>

### <a name="setmark"></a><span data-ttu-id="8c299-715">сетмарк</span><span class="sxs-lookup"><span data-stu-id="8c299-715">SetMark</span></span>

<span data-ttu-id="8c299-716">Пометка текущего положения курсора для использования в последующей команде редактирования.</span><span class="sxs-lookup"><span data-stu-id="8c299-716">Mark the current location of the cursor for use in a subsequent editing command.</span></span>

- <span data-ttu-id="8c299-717">Emacs: `<Ctrl+`>\`</span><span class="sxs-lookup"><span data-stu-id="8c299-717">Emacs: `<Ctrl+`>\`</span></span>

## <a name="search-functions"></a><span data-ttu-id="8c299-718">Функции поиска</span><span class="sxs-lookup"><span data-stu-id="8c299-718">Search functions</span></span>

### <a name="charactersearch"></a><span data-ttu-id="8c299-719">чарактерсеарч</span><span class="sxs-lookup"><span data-stu-id="8c299-719">CharacterSearch</span></span>

<span data-ttu-id="8c299-720">Чтение символа и поиск вперед для следующего вхождения этого символа.</span><span class="sxs-lookup"><span data-stu-id="8c299-720">Read a character and search forward for the next occurrence of that character.</span></span>
<span data-ttu-id="8c299-721">Если указан аргумент, то для n-го вхождения выполните поиск вперед (или назад, если отрицательное).</span><span class="sxs-lookup"><span data-stu-id="8c299-721">If an argument is specified, search forward (or backward if negative) for the nth occurrence.</span></span>

- <span data-ttu-id="8c299-722">Процессор `<F3>`</span><span class="sxs-lookup"><span data-stu-id="8c299-722">Cmd: `<F3>`</span></span>
- <span data-ttu-id="8c299-723">Emacs: `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="8c299-723">Emacs: `<Ctrl+]>`</span></span>
- <span data-ttu-id="8c299-724">Режим вставки в VI: `<F3>`</span><span class="sxs-lookup"><span data-stu-id="8c299-724">Vi insert mode: `<F3>`</span></span>
- <span data-ttu-id="8c299-725">Режим команд VI: `<F3>`</span><span class="sxs-lookup"><span data-stu-id="8c299-725">Vi command mode: `<F3>`</span></span>

### <a name="charactersearchbackward"></a><span data-ttu-id="8c299-726">чарактерсеарчбакквард</span><span class="sxs-lookup"><span data-stu-id="8c299-726">CharacterSearchBackward</span></span>

<span data-ttu-id="8c299-727">Чтение символа и поиск следующего вхождения этого символа в обратном направлении.</span><span class="sxs-lookup"><span data-stu-id="8c299-727">Read a character and search backward for the next occurrence of that character.</span></span> <span data-ttu-id="8c299-728">Если аргумент указан, поиск в n-й последовательности осуществляется назад (или вперед, если отрицательное).</span><span class="sxs-lookup"><span data-stu-id="8c299-728">If an argument is specified, search backward (or forward if negative) for the nth occurrence.</span></span>

- <span data-ttu-id="8c299-729">Процессор `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="8c299-729">Cmd: `<Shift+F3>`</span></span>
- <span data-ttu-id="8c299-730">Emacs: `<Ctrl+Alt+]>`</span><span class="sxs-lookup"><span data-stu-id="8c299-730">Emacs: `<Ctrl+Alt+]>`</span></span>
- <span data-ttu-id="8c299-731">Режим вставки в VI: `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="8c299-731">Vi insert mode: `<Shift+F3>`</span></span>
- <span data-ttu-id="8c299-732">Режим команд VI: `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="8c299-732">Vi command mode: `<Shift+F3>`</span></span>

### <a name="repeatlastcharsearch"></a><span data-ttu-id="8c299-733">репеатластчарсеарч</span><span class="sxs-lookup"><span data-stu-id="8c299-733">RepeatLastCharSearch</span></span>

<span data-ttu-id="8c299-734">Повторите поиск последнего записанного символа.</span><span class="sxs-lookup"><span data-stu-id="8c299-734">Repeat the last recorded character search.</span></span>

- <span data-ttu-id="8c299-735">Режим команд VI: `<;>`</span><span class="sxs-lookup"><span data-stu-id="8c299-735">Vi command mode: `<;>`</span></span>

### <a name="repeatlastcharsearchbackwards"></a><span data-ttu-id="8c299-736">репеатластчарсеарчбакквардс</span><span class="sxs-lookup"><span data-stu-id="8c299-736">RepeatLastCharSearchBackwards</span></span>

<span data-ttu-id="8c299-737">Повторите поиск последнего записанного символа, но в обратном направлении.</span><span class="sxs-lookup"><span data-stu-id="8c299-737">Repeat the last recorded character search, but in the opposite direction.</span></span>

- <span data-ttu-id="8c299-738">Режим команд VI: `<,>`</span><span class="sxs-lookup"><span data-stu-id="8c299-738">Vi command mode: `<,>`</span></span>

### <a name="repeatsearch"></a><span data-ttu-id="8c299-739">репеатсеарч</span><span class="sxs-lookup"><span data-stu-id="8c299-739">RepeatSearch</span></span>

<span data-ttu-id="8c299-740">Повторите последний поиск в том же направлении, что и раньше.</span><span class="sxs-lookup"><span data-stu-id="8c299-740">Repeat the last search in the same direction as before.</span></span>

- <span data-ttu-id="8c299-741">Режим команд VI: `<n>`</span><span class="sxs-lookup"><span data-stu-id="8c299-741">Vi command mode: `<n>`</span></span>

### <a name="repeatsearchbackward"></a><span data-ttu-id="8c299-742">репеатсеарчбакквард</span><span class="sxs-lookup"><span data-stu-id="8c299-742">RepeatSearchBackward</span></span>

<span data-ttu-id="8c299-743">Повторите последний поиск в том же направлении, что и раньше.</span><span class="sxs-lookup"><span data-stu-id="8c299-743">Repeat the last search in the same direction as before.</span></span>

- <span data-ttu-id="8c299-744">Режим команд VI: `<N>`</span><span class="sxs-lookup"><span data-stu-id="8c299-744">Vi command mode: `<N>`</span></span>

### <a name="searchchar"></a><span data-ttu-id="8c299-745">сеарччар</span><span class="sxs-lookup"><span data-stu-id="8c299-745">SearchChar</span></span>

<span data-ttu-id="8c299-746">Прочитать следующий символ, затем найти его, перейти вперед, а затем отследить символ.</span><span class="sxs-lookup"><span data-stu-id="8c299-746">Read the next character and then find it, going forward, and then back off a character.</span></span> <span data-ttu-id="8c299-747">Это относится к функциональным возможностям.</span><span class="sxs-lookup"><span data-stu-id="8c299-747">This is for 't' functionality.</span></span>

- <span data-ttu-id="8c299-748">Режим команд VI: `<f>`</span><span class="sxs-lookup"><span data-stu-id="8c299-748">Vi command mode: `<f>`</span></span>

### <a name="searchcharbackward"></a><span data-ttu-id="8c299-749">сеарччарбакквард</span><span class="sxs-lookup"><span data-stu-id="8c299-749">SearchCharBackward</span></span>

<span data-ttu-id="8c299-750">Прочитать следующий символ, а затем найти его, вернуться назад, а затем отследить символ.</span><span class="sxs-lookup"><span data-stu-id="8c299-750">Read the next character and then find it, going backward, and then back off a character.</span></span> <span data-ttu-id="8c299-751">Это относится к функциональным возможностям.</span><span class="sxs-lookup"><span data-stu-id="8c299-751">This is for 'T' functionality.</span></span>

- <span data-ttu-id="8c299-752">Режим команд VI: `<F>`</span><span class="sxs-lookup"><span data-stu-id="8c299-752">Vi command mode: `<F>`</span></span>

### <a name="searchcharbackwardwithbackoff"></a><span data-ttu-id="8c299-753">сеарччарбакквардвисбаккофф</span><span class="sxs-lookup"><span data-stu-id="8c299-753">SearchCharBackwardWithBackoff</span></span>

<span data-ttu-id="8c299-754">Прочитать следующий символ, а затем найти его, вернуться назад, а затем отследить символ.</span><span class="sxs-lookup"><span data-stu-id="8c299-754">Read the next character and then find it, going backward, and then back off a character.</span></span> <span data-ttu-id="8c299-755">Это относится к функциональным возможностям.</span><span class="sxs-lookup"><span data-stu-id="8c299-755">This is for 'T' functionality.</span></span>

- <span data-ttu-id="8c299-756">Режим команд VI: `<T>`</span><span class="sxs-lookup"><span data-stu-id="8c299-756">Vi command mode: `<T>`</span></span>

### <a name="searchcharwithbackoff"></a><span data-ttu-id="8c299-757">сеарччарвисбаккофф</span><span class="sxs-lookup"><span data-stu-id="8c299-757">SearchCharWithBackoff</span></span>

<span data-ttu-id="8c299-758">Прочитать следующий символ, затем найти его, перейти вперед, а затем отследить символ.</span><span class="sxs-lookup"><span data-stu-id="8c299-758">Read the next character and then find it, going forward, and then back off a character.</span></span> <span data-ttu-id="8c299-759">Это относится к функциональным возможностям.</span><span class="sxs-lookup"><span data-stu-id="8c299-759">This is for 't' functionality.</span></span>

- <span data-ttu-id="8c299-760">Режим команд VI: `<t>`</span><span class="sxs-lookup"><span data-stu-id="8c299-760">Vi command mode: `<t>`</span></span>

### <a name="searchforward"></a><span data-ttu-id="8c299-761">сеарчфорвард</span><span class="sxs-lookup"><span data-stu-id="8c299-761">SearchForward</span></span>

<span data-ttu-id="8c299-762">Запрашивает строку поиска и инициирует поиск по запросу Акцептлине.</span><span class="sxs-lookup"><span data-stu-id="8c299-762">Prompts for a search string and initiates search upon AcceptLine.</span></span>

- <span data-ttu-id="8c299-763">Режим вставки в VI: `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="8c299-763">Vi insert mode: `<Ctrl+s>`</span></span>
- <span data-ttu-id="8c299-764">Режим команд VI: `<?>` , `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="8c299-764">Vi command mode: `<?>`, `<Ctrl+s>`</span></span>

## <a name="custom-key-bindings"></a><span data-ttu-id="8c299-765">Пользовательские привязки клавиш</span><span class="sxs-lookup"><span data-stu-id="8c299-765">Custom Key Bindings</span></span>

<span data-ttu-id="8c299-766">PSReadLine поддерживает пользовательские привязки клавиш с помощью командлета `Set-PSReadLineKeyHandler` .</span><span class="sxs-lookup"><span data-stu-id="8c299-766">PSReadLine supports custom key bindings using the cmdlet `Set-PSReadLineKeyHandler`.</span></span> <span data-ttu-id="8c299-767">Большинство пользовательских привязок вызывают одну из приведенных выше функций, например</span><span class="sxs-lookup"><span data-stu-id="8c299-767">Most custom key bindings call one of the above functions, for example</span></span>

```powershell
Set-PSReadLineKeyHandler -Key UpArrow -Function HistorySearchBackward
```

<span data-ttu-id="8c299-768">Можно привязать ScriptBlock к ключу.</span><span class="sxs-lookup"><span data-stu-id="8c299-768">You can bind a ScriptBlock to a key.</span></span> <span data-ttu-id="8c299-769">Блок ScriptBlock может выполнять практически все необходимые действия.</span><span class="sxs-lookup"><span data-stu-id="8c299-769">The ScriptBlock can do pretty much anything you want.</span></span> <span data-ttu-id="8c299-770">Ниже приведены некоторые полезные примеры.</span><span class="sxs-lookup"><span data-stu-id="8c299-770">Some useful examples include</span></span>

- <span data-ttu-id="8c299-771">Изменение командной строки</span><span class="sxs-lookup"><span data-stu-id="8c299-771">edit the command line</span></span>
- <span data-ttu-id="8c299-772">Открытие нового окна (например, Справка)</span><span class="sxs-lookup"><span data-stu-id="8c299-772">opening a new window (e.g. help)</span></span>
- <span data-ttu-id="8c299-773">Изменение каталогов без изменения командной строки</span><span class="sxs-lookup"><span data-stu-id="8c299-773">change directories without changing the command line</span></span>

<span data-ttu-id="8c299-774">Блок ScriptBlock получает два аргумента:</span><span class="sxs-lookup"><span data-stu-id="8c299-774">The ScriptBlock receives two arguments:</span></span>

- <span data-ttu-id="8c299-775">`$key` — Объект **[консолекэйинфо]** , который является ключом, запускающим пользовательскую привязку.</span><span class="sxs-lookup"><span data-stu-id="8c299-775">`$key` - A **[ConsoleKeyInfo]** object that is the key that triggered the custom binding.</span></span> <span data-ttu-id="8c299-776">Если один и тот же блок сценария привязан к нескольким ключам и необходимо выполнять различные действия в зависимости от ключа, можно проверить $key.</span><span class="sxs-lookup"><span data-stu-id="8c299-776">If you bind the same ScriptBlock to multiple keys and need to perform different actions depending on the key, you can check $key.</span></span> <span data-ttu-id="8c299-777">Многие пользовательские привязки игнорируют этот аргумент.</span><span class="sxs-lookup"><span data-stu-id="8c299-777">Many custom bindings ignore this argument.</span></span>

- <span data-ttu-id="8c299-778">`$arg` — Произвольный аргумент.</span><span class="sxs-lookup"><span data-stu-id="8c299-778">`$arg` - An arbitrary argument.</span></span> <span data-ttu-id="8c299-779">Чаще всего это будет целочисленный аргумент, который пользователь передает из ключевых привязок Дигитаргумент.</span><span class="sxs-lookup"><span data-stu-id="8c299-779">Most often, this would be an integer argument that the user passes from the key bindings DigitArgument.</span></span> <span data-ttu-id="8c299-780">Если привязка не принимает аргументы, целесообразно проигнорировать этот аргумент.</span><span class="sxs-lookup"><span data-stu-id="8c299-780">If your binding doesn't accept arguments, it's reasonable to ignore this argument.</span></span>

<span data-ttu-id="8c299-781">Рассмотрим пример, который добавляет в журнал командную строку, не выполняя ее.</span><span class="sxs-lookup"><span data-stu-id="8c299-781">Let's take a look at an example that adds a command line to history without executing it.</span></span> <span data-ttu-id="8c299-782">Это полезно, если вы забыли сделать что-то, но не хотите повторно вводить уже введенную командную строку.</span><span class="sxs-lookup"><span data-stu-id="8c299-782">This is useful when you realize you forgot to do something, but don't want to re-enter the command line you've already entered.</span></span>

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

<span data-ttu-id="8c299-783">В файле, `SamplePSReadLineProfile.ps1` который устанавливается в папку модуля PSReadLine, можно увидеть много других примеров.</span><span class="sxs-lookup"><span data-stu-id="8c299-783">You can see many more examples in the file `SamplePSReadLineProfile.ps1` which is installed in the PSReadLine module folder.</span></span>

<span data-ttu-id="8c299-784">Большинство ключевых привязок используют некоторые вспомогательные функции для редактирования командной строки.</span><span class="sxs-lookup"><span data-stu-id="8c299-784">Most key bindings use some helper functions for editing the command line.</span></span>
<span data-ttu-id="8c299-785">Эти API-интерфейсы описаны в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="8c299-785">Those APIs are documented in the next section.</span></span>

## <a name="custom-key-binding-support-apis"></a><span data-ttu-id="8c299-786">API поддержки пользовательского сочетания клавиш</span><span class="sxs-lookup"><span data-stu-id="8c299-786">Custom Key Binding Support APIs</span></span>

<span data-ttu-id="8c299-787">Следующие функции являются открытыми в Microsoft. PowerShell. Псконсолереадлине, но не могут быть напрямую привязаны к ключу.</span><span class="sxs-lookup"><span data-stu-id="8c299-787">The following functions are public in Microsoft.PowerShell.PSConsoleReadLine, but cannot be directly bound to a key.</span></span> <span data-ttu-id="8c299-788">Большинство из них удобно использовать в пользовательских привязках клавиш.</span><span class="sxs-lookup"><span data-stu-id="8c299-788">Most are useful in custom key bindings.</span></span>

```csharp
void AddToHistory(string command)
```

<span data-ttu-id="8c299-789">Добавьте командную строку в журнал, не выполняя ее.</span><span class="sxs-lookup"><span data-stu-id="8c299-789">Add a command line to history without executing it.</span></span>

```csharp
void ClearKillRing()
```

<span data-ttu-id="8c299-790">Снимите флажок Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="8c299-790">Clear the kill-ring.</span></span>  <span data-ttu-id="8c299-791">Это в основном используется для тестирования.</span><span class="sxs-lookup"><span data-stu-id="8c299-791">This is mostly used for testing.</span></span>

```csharp
void Delete(int start, int length)
```

<span data-ttu-id="8c299-792">Удалить символы длины из Start.</span><span class="sxs-lookup"><span data-stu-id="8c299-792">Delete length characters from start.</span></span>  <span data-ttu-id="8c299-793">Эта операция поддерживает операцию отмены и повтора.</span><span class="sxs-lookup"><span data-stu-id="8c299-793">This operation supports undo/redo.</span></span>

```csharp
void Ding()
```

<span data-ttu-id="8c299-794">Выполните действие DING, основанное на предпочтениях пользователей.</span><span class="sxs-lookup"><span data-stu-id="8c299-794">Perform the Ding action based on the users preference.</span></span>

```csharp
void GetBufferState([ref] string input, [ref] int cursor)
void GetBufferState([ref] Ast ast, [ref] Token[] tokens,
  [ref] ParseError[] parseErrors, [ref] int cursor)
```

<span data-ttu-id="8c299-795">Эти две функции извлекают полезную информацию о текущем состоянии входного буфера.</span><span class="sxs-lookup"><span data-stu-id="8c299-795">These two functions retrieve useful information about the current state of the input buffer.</span></span>  <span data-ttu-id="8c299-796">Первый из них чаще всего используется в простых случаях.</span><span class="sxs-lookup"><span data-stu-id="8c299-796">The first is more commonly used for simple cases.</span></span>  <span data-ttu-id="8c299-797">Второй используется, если привязка делает что-то более сложное с AST.</span><span class="sxs-lookup"><span data-stu-id="8c299-797">The second is used if your binding is doing something more advanced with the Ast.</span></span>

```csharp
IEnumerable[Microsoft.PowerShell.KeyHandler]
  GetKeyHandlers(bool includeBound, bool includeUnbound)

```

<span data-ttu-id="8c299-798">Эта функция используется Get-PSReadLineKeyHandler и, возможно, не полезна в пользовательской привязке ключа.</span><span class="sxs-lookup"><span data-stu-id="8c299-798">This function is used by Get-PSReadLineKeyHandler and probably isn't useful in a custom key binding.</span></span>

```csharp
Microsoft.PowerShell.PSConsoleReadLineOptions GetOptions()
```

<span data-ttu-id="8c299-799">Эта функция используется Get-PSReadLineOption и, возможно, не слишком полезна в пользовательской привязке ключа.</span><span class="sxs-lookup"><span data-stu-id="8c299-799">This function is used by Get-PSReadLineOption and probably isn't too useful in a custom key binding.</span></span>

```csharp
void GetSelectionState([ref] int start, [ref] int length)
```

<span data-ttu-id="8c299-800">Если в командной строке ничего не выбрано, значение-1 будет возвращено как в начале, так и в длине.</span><span class="sxs-lookup"><span data-stu-id="8c299-800">If there is no selection on the command line, -1 will be returned in both start and length.</span></span> <span data-ttu-id="8c299-801">Если в командной строке имеется выделенный фрагмент, то начинается и длина выбора возвращается.</span><span class="sxs-lookup"><span data-stu-id="8c299-801">If there is a selection on the command line, the start and length of the selection are returned.</span></span>

```csharp
void Insert(char c)
void Insert(string s)
```

<span data-ttu-id="8c299-802">Вставка символа или строки в курсоре.</span><span class="sxs-lookup"><span data-stu-id="8c299-802">Insert a character or string at the cursor.</span></span>  <span data-ttu-id="8c299-803">Эта операция поддерживает операцию отмены и повтора.</span><span class="sxs-lookup"><span data-stu-id="8c299-803">This operation supports undo/redo.</span></span>

```csharp
string ReadLine(runspace remoteRunspace,
  System.Management.Automation.EngineIntrinsics engineIntrinsics)
```

<span data-ttu-id="8c299-804">Это Главная точка входа для PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="8c299-804">This is the main entry point to PSReadLine.</span></span> <span data-ttu-id="8c299-805">Она не поддерживает рекурсию, поэтому она не полезна в пользовательской привязке ключа.</span><span class="sxs-lookup"><span data-stu-id="8c299-805">It does not support recursion, so is not useful in a custom key binding.</span></span>

```csharp
void RemoveKeyHandler(string[] key)
```

<span data-ttu-id="8c299-806">Эта функция используется Remove-PSReadLineKeyHandler и, возможно, не слишком полезна в пользовательской привязке ключа.</span><span class="sxs-lookup"><span data-stu-id="8c299-806">This function is used by Remove-PSReadLineKeyHandler and probably isn't too useful in a custom key binding.</span></span>

```csharp
void Replace(int start, int length, string replacement)
```

<span data-ttu-id="8c299-807">Замените некоторые входные данные.</span><span class="sxs-lookup"><span data-stu-id="8c299-807">Replace some of the input.</span></span> <span data-ttu-id="8c299-808">Эта операция поддерживает операцию отмены и повтора.</span><span class="sxs-lookup"><span data-stu-id="8c299-808">This operation supports undo/redo.</span></span> <span data-ttu-id="8c299-809">Это предпочтительнее удаление с последующим вставкой, так как оно обрабатывается как одно действие для отмены.</span><span class="sxs-lookup"><span data-stu-id="8c299-809">This is preferred over Delete followed by Insert because it is treated as a single action for undo.</span></span>

```csharp
void SetCursorPosition(int cursor)
```

<span data-ttu-id="8c299-810">Переместить курсор к заданному смещению.</span><span class="sxs-lookup"><span data-stu-id="8c299-810">Move the cursor to the given offset.</span></span> <span data-ttu-id="8c299-811">Перемещение курсора не ведется для отмены.</span><span class="sxs-lookup"><span data-stu-id="8c299-811">Cursor movement is not tracked for undo.</span></span>

```csharp
void SetOptions(Microsoft.PowerShell.SetPSReadLineOption options)
```

<span data-ttu-id="8c299-812">Эта функция является вспомогательным методом, используемым командлетом Set-PSReadLineOption, но может быть полезен для пользовательской привязки ключа, которая хочет временно изменить параметр.</span><span class="sxs-lookup"><span data-stu-id="8c299-812">This function is a helper method used by the cmdlet Set-PSReadLineOption, but might be useful to a custom key binding that wants to temporarily change a setting.</span></span>

```csharp
bool TryGetArgAsInt(System.Object arg, [ref] int numericArg,
  int defaultNumericArg)
```

<span data-ttu-id="8c299-813">Этот вспомогательный метод используется для пользовательских привязок, которые учитывают Дигитаргумент.</span><span class="sxs-lookup"><span data-stu-id="8c299-813">This helper method is used for custom bindings that honor DigitArgument.</span></span> <span data-ttu-id="8c299-814">Обычный вызов выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="8c299-814">A typical call looks like</span></span>

```powershell
[int]$numericArg = 0
[Microsoft.PowerShell.PSConsoleReadLine]::TryGetArgAsInt($arg,
  [ref]$numericArg, 1)
```

## <a name="note"></a><span data-ttu-id="8c299-815">Примечание</span><span class="sxs-lookup"><span data-stu-id="8c299-815">Note</span></span>

### <a name="command-history"></a><span data-ttu-id="8c299-816">Журнал команд</span><span class="sxs-lookup"><span data-stu-id="8c299-816">Command History</span></span>

<span data-ttu-id="8c299-817">PSReadLine поддерживает файл журнала, содержащий все команды и данные, введенные из командной строки.</span><span class="sxs-lookup"><span data-stu-id="8c299-817">PSReadLine maintains a history file containing all the commands and data you have entered from the command line.</span></span> <span data-ttu-id="8c299-818">Это может быть конфиденциальные данные, включая пароли.</span><span class="sxs-lookup"><span data-stu-id="8c299-818">This may contain sensitive data including passwords.</span></span> <span data-ttu-id="8c299-819">Например, при использовании `ConvertTo-SecureString` командлета пароль заносится в файл журнала в виде обычного текста.</span><span class="sxs-lookup"><span data-stu-id="8c299-819">For example, if you use the `ConvertTo-SecureString` cmdlet the password is logged in the history file as plain text.</span></span> <span data-ttu-id="8c299-820">Файлы журнала — это файл с именем `$($host.Name)_history.txt` .</span><span class="sxs-lookup"><span data-stu-id="8c299-820">The history files is a file named `$($host.Name)_history.txt`.</span></span> <span data-ttu-id="8c299-821">В системах Windows файл журнала хранится в файле `$env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine` .</span><span class="sxs-lookup"><span data-stu-id="8c299-821">On Windows systems the history file is stored at `$env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine`.</span></span>

### <a name="feedback--contributing-to-psreadline"></a><span data-ttu-id="8c299-822">Обратная связь & участие в PSReadLine</span><span class="sxs-lookup"><span data-stu-id="8c299-822">Feedback & Contributing To PSReadLine</span></span>

[<span data-ttu-id="8c299-823">PSReadLine на GitHub</span><span class="sxs-lookup"><span data-stu-id="8c299-823">PSReadLine on GitHub</span></span>](https://github.com/PowerShell/PSReadLine)

<span data-ttu-id="8c299-824">Вы можете отправить запрос на вытягивание или отправить отзыв на страницу GitHub.</span><span class="sxs-lookup"><span data-stu-id="8c299-824">Feel free to submit a pull request or submit feedback on the GitHub page.</span></span>

## <a name="see-also"></a><span data-ttu-id="8c299-825">См. также:</span><span class="sxs-lookup"><span data-stu-id="8c299-825">See Also</span></span>

<span data-ttu-id="8c299-826">На PSReadLine сильно влияют библиотеки GNU [ReadLine](https://tiswww.case.edu/php/chet/readline/rltop.html) .</span><span class="sxs-lookup"><span data-stu-id="8c299-826">PSReadLine is heavily influenced by the GNU [readline](https://tiswww.case.edu/php/chet/readline/rltop.html) library.</span></span>
