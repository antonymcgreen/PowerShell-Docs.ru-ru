---
description: PSReadLine предоставляет улучшенные возможности редактирования командной строки в консоли PowerShell.
keywords: powershell
Locale: en-US
ms.date: 02/10/2020
online version: https://docs.microsoft.com/powershell/module/psreadline/about/about_psreadline?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: О PSReadLine
ms.openlocfilehash: 5b59ffcdfb35c2aa10f8e0caf3a3b365c5bcf93e
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93232510"
---
# <a name="psreadline"></a><span data-ttu-id="f1bd3-104">PSReadLine</span><span class="sxs-lookup"><span data-stu-id="f1bd3-104">PSReadLine</span></span>

## <a name="about_psreadline"></a><span data-ttu-id="f1bd3-105">about_PSReadLine</span><span class="sxs-lookup"><span data-stu-id="f1bd3-105">about_PSReadLine</span></span>

## <a name="short-description"></a><span data-ttu-id="f1bd3-106">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="f1bd3-106">SHORT DESCRIPTION</span></span>

<span data-ttu-id="f1bd3-107">PSReadLine предоставляет улучшенные возможности редактирования командной строки в консоли PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-107">PSReadLine provides an improved command-line editing experience in the PowerShell console.</span></span>

## <a name="long-description"></a><span data-ttu-id="f1bd3-108">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="f1bd3-108">LONG DESCRIPTION</span></span>

<span data-ttu-id="f1bd3-109">PSReadLine 2,0 предоставляет широкие возможности редактирования командной строки для консоли PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-109">PSReadLine 2.0 provides a powerful command-line editing experience for the PowerShell console.</span></span> <span data-ttu-id="f1bd3-110">Консоль предоставляет следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="f1bd3-110">It provides:</span></span>

- <span data-ttu-id="f1bd3-111">Цветовое выделение синтаксиса командной строки</span><span class="sxs-lookup"><span data-stu-id="f1bd3-111">Syntax coloring of the command line</span></span>
- <span data-ttu-id="f1bd3-112">Визуальное обозначение синтаксических ошибок</span><span class="sxs-lookup"><span data-stu-id="f1bd3-112">A visual indication of syntax errors</span></span>
- <span data-ttu-id="f1bd3-113">Более эффективный многострочный интерфейс (как редактирование, так и журнал)</span><span class="sxs-lookup"><span data-stu-id="f1bd3-113">A better multi-line experience (both editing and history)</span></span>
- <span data-ttu-id="f1bd3-114">Настраиваемые сочетания клавиш</span><span class="sxs-lookup"><span data-stu-id="f1bd3-114">Customizable key bindings</span></span>
- <span data-ttu-id="f1bd3-115">Режимы работы cmd и Emacs</span><span class="sxs-lookup"><span data-stu-id="f1bd3-115">Cmd and Emacs modes</span></span>
- <span data-ttu-id="f1bd3-116">Множество параметров конфигурации</span><span class="sxs-lookup"><span data-stu-id="f1bd3-116">Many configuration options</span></span>
- <span data-ttu-id="f1bd3-117">Завершение стиля bash (необязательно в режиме cmd, по умолчанию в режиме Emacs)</span><span class="sxs-lookup"><span data-stu-id="f1bd3-117">Bash style completion (optional in Cmd mode, default in Emacs mode)</span></span>
- <span data-ttu-id="f1bd3-118">Emacs: Янк/Kill-Ring</span><span class="sxs-lookup"><span data-stu-id="f1bd3-118">Emacs yank/kill-ring</span></span>
- <span data-ttu-id="f1bd3-119">Перемещение и уничтожение токена PowerShell на основе маркеров "Word"</span><span class="sxs-lookup"><span data-stu-id="f1bd3-119">PowerShell token based "word" movement and kill</span></span>

<span data-ttu-id="f1bd3-120">В классе **[Microsoft. PowerShell. псконсолереадлине]** доступны следующие функции.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-120">The following functions are available in the class **[Microsoft.PowerShell.PSConsoleReadLine]**.</span></span>

> [!NOTE]
> <span data-ttu-id="f1bd3-121">Начиная с PowerShell 7,0, PowerShell пропускает автоматическую загрузку PSReadLine в Windows при обнаружении программы чтения с экрана.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-121">Beginning with PowerShell 7.0, PowerShell skips auto-loading PSReadLine on Windows if a screen reader program is detected.</span></span> <span data-ttu-id="f1bd3-122">В настоящее время PSReadLine плохо работает с программами чтения с экрана.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-122">Currently, PSReadLine doesn't work well with the screen readers.</span></span> <span data-ttu-id="f1bd3-123">Визуализация и форматирование по умолчанию для PowerShell 7,0 в Windows работают правильно.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-123">The default rendering and formatting of PowerShell 7.0 on Windows works properly.</span></span> <span data-ttu-id="f1bd3-124">При необходимости модуль можно загрузить вручную.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-124">You can manually load the module if necessary.</span></span>

## <a name="basic-editing-functions"></a><span data-ttu-id="f1bd3-125">Базовые функции редактирования</span><span class="sxs-lookup"><span data-stu-id="f1bd3-125">Basic editing functions</span></span>

### <a name="abort"></a><span data-ttu-id="f1bd3-126">Прерывание</span><span class="sxs-lookup"><span data-stu-id="f1bd3-126">Abort</span></span>

<span data-ttu-id="f1bd3-127">Прервать текущее действие, например добавочный поиск по журналу.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-127">Abort current action, e.g. incremental history search.</span></span>

- <span data-ttu-id="f1bd3-128">Emacs: `<Ctrl+g>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-128">Emacs: `<Ctrl+g>`</span></span>

### <a name="acceptandgetnext"></a><span data-ttu-id="f1bd3-129">акцептанджетнекст</span><span class="sxs-lookup"><span data-stu-id="f1bd3-129">AcceptAndGetNext</span></span>

<span data-ttu-id="f1bd3-130">Попытка выполнить текущий вход.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-130">Attempt to execute the current input.</span></span> <span data-ttu-id="f1bd3-131">Если его можно выполнить (например, Акцептлине), то следует отозвать следующий элемент из журнала при следующем вызове метода ReadLine.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-131">If it can be executed (like AcceptLine), then recall the next item from history the next time ReadLine is called.</span></span>

- <span data-ttu-id="f1bd3-132">Emacs: `<Ctrl+o>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-132">Emacs: `<Ctrl+o>`</span></span>

### <a name="acceptline"></a><span data-ttu-id="f1bd3-133">акцептлине</span><span class="sxs-lookup"><span data-stu-id="f1bd3-133">AcceptLine</span></span>

<span data-ttu-id="f1bd3-134">Попытка выполнить текущий вход.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-134">Attempt to execute the current input.</span></span> <span data-ttu-id="f1bd3-135">Если текущий ввод неполон (например, отсутствует закрывающая круглая скобка, квадратная скобка или кавычка, запрос продолжения отображается на следующей строке, а PSReadLine ожидает ввода ключей для изменения текущих входных данных.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-135">If the current input is incomplete (for example there is a missing closing parenthesis, bracket, or quote, then the continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span>

- <span data-ttu-id="f1bd3-136">Процессор `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-136">Cmd: `<Enter>`</span></span>
- <span data-ttu-id="f1bd3-137">Emacs: `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-137">Emacs: `<Enter>`</span></span>
- <span data-ttu-id="f1bd3-138">Режим вставки в VI: `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-138">Vi insert mode: `<Enter>`</span></span>

### <a name="addline"></a><span data-ttu-id="f1bd3-139">аддлине</span><span class="sxs-lookup"><span data-stu-id="f1bd3-139">AddLine</span></span>

<span data-ttu-id="f1bd3-140">Запрос продолжения отображается на следующей строке, а PSReadLine ожидает ввода ключей для изменения текущих входных данных.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-140">The continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span> <span data-ttu-id="f1bd3-141">Это полезно для ввода многострочных входных данных в виде одной команды, даже если одна строка завершается самим вводом.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-141">This is useful to enter multi-line input as a single command even when a single line is complete input by itself.</span></span>

- <span data-ttu-id="f1bd3-142">Процессор `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-142">Cmd: `<Shift+Enter>`</span></span>
- <span data-ttu-id="f1bd3-143">Emacs: `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-143">Emacs: `<Shift+Enter>`</span></span>
- <span data-ttu-id="f1bd3-144">Режим вставки в VI: `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-144">Vi insert mode: `<Shift+Enter>`</span></span>
- <span data-ttu-id="f1bd3-145">Режим команд VI: `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-145">Vi command mode: `<Shift+Enter>`</span></span>

### <a name="backwarddeletechar"></a><span data-ttu-id="f1bd3-146">бакквардделетечар</span><span class="sxs-lookup"><span data-stu-id="f1bd3-146">BackwardDeleteChar</span></span>

<span data-ttu-id="f1bd3-147">Удалить символ перед курсором.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-147">Delete the character before the cursor.</span></span>

- <span data-ttu-id="f1bd3-148">Cmd: `<Backspace>` , `<Ctrl+h>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-148">Cmd: `<Backspace>`, `<Ctrl+h>`</span></span>
- <span data-ttu-id="f1bd3-149">Emacs: `<Backspace>` , `<Ctrl+Backspace>` , `<Ctrl+h>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-149">Emacs: `<Backspace>`, `<Ctrl+Backspace>`, `<Ctrl+h>`</span></span>
- <span data-ttu-id="f1bd3-150">Режим вставки в VI: `<Backspace>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-150">Vi insert mode: `<Backspace>`</span></span>
- <span data-ttu-id="f1bd3-151">Режим команд VI: `<X>` , `<d,h>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-151">Vi command mode: `<X>`, `<d,h>`</span></span>

### <a name="backwarddeleteline"></a><span data-ttu-id="f1bd3-152">бакквардделетелине</span><span class="sxs-lookup"><span data-stu-id="f1bd3-152">BackwardDeleteLine</span></span>

<span data-ttu-id="f1bd3-153">Like Бакквардкилллине — удаляет текст с точки до начала строки, но не помещает удаленный текст в инструкцию KILL-Ring.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-153">Like BackwardKillLine - deletes text from the point to the start of the line, but does not put the deleted text in the kill-ring.</span></span>

- <span data-ttu-id="f1bd3-154">Процессор `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-154">Cmd: `<Ctrl+Home>`</span></span>
- <span data-ttu-id="f1bd3-155">Режим вставки в VI: `<Ctrl+u>` , `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-155">Vi insert mode: `<Ctrl+u>`, `<Ctrl+Home>`</span></span>
- <span data-ttu-id="f1bd3-156">Режим команд VI: `<Ctrl+u>` , `<Ctrl+Home>` , `<d,0>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-156">Vi command mode: `<Ctrl+u>`, `<Ctrl+Home>`, `<d,0>`</span></span>

### <a name="backwarddeleteword"></a><span data-ttu-id="f1bd3-157">бакквардделетеворд</span><span class="sxs-lookup"><span data-stu-id="f1bd3-157">BackwardDeleteWord</span></span>

<span data-ttu-id="f1bd3-158">Удаляет предыдущее слово.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-158">Deletes the previous word.</span></span>

- <span data-ttu-id="f1bd3-159">Режим команд VI: `<Ctrl+w>` , `<d,b>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-159">Vi command mode: `<Ctrl+w>`, `<d,b>`</span></span>

### <a name="backwardkillline"></a><span data-ttu-id="f1bd3-160">бакквардкилллине</span><span class="sxs-lookup"><span data-stu-id="f1bd3-160">BackwardKillLine</span></span>

<span data-ttu-id="f1bd3-161">Очистить входные данные от начала ввода до курсора.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-161">Clear the input from the start of the input to the cursor.</span></span> <span data-ttu-id="f1bd3-162">Очистка текста помещается в буфер Kill.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-162">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="f1bd3-163">Emacs: `<Ctrl+u>` , `<Ctrl+x,Backspace>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-163">Emacs: `<Ctrl+u>`, `<Ctrl+x,Backspace>`</span></span>

### <a name="backwardkillword"></a><span data-ttu-id="f1bd3-164">бакквардкиллворд</span><span class="sxs-lookup"><span data-stu-id="f1bd3-164">BackwardKillWord</span></span>

<span data-ttu-id="f1bd3-165">Очистить ввод от начала текущего слова до курсора.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-165">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="f1bd3-166">Если курсор находится между словами, входные данные очищаются от начала предыдущего слова до курсора.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-166">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="f1bd3-167">Очистка текста помещается в буфер Kill.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-167">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="f1bd3-168">Процессор `<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-168">Cmd: `<Ctrl+Backspace>`</span></span>
- <span data-ttu-id="f1bd3-169">Emacs: `<Alt+Backspace>` , `<Escape,Backspace>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-169">Emacs: `<Alt+Backspace>`, `<Escape,Backspace>`</span></span>
- <span data-ttu-id="f1bd3-170">Режим вставки в VI: `<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-170">Vi insert mode: `<Ctrl+Backspace>`</span></span>
- <span data-ttu-id="f1bd3-171">Режим команд VI: `<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-171">Vi command mode: `<Ctrl+Backspace>`</span></span>

### <a name="cancelline"></a><span data-ttu-id="f1bd3-172">канцеллине</span><span class="sxs-lookup"><span data-stu-id="f1bd3-172">CancelLine</span></span>

<span data-ttu-id="f1bd3-173">Отмена текущих входных данных с выходом на экран, но возврат к узлу, чтобы снова выполнить оценку запроса.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-173">Cancel the current input, leaving the input on the screen, but returns back to the host so the prompt is evaluated again.</span></span>

- <span data-ttu-id="f1bd3-174">Режим вставки в VI: `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-174">Vi insert mode: `<Ctrl+c>`</span></span>
- <span data-ttu-id="f1bd3-175">Режим команд VI: `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-175">Vi command mode: `<Ctrl+c>`</span></span>

### <a name="copy"></a><span data-ttu-id="f1bd3-176">Копировать</span><span class="sxs-lookup"><span data-stu-id="f1bd3-176">Copy</span></span>

<span data-ttu-id="f1bd3-177">Копировать выбранный регион в буфер обмена системы.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-177">Copy selected region to the system clipboard.</span></span> <span data-ttu-id="f1bd3-178">Если регион не выбран, скопируйте всю строку.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-178">If no region is selected, copy the whole line.</span></span>

- <span data-ttu-id="f1bd3-179">Процессор `<Ctrl+C>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-179">Cmd: `<Ctrl+C>`</span></span>

### <a name="copyorcancelline"></a><span data-ttu-id="f1bd3-180">копйорканцеллине</span><span class="sxs-lookup"><span data-stu-id="f1bd3-180">CopyOrCancelLine</span></span>

<span data-ttu-id="f1bd3-181">Если выбран текст, скопируйте в буфер обмена, в противном случае отмените строку.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-181">If text is selected, copy to the clipboard, otherwise cancel the line.</span></span>

- <span data-ttu-id="f1bd3-182">Процессор `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-182">Cmd: `<Ctrl+c>`</span></span>
- <span data-ttu-id="f1bd3-183">Emacs: `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-183">Emacs: `<Ctrl+c>`</span></span>

### <a name="cut"></a><span data-ttu-id="f1bd3-184">Вырезать</span><span class="sxs-lookup"><span data-stu-id="f1bd3-184">Cut</span></span>

<span data-ttu-id="f1bd3-185">Удалить выбранный регион, поместив удаленный текст в системный буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-185">Delete selected region placing deleted text in the system clipboard.</span></span>

- <span data-ttu-id="f1bd3-186">Процессор `<Ctrl+x>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-186">Cmd: `<Ctrl+x>`</span></span>

### <a name="deletechar"></a><span data-ttu-id="f1bd3-187">делетечар</span><span class="sxs-lookup"><span data-stu-id="f1bd3-187">DeleteChar</span></span>

<span data-ttu-id="f1bd3-188">Удалите символ под курсором.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-188">Delete the character under the cursor.</span></span>

- <span data-ttu-id="f1bd3-189">Процессор `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-189">Cmd: `<Delete>`</span></span>
- <span data-ttu-id="f1bd3-190">Emacs: `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-190">Emacs: `<Delete>`</span></span>
- <span data-ttu-id="f1bd3-191">Режим вставки в VI: `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-191">Vi insert mode: `<Delete>`</span></span>
- <span data-ttu-id="f1bd3-192">Режим команд VI: `<Delete>` , `<x>` , `<d,l>` , `<d,Space>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-192">Vi command mode: `<Delete>`, `<x>`, `<d,l>`, `<d,Space>`</span></span>

### <a name="deletecharorexit"></a><span data-ttu-id="f1bd3-193">делетечарорексит</span><span class="sxs-lookup"><span data-stu-id="f1bd3-193">DeleteCharOrExit</span></span>

<span data-ttu-id="f1bd3-194">Удалите символ под курсором или, если строка пуста, завершите процесс.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-194">Delete the character under the cursor, or if the line is empty, exit the process.</span></span>

- <span data-ttu-id="f1bd3-195">Emacs: `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-195">Emacs: `<Ctrl+d>`</span></span>

### <a name="deleteendofword"></a><span data-ttu-id="f1bd3-196">делетиндофворд</span><span class="sxs-lookup"><span data-stu-id="f1bd3-196">DeleteEndOfWord</span></span>

<span data-ttu-id="f1bd3-197">Удалить до конца слова.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-197">Delete to the end of the word.</span></span>

- <span data-ttu-id="f1bd3-198">Режим команд VI: `<d,e>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-198">Vi command mode: `<d,e>`</span></span>

### <a name="deleteline"></a><span data-ttu-id="f1bd3-199">Сбой deleteline</span><span class="sxs-lookup"><span data-stu-id="f1bd3-199">DeleteLine</span></span>

<span data-ttu-id="f1bd3-200">Удаляет текущую строку, включая отмену.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-200">Deletes the current line, enabling undo.</span></span>

- <span data-ttu-id="f1bd3-201">Режим команд VI: `<d,d>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-201">Vi command mode: `<d,d>`</span></span>

### <a name="deletelinetofirstchar"></a><span data-ttu-id="f1bd3-202">делетелинетофирстчар</span><span class="sxs-lookup"><span data-stu-id="f1bd3-202">DeleteLineToFirstChar</span></span>

<span data-ttu-id="f1bd3-203">Удаляет текст из курсора на первый символ строки, отличный от пробела.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-203">Deletes text from the cursor to the first non-blank character of the line.</span></span>

- <span data-ttu-id="f1bd3-204">Режим команд VI: `<d,^>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-204">Vi command mode: `<d,^>`</span></span>

### <a name="deletetoend"></a><span data-ttu-id="f1bd3-205">делететоенд</span><span class="sxs-lookup"><span data-stu-id="f1bd3-205">DeleteToEnd</span></span>

<span data-ttu-id="f1bd3-206">Удалить до конца строки.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-206">Delete to the end of the line.</span></span>

- <span data-ttu-id="f1bd3-207">Режим команд VI: `<D>` , `<d,$>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-207">Vi command mode: `<D>`, `<d,$>`</span></span>

### <a name="deleteword"></a><span data-ttu-id="f1bd3-208">DeleteWord</span><span class="sxs-lookup"><span data-stu-id="f1bd3-208">DeleteWord</span></span>

<span data-ttu-id="f1bd3-209">Удалить следующее слово.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-209">Delete the next word.</span></span>

- <span data-ttu-id="f1bd3-210">Режим команд VI: `<d,w>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-210">Vi command mode: `<d,w>`</span></span>

### <a name="forwarddeleteline"></a><span data-ttu-id="f1bd3-211">форвардделетелине</span><span class="sxs-lookup"><span data-stu-id="f1bd3-211">ForwardDeleteLine</span></span>

<span data-ttu-id="f1bd3-212">Как и Форвардкилллине — удаляет текст с точки до конца строки, но не помещает удаленный текст в инструкцию KILL-Ring.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-212">Like ForwardKillLine - deletes text from the point to the end of the line, but does not put the deleted text in the kill-ring.</span></span>

- <span data-ttu-id="f1bd3-213">Процессор `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-213">Cmd: `<Ctrl+End>`</span></span>
- <span data-ttu-id="f1bd3-214">Режим вставки в VI: `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-214">Vi insert mode: `<Ctrl+End>`</span></span>
- <span data-ttu-id="f1bd3-215">Режим команд VI: `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-215">Vi command mode: `<Ctrl+End>`</span></span>

### <a name="insertlineabove"></a><span data-ttu-id="f1bd3-216">инсертлинеабове</span><span class="sxs-lookup"><span data-stu-id="f1bd3-216">InsertLineAbove</span></span>

<span data-ttu-id="f1bd3-217">Новая пустая строка создается над текущей строкой, независимо от того, где находится курсор на текущей строке.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-217">A new empty line is created above the current line regardless of where the cursor is on the current line.</span></span> <span data-ttu-id="f1bd3-218">Курсор переместится в начало новой строки.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-218">The cursor moves to the beginning of the new line.</span></span>

- <span data-ttu-id="f1bd3-219">Процессор `<Ctrl+Enter>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-219">Cmd: `<Ctrl+Enter>`</span></span>

### <a name="insertlinebelow"></a><span data-ttu-id="f1bd3-220">инсертлинебелов</span><span class="sxs-lookup"><span data-stu-id="f1bd3-220">InsertLineBelow</span></span>

<span data-ttu-id="f1bd3-221">Новая пустая строка создается под текущей строкой независимо от того, где находится курсор на текущей строке.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-221">A new empty line is created below the current line regardless of where the cursor is on the current line.</span></span> <span data-ttu-id="f1bd3-222">Курсор переместится в начало новой строки.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-222">The cursor moves to the beginning of the new line.</span></span>

- <span data-ttu-id="f1bd3-223">Процессор `<Shift+Ctrl+Enter>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-223">Cmd: `<Shift+Ctrl+Enter>`</span></span>

### <a name="invertcase"></a><span data-ttu-id="f1bd3-224">инверткасе</span><span class="sxs-lookup"><span data-stu-id="f1bd3-224">InvertCase</span></span>

<span data-ttu-id="f1bd3-225">Инвертировать регистр текущего символа и перейти к следующему.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-225">Invert the case of the current character and move to the next one.</span></span>

- <span data-ttu-id="f1bd3-226">Режим команд VI: `<~>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-226">Vi command mode: `<~>`</span></span>

### <a name="killline"></a><span data-ttu-id="f1bd3-227">килллине</span><span class="sxs-lookup"><span data-stu-id="f1bd3-227">KillLine</span></span>

<span data-ttu-id="f1bd3-228">Очистить входные данные от курсора до конца входных данных.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-228">Clear the input from the cursor to the end of the input.</span></span> <span data-ttu-id="f1bd3-229">Очистка текста помещается в буфер Kill.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-229">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="f1bd3-230">Emacs: `<Ctrl+k>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-230">Emacs: `<Ctrl+k>`</span></span>

### <a name="killregion"></a><span data-ttu-id="f1bd3-231">киллрегион</span><span class="sxs-lookup"><span data-stu-id="f1bd3-231">KillRegion</span></span>

<span data-ttu-id="f1bd3-232">Удалить текст между курсором и меткой.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-232">Kill the text between the cursor and the mark.</span></span>

- <span data-ttu-id="f1bd3-233">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-233">Function is unbound.</span></span>

### <a name="killword"></a><span data-ttu-id="f1bd3-234">киллворд</span><span class="sxs-lookup"><span data-stu-id="f1bd3-234">KillWord</span></span>

<span data-ttu-id="f1bd3-235">Очистить ввод от курсора до конца текущего слова.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-235">Clear the input from the cursor to the end of the current word.</span></span> <span data-ttu-id="f1bd3-236">Если курсор находится между словами, входные данные очищаются от курсора до конца следующего слова.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-236">If the cursor is between words, the input is cleared from the cursor to the end of the next word.</span></span> <span data-ttu-id="f1bd3-237">Очистка текста помещается в буфер Kill.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-237">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="f1bd3-238">Процессор `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-238">Cmd: `<Ctrl+Delete>`</span></span>
- <span data-ttu-id="f1bd3-239">Emacs: `<Alt+d>` , `<Escape,d>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-239">Emacs: `<Alt+d>`, `<Escape,d>`</span></span>
- <span data-ttu-id="f1bd3-240">Режим вставки в VI: `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-240">Vi insert mode: `<Ctrl+Delete>`</span></span>
- <span data-ttu-id="f1bd3-241">Режим команд VI: `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-241">Vi command mode: `<Ctrl+Delete>`</span></span>

### <a name="paste"></a><span data-ttu-id="f1bd3-242">Вставить</span><span class="sxs-lookup"><span data-stu-id="f1bd3-242">Paste</span></span>

<span data-ttu-id="f1bd3-243">Вставка текста из буфера обмена системы.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-243">Paste text from the system clipboard.</span></span>

- <span data-ttu-id="f1bd3-244">Cmd: `<Ctrl+v>` , `<Shift+Insert>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-244">Cmd: `<Ctrl+v>`, `<Shift+Insert>`</span></span>
- <span data-ttu-id="f1bd3-245">Режим вставки в VI: `<Ctrl+v>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-245">Vi insert mode: `<Ctrl+v>`</span></span>
- <span data-ttu-id="f1bd3-246">Режим команд VI: `<Ctrl+v>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-246">Vi command mode: `<Ctrl+v>`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f1bd3-247">При использовании функции **вставки** все содержимое буфера буфера обмена вставляется во входной буфер PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-247">When using the **Paste** function, the entire contents of the clipboard buffer is pasted into the input buffer of PSReadLine.</span></span> <span data-ttu-id="f1bd3-248">Затем входной буфер передается средству синтаксического анализа PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-248">The input buffer is then passed to the PowerShell parser.</span></span> <span data-ttu-id="f1bd3-249">Вход, вставленный с помощью консольного приложения, щелкните **правой кнопкой мыши** метод вставки, скопированный во входной буфер по одному символу за раз.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-249">Input pasted using the console application's **right-click** paste method is copied to the input buffer one character at a time.</span></span> <span data-ttu-id="f1bd3-250">Входной буфер передается средству синтаксического анализа при копировании символа новой строки.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-250">The input buffer is passed to the parser when a newline character is copied.</span></span> <span data-ttu-id="f1bd3-251">Поэтому входные данные анализируются по одной строке за раз.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-251">Therefore, the input is parsed one line at a time.</span></span> <span data-ttu-id="f1bd3-252">Различие между методами вставки приводит к различному поведению при выполнении.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-252">The difference between paste methods results in different execution behavior.</span></span>

### <a name="pasteafter"></a><span data-ttu-id="f1bd3-253">пастеафтер</span><span class="sxs-lookup"><span data-stu-id="f1bd3-253">PasteAfter</span></span>

<span data-ttu-id="f1bd3-254">Вставьте буфер обмена после курсора, переместив курсор в конец вставленного текста.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-254">Paste the clipboard after the cursor, moving the cursor to the end of the pasted text.</span></span>

- <span data-ttu-id="f1bd3-255">Режим команд VI: `<p>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-255">Vi command mode: `<p>`</span></span>

### <a name="pastebefore"></a><span data-ttu-id="f1bd3-256">пастебефоре</span><span class="sxs-lookup"><span data-stu-id="f1bd3-256">PasteBefore</span></span>

<span data-ttu-id="f1bd3-257">Вставьте буфер обмена перед курсором, переместив курсор в конец вставленного текста.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-257">Paste the clipboard before the cursor, moving the cursor to the end of the pasted text.</span></span>

- <span data-ttu-id="f1bd3-258">Режим команд VI: `<P>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-258">Vi command mode: `<P>`</span></span>

### <a name="prependandaccept"></a><span data-ttu-id="f1bd3-259">препендандакцепт</span><span class="sxs-lookup"><span data-stu-id="f1bd3-259">PrependAndAccept</span></span>

<span data-ttu-id="f1bd3-260">Добавьте в начало "#" и примите строку.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-260">Prepend a '#' and accept the line.</span></span>

- <span data-ttu-id="f1bd3-261">Режим команд VI: `<#>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-261">Vi command mode: `<#>`</span></span>

### <a name="redo"></a><span data-ttu-id="f1bd3-262">Повторить</span><span class="sxs-lookup"><span data-stu-id="f1bd3-262">Redo</span></span>

<span data-ttu-id="f1bd3-263">Отмена отмены.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-263">Undo an undo.</span></span>

- <span data-ttu-id="f1bd3-264">Процессор `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-264">Cmd: `<Ctrl+y>`</span></span>
- <span data-ttu-id="f1bd3-265">Режим вставки в VI: `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-265">Vi insert mode: `<Ctrl+y>`</span></span>
- <span data-ttu-id="f1bd3-266">Режим команд VI: `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-266">Vi command mode: `<Ctrl+y>`</span></span>

### <a name="repeatlastcommand"></a><span data-ttu-id="f1bd3-267">репеатласткомманд</span><span class="sxs-lookup"><span data-stu-id="f1bd3-267">RepeatLastCommand</span></span>

<span data-ttu-id="f1bd3-268">Повторите Последнее изменение текста.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-268">Repeat the last text modification.</span></span>

- <span data-ttu-id="f1bd3-269">Режим команд VI: `<.>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-269">Vi command mode: `<.>`</span></span>

### <a name="revertline"></a><span data-ttu-id="f1bd3-270">ревертлине</span><span class="sxs-lookup"><span data-stu-id="f1bd3-270">RevertLine</span></span>

<span data-ttu-id="f1bd3-271">Меняет все входные данные на текущие входные данные.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-271">Reverts all of the input to the current input.</span></span>

- <span data-ttu-id="f1bd3-272">Процессор `<Escape>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-272">Cmd: `<Escape>`</span></span>
- <span data-ttu-id="f1bd3-273">Emacs: `<Alt+r>` , `<Escape,r>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-273">Emacs: `<Alt+r>`, `<Escape,r>`</span></span>

### <a name="shellbackwardkillword"></a><span data-ttu-id="f1bd3-274">шеллбакквардкиллворд</span><span class="sxs-lookup"><span data-stu-id="f1bd3-274">ShellBackwardKillWord</span></span>

<span data-ttu-id="f1bd3-275">Очистить ввод от начала текущего слова до курсора.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-275">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="f1bd3-276">Если курсор находится между словами, входные данные очищаются от начала предыдущего слова до курсора.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-276">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="f1bd3-277">Очистка текста помещается в буфер Kill.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-277">The cleared text is placed in the kill-ring.</span></span>

<span data-ttu-id="f1bd3-278">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-278">Function is unbound.</span></span>

### <a name="shellkillword"></a><span data-ttu-id="f1bd3-279">шеллкиллворд</span><span class="sxs-lookup"><span data-stu-id="f1bd3-279">ShellKillWord</span></span>

<span data-ttu-id="f1bd3-280">Очистить ввод от курсора до конца текущего слова.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-280">Clear the input from the cursor to the end of the current word.</span></span> <span data-ttu-id="f1bd3-281">Если курсор находится между словами, входные данные очищаются от курсора до конца следующего слова.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-281">If the cursor is between words, the input is cleared from the cursor to the end of the next word.</span></span> <span data-ttu-id="f1bd3-282">Очистка текста помещается в буфер Kill.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-282">The cleared text is placed in the kill-ring.</span></span>

<span data-ttu-id="f1bd3-283">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-283">Function is unbound.</span></span>

### <a name="swapcharacters"></a><span data-ttu-id="f1bd3-284">свапчарактерс</span><span class="sxs-lookup"><span data-stu-id="f1bd3-284">SwapCharacters</span></span>

<span data-ttu-id="f1bd3-285">Поменять местами текущий и тот же символ.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-285">Swap the current character and the one before it.</span></span>

- <span data-ttu-id="f1bd3-286">Emacs: `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-286">Emacs: `<Ctrl+t>`</span></span>
- <span data-ttu-id="f1bd3-287">Режим вставки в VI: `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-287">Vi insert mode: `<Ctrl+t>`</span></span>
- <span data-ttu-id="f1bd3-288">Режим команд VI: `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-288">Vi command mode: `<Ctrl+t>`</span></span>

### <a name="undo"></a><span data-ttu-id="f1bd3-289">Отменить</span><span class="sxs-lookup"><span data-stu-id="f1bd3-289">Undo</span></span>

<span data-ttu-id="f1bd3-290">Отмена предыдущего изменения.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-290">Undo a previous edit.</span></span>

- <span data-ttu-id="f1bd3-291">Процессор `<Ctrl+z>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-291">Cmd: `<Ctrl+z>`</span></span>
- <span data-ttu-id="f1bd3-292">Emacs: `<Ctrl+_>` , `<Ctrl+x,Ctrl+u>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-292">Emacs: `<Ctrl+_>`, `<Ctrl+x,Ctrl+u>`</span></span>
- <span data-ttu-id="f1bd3-293">Режим вставки в VI: `<Ctrl+z>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-293">Vi insert mode: `<Ctrl+z>`</span></span>
- <span data-ttu-id="f1bd3-294">Режим команд VI: `<Ctrl+z>` , `<u>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-294">Vi command mode: `<Ctrl+z>`, `<u>`</span></span>

### <a name="undoall"></a><span data-ttu-id="f1bd3-295">ундоалл</span><span class="sxs-lookup"><span data-stu-id="f1bd3-295">UndoAll</span></span>

<span data-ttu-id="f1bd3-296">Отмена всех предыдущих изменений для строки.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-296">Undo all previous edits for line.</span></span>

- <span data-ttu-id="f1bd3-297">Режим команд VI: `<U>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-297">Vi command mode: `<U>`</span></span>

### <a name="unixwordrubout"></a><span data-ttu-id="f1bd3-298">униксвордрубаут</span><span class="sxs-lookup"><span data-stu-id="f1bd3-298">UnixWordRubout</span></span>

<span data-ttu-id="f1bd3-299">Очистить ввод от начала текущего слова до курсора.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-299">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="f1bd3-300">Если курсор находится между словами, входные данные очищаются от начала предыдущего слова до курсора.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-300">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="f1bd3-301">Очистка текста помещается в буфер Kill.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-301">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="f1bd3-302">Emacs: `<Ctrl+w>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-302">Emacs: `<Ctrl+w>`</span></span>

### <a name="validateandacceptline"></a><span data-ttu-id="f1bd3-303">валидатеандакцептлине</span><span class="sxs-lookup"><span data-stu-id="f1bd3-303">ValidateAndAcceptLine</span></span>

<span data-ttu-id="f1bd3-304">Попытка выполнить текущий вход.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-304">Attempt to execute the current input.</span></span> <span data-ttu-id="f1bd3-305">Если текущий ввод неполон (например, отсутствует закрывающая круглая скобка, квадратная скобка или кавычка, запрос продолжения отображается на следующей строке, а PSReadLine ожидает ввода ключей для изменения текущих входных данных.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-305">If the current input is incomplete (for example there is a missing closing parenthesis, bracket, or quote, then the continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span>

- <span data-ttu-id="f1bd3-306">Emacs: `<Ctrl+m>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-306">Emacs: `<Ctrl+m>`</span></span>

### <a name="viacceptline"></a><span data-ttu-id="f1bd3-307">виакцептлине</span><span class="sxs-lookup"><span data-stu-id="f1bd3-307">ViAcceptLine</span></span>

<span data-ttu-id="f1bd3-308">Примите строку и переключитесь в режим вставки.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-308">Accept the line and switch to Insert mode.</span></span>

- <span data-ttu-id="f1bd3-309">Режим команд VI: `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-309">Vi command mode: `<Enter>`</span></span>

### <a name="viacceptlineorexit"></a><span data-ttu-id="f1bd3-310">виакцептлинеорексит</span><span class="sxs-lookup"><span data-stu-id="f1bd3-310">ViAcceptLineOrExit</span></span>

<span data-ttu-id="f1bd3-311">Как и Делетечарорексит в режиме Emacs, но принимает строку вместо удаления символа.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-311">Like DeleteCharOrExit in Emacs mode, but accepts the line instead of deleting a character.</span></span>

- <span data-ttu-id="f1bd3-312">Режим вставки в VI: `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-312">Vi insert mode: `<Ctrl+d>`</span></span>
- <span data-ttu-id="f1bd3-313">Режим команд VI: `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-313">Vi command mode: `<Ctrl+d>`</span></span>

### <a name="viappendline"></a><span data-ttu-id="f1bd3-314">виаппендлине</span><span class="sxs-lookup"><span data-stu-id="f1bd3-314">ViAppendLine</span></span>

<span data-ttu-id="f1bd3-315">Новая строка вставляется под текущей строкой.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-315">A new line is inserted below the current line.</span></span>

- <span data-ttu-id="f1bd3-316">Режим команд VI: `<o>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-316">Vi command mode: `<o>`</span></span>

### <a name="vibackwarddeleteglob"></a><span data-ttu-id="f1bd3-317">вибакквардделетеглоб</span><span class="sxs-lookup"><span data-stu-id="f1bd3-317">ViBackwardDeleteGlob</span></span>

<span data-ttu-id="f1bd3-318">Удаляет предыдущее слово, используя только пробелы в качестве разделителя слов.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-318">Deletes the previous word, using only white space as the word delimiter.</span></span>

- <span data-ttu-id="f1bd3-319">Режим команд VI: `<d,B>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-319">Vi command mode: `<d,B>`</span></span>

### <a name="vibackwardglob"></a><span data-ttu-id="f1bd3-320">вибакквардглоб</span><span class="sxs-lookup"><span data-stu-id="f1bd3-320">ViBackwardGlob</span></span>

<span data-ttu-id="f1bd3-321">Перемещает курсор назад к началу предыдущего слова, используя только пробелы в качестве разделителей.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-321">Moves the cursor back to the beginning of the previous word, using only white space as delimiters.</span></span>

- <span data-ttu-id="f1bd3-322">Режим команд VI: `<B>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-322">Vi command mode: `<B>`</span></span>

### <a name="videletebrace"></a><span data-ttu-id="f1bd3-323">виделетебраце</span><span class="sxs-lookup"><span data-stu-id="f1bd3-323">ViDeleteBrace</span></span>

<span data-ttu-id="f1bd3-324">Найдите парную фигурную скобку, круглую скобку или квадратную скобку и удалите все содержимое внутри, включая фигурную скобку.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-324">Find the matching brace, parenthesis, or square bracket and delete all contents within, including the brace.</span></span>

- <span data-ttu-id="f1bd3-325">Режим команд VI: `<d,%>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-325">Vi command mode: `<d,%>`</span></span>

### <a name="videleteendofglob"></a><span data-ttu-id="f1bd3-326">виделетиндофглоб</span><span class="sxs-lookup"><span data-stu-id="f1bd3-326">ViDeleteEndOfGlob</span></span>

<span data-ttu-id="f1bd3-327">Удалить до конца слова.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-327">Delete to the end of the word.</span></span>

- <span data-ttu-id="f1bd3-328">Режим команд VI: `<d,E>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-328">Vi command mode: `<d,E>`</span></span>

### <a name="videleteglob"></a><span data-ttu-id="f1bd3-329">виделетеглоб</span><span class="sxs-lookup"><span data-stu-id="f1bd3-329">ViDeleteGlob</span></span>

<span data-ttu-id="f1bd3-330">Удалите следующий стандартная маска (слово, разделенное пробелами).</span><span class="sxs-lookup"><span data-stu-id="f1bd3-330">Delete the next glob (white space delimited word).</span></span>

- <span data-ttu-id="f1bd3-331">Режим команд VI: `<d,W>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-331">Vi command mode: `<d,W>`</span></span>

### <a name="videletetobeforechar"></a><span data-ttu-id="f1bd3-332">виделететобефоречар</span><span class="sxs-lookup"><span data-stu-id="f1bd3-332">ViDeleteToBeforeChar</span></span>

<span data-ttu-id="f1bd3-333">Удаляет до заданного символа.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-333">Deletes until given character.</span></span>

- <span data-ttu-id="f1bd3-334">Режим команд VI: `<d,t>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-334">Vi command mode: `<d,t>`</span></span>

### <a name="videletetobeforecharbackward"></a><span data-ttu-id="f1bd3-335">виделететобефоречарбакквард</span><span class="sxs-lookup"><span data-stu-id="f1bd3-335">ViDeleteToBeforeCharBackward</span></span>

<span data-ttu-id="f1bd3-336">Удаляет до заданного символа.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-336">Deletes until given character.</span></span>

- <span data-ttu-id="f1bd3-337">Режим команд VI: `<d,T>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-337">Vi command mode: `<d,T>`</span></span>

### <a name="videletetochar"></a><span data-ttu-id="f1bd3-338">виделететочар</span><span class="sxs-lookup"><span data-stu-id="f1bd3-338">ViDeleteToChar</span></span>

<span data-ttu-id="f1bd3-339">Удаляет до заданного символа.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-339">Deletes until given character.</span></span>

- <span data-ttu-id="f1bd3-340">Режим команд VI: `<d,f>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-340">Vi command mode: `<d,f>`</span></span>

### <a name="videletetocharbackward"></a><span data-ttu-id="f1bd3-341">виделететочарбакквард</span><span class="sxs-lookup"><span data-stu-id="f1bd3-341">ViDeleteToCharBackward</span></span>

<span data-ttu-id="f1bd3-342">Удаляет обратную сторону до заданного символа.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-342">Deletes backwards until given character.</span></span>

- <span data-ttu-id="f1bd3-343">Режим команд VI: `<d,F>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-343">Vi command mode: `<d,F>`</span></span>

### <a name="viinsertatbegining"></a><span data-ttu-id="f1bd3-344">виинсертатбегининг</span><span class="sxs-lookup"><span data-stu-id="f1bd3-344">ViInsertAtBegining</span></span>

<span data-ttu-id="f1bd3-345">Переключитесь в режим вставки и поместите курсор в начало строки.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-345">Switch to Insert mode and position the cursor at the beginning of the line.</span></span>

- <span data-ttu-id="f1bd3-346">Режим команд VI: `<I>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-346">Vi command mode: `<I>`</span></span>

### <a name="viinsertatend"></a><span data-ttu-id="f1bd3-347">виинсертатенд</span><span class="sxs-lookup"><span data-stu-id="f1bd3-347">ViInsertAtEnd</span></span>

<span data-ttu-id="f1bd3-348">Переключитесь в режим вставки и поместите курсор в конец строки.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-348">Switch to Insert mode and position the cursor at the end of the line.</span></span>

- <span data-ttu-id="f1bd3-349">Режим команд VI: `<A>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-349">Vi command mode: `<A>`</span></span>

### <a name="viinsertline"></a><span data-ttu-id="f1bd3-350">виинсертлине</span><span class="sxs-lookup"><span data-stu-id="f1bd3-350">ViInsertLine</span></span>

<span data-ttu-id="f1bd3-351">Новая строка вставляется над текущей строкой.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-351">A new line is inserted above the current line.</span></span>

- <span data-ttu-id="f1bd3-352">Режим команд VI: `<O>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-352">Vi command mode: `<O>`</span></span>

### <a name="viinsertwithappend"></a><span data-ttu-id="f1bd3-353">виинсертвисаппенд</span><span class="sxs-lookup"><span data-stu-id="f1bd3-353">ViInsertWithAppend</span></span>

<span data-ttu-id="f1bd3-354">Добавление из текущей позицией строки.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-354">Append from the current line position.</span></span>

- <span data-ttu-id="f1bd3-355">Режим команд VI: `<a>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-355">Vi command mode: `<a>`</span></span>

### <a name="viinsertwithdelete"></a><span data-ttu-id="f1bd3-356">виинсертвисделете</span><span class="sxs-lookup"><span data-stu-id="f1bd3-356">ViInsertWithDelete</span></span>

<span data-ttu-id="f1bd3-357">Удалите текущий символ и переключитесь в режим вставки.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-357">Delete the current character and switch to Insert mode.</span></span>

- <span data-ttu-id="f1bd3-358">Режим команд VI: `<s>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-358">Vi command mode: `<s>`</span></span>

### <a name="vijoinlines"></a><span data-ttu-id="f1bd3-359">вижоинлинес</span><span class="sxs-lookup"><span data-stu-id="f1bd3-359">ViJoinLines</span></span>

<span data-ttu-id="f1bd3-360">Объединяет текущую строку и следующую строку.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-360">Joins the current line and the next line.</span></span>

- <span data-ttu-id="f1bd3-361">Режим команд VI: `<J>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-361">Vi command mode: `<J>`</span></span>

### <a name="vireplaceline"></a><span data-ttu-id="f1bd3-362">виреплацелине</span><span class="sxs-lookup"><span data-stu-id="f1bd3-362">ViReplaceLine</span></span>

<span data-ttu-id="f1bd3-363">Очистить всю командную строку.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-363">Erase the entire command line.</span></span>

- <span data-ttu-id="f1bd3-364">Режим команд VI: `<S>` , `<c,c>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-364">Vi command mode: `<S>`, `<c,c>`</span></span>

### <a name="vireplacetobeforechar"></a><span data-ttu-id="f1bd3-365">виреплацетобефоречар</span><span class="sxs-lookup"><span data-stu-id="f1bd3-365">ViReplaceToBeforeChar</span></span>

<span data-ttu-id="f1bd3-366">Заменяет заданный символ.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-366">Replaces until given character.</span></span>

- <span data-ttu-id="f1bd3-367">Режим команд VI: `<c,t>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-367">Vi command mode: `<c,t>`</span></span>

### <a name="vireplacetobeforecharbackward"></a><span data-ttu-id="f1bd3-368">виреплацетобефоречарбакквард</span><span class="sxs-lookup"><span data-stu-id="f1bd3-368">ViReplaceToBeforeCharBackward</span></span>

<span data-ttu-id="f1bd3-369">Заменяет заданный символ.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-369">Replaces until given character.</span></span>

- <span data-ttu-id="f1bd3-370">Режим команд VI: `<c,T>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-370">Vi command mode: `<c,T>`</span></span>

### <a name="vireplacetochar"></a><span data-ttu-id="f1bd3-371">виреплацеточар</span><span class="sxs-lookup"><span data-stu-id="f1bd3-371">ViReplaceToChar</span></span>

<span data-ttu-id="f1bd3-372">Удаляет до заданного символа.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-372">Deletes until given character.</span></span>

- <span data-ttu-id="f1bd3-373">Режим команд VI: `<c,f>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-373">Vi command mode: `<c,f>`</span></span>

### <a name="vireplacetocharbackward"></a><span data-ttu-id="f1bd3-374">виреплацеточарбакквард</span><span class="sxs-lookup"><span data-stu-id="f1bd3-374">ViReplaceToCharBackward</span></span>

<span data-ttu-id="f1bd3-375">Заменяет заданный символ.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-375">Replaces until given character.</span></span>

- <span data-ttu-id="f1bd3-376">Режим команд VI: `<c,F>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-376">Vi command mode: `<c,F>`</span></span>

### <a name="viyankbeginningofline"></a><span data-ttu-id="f1bd3-377">вийанкбегиннингофлине</span><span class="sxs-lookup"><span data-stu-id="f1bd3-377">ViYankBeginningOfLine</span></span>

<span data-ttu-id="f1bd3-378">Янк от начала буфера до курсора.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-378">Yank from the beginning of the buffer to the cursor.</span></span>

- <span data-ttu-id="f1bd3-379">Режим команд VI: `<y,0>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-379">Vi command mode: `<y,0>`</span></span>

### <a name="viyankendofglob"></a><span data-ttu-id="f1bd3-380">вийанкендофглоб</span><span class="sxs-lookup"><span data-stu-id="f1bd3-380">ViYankEndOfGlob</span></span>

<span data-ttu-id="f1bd3-381">Янк от курсора до конца слова.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-381">Yank from the cursor to the end of the WORD(s).</span></span>

- <span data-ttu-id="f1bd3-382">Режим команд VI: `<y,E>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-382">Vi command mode: `<y,E>`</span></span>

### <a name="viyankendofword"></a><span data-ttu-id="f1bd3-383">вийанкендофворд</span><span class="sxs-lookup"><span data-stu-id="f1bd3-383">ViYankEndOfWord</span></span>

<span data-ttu-id="f1bd3-384">Янк от курсора до конца слова.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-384">Yank from the cursor to the end of the word(s).</span></span>

- <span data-ttu-id="f1bd3-385">Режим команд VI: `<y,e>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-385">Vi command mode: `<y,e>`</span></span>

### <a name="viyankleft"></a><span data-ttu-id="f1bd3-386">вийанклефт</span><span class="sxs-lookup"><span data-stu-id="f1bd3-386">ViYankLeft</span></span>

<span data-ttu-id="f1bd3-387">Янк символы слева от курсора.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-387">Yank character(s) to the left of the cursor.</span></span>

- <span data-ttu-id="f1bd3-388">Режим команд VI: `<y,h>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-388">Vi command mode: `<y,h>`</span></span>

### <a name="viyankline"></a><span data-ttu-id="f1bd3-389">вийанклине</span><span class="sxs-lookup"><span data-stu-id="f1bd3-389">ViYankLine</span></span>

<span data-ttu-id="f1bd3-390">Янк весь буфер.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-390">Yank the entire buffer.</span></span>

- <span data-ttu-id="f1bd3-391">Режим команд VI: `<y,y>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-391">Vi command mode: `<y,y>`</span></span>

### <a name="viyanknextglob"></a><span data-ttu-id="f1bd3-392">вийанкнекстглоб</span><span class="sxs-lookup"><span data-stu-id="f1bd3-392">ViYankNextGlob</span></span>

<span data-ttu-id="f1bd3-393">Янк от курсора до начала следующего слова.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-393">Yank from cursor to the start of the next WORD(s).</span></span>

- <span data-ttu-id="f1bd3-394">Режим команд VI: `<y,W>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-394">Vi command mode: `<y,W>`</span></span>

### <a name="viyanknextword"></a><span data-ttu-id="f1bd3-395">вийанкнекстворд</span><span class="sxs-lookup"><span data-stu-id="f1bd3-395">ViYankNextWord</span></span>

<span data-ttu-id="f1bd3-396">Янк слова после курсора.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-396">Yank the word(s) after the cursor.</span></span>

- <span data-ttu-id="f1bd3-397">Режим команд VI: `<y,w>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-397">Vi command mode: `<y,w>`</span></span>

### <a name="viyankpercent"></a><span data-ttu-id="f1bd3-398">вийанкперцент</span><span class="sxs-lookup"><span data-stu-id="f1bd3-398">ViYankPercent</span></span>

<span data-ttu-id="f1bd3-399">Янк в парную фигурную скобку.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-399">Yank to/from matching brace.</span></span>

- <span data-ttu-id="f1bd3-400">Режим команд VI: `<y,%>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-400">Vi command mode: `<y,%>`</span></span>

### <a name="viyankpreviousglob"></a><span data-ttu-id="f1bd3-401">вийанкпревиаусглоб</span><span class="sxs-lookup"><span data-stu-id="f1bd3-401">ViYankPreviousGlob</span></span>

<span data-ttu-id="f1bd3-402">Янк от начала слов до курсора.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-402">Yank from beginning of the WORD(s) to cursor.</span></span>

- <span data-ttu-id="f1bd3-403">Режим команд VI: `<y,B>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-403">Vi command mode: `<y,B>`</span></span>

### <a name="viyankpreviousword"></a><span data-ttu-id="f1bd3-404">вийанкпревиаусворд</span><span class="sxs-lookup"><span data-stu-id="f1bd3-404">ViYankPreviousWord</span></span>

<span data-ttu-id="f1bd3-405">Янк слова перед курсором.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-405">Yank the word(s) before the cursor.</span></span>

- <span data-ttu-id="f1bd3-406">Режим команд VI: `<y,b>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-406">Vi command mode: `<y,b>`</span></span>

### <a name="viyankright"></a><span data-ttu-id="f1bd3-407">вийанкригхт</span><span class="sxs-lookup"><span data-stu-id="f1bd3-407">ViYankRight</span></span>

<span data-ttu-id="f1bd3-408">Янк символы в положении и справа от курсора.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-408">Yank character(s) under and to the right of the cursor.</span></span>

- <span data-ttu-id="f1bd3-409">Режим команд VI: `<y,l>` , `<y,Space>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-409">Vi command mode: `<y,l>`, `<y,Space>`</span></span>

### <a name="viyanktoendofline"></a><span data-ttu-id="f1bd3-410">вийанктоендофлине</span><span class="sxs-lookup"><span data-stu-id="f1bd3-410">ViYankToEndOfLine</span></span>

<span data-ttu-id="f1bd3-411">Янк от курсора до конца буфера.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-411">Yank from the cursor to the end of the buffer.</span></span>

- <span data-ttu-id="f1bd3-412">Режим команд VI: `<y,$>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-412">Vi command mode: `<y,$>`</span></span>

### <a name="viyanktofirstchar"></a><span data-ttu-id="f1bd3-413">вийанктофирстчар</span><span class="sxs-lookup"><span data-stu-id="f1bd3-413">ViYankToFirstChar</span></span>

<span data-ttu-id="f1bd3-414">Янк от первого символа, отличного от пробела, к курсору.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-414">Yank from the first non-whitespace character to the cursor.</span></span>

- <span data-ttu-id="f1bd3-415">Режим команд VI: `<y,^>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-415">Vi command mode: `<y,^>`</span></span>

### <a name="yank"></a><span data-ttu-id="f1bd3-416">янк</span><span class="sxs-lookup"><span data-stu-id="f1bd3-416">Yank</span></span>

<span data-ttu-id="f1bd3-417">Добавление последнего недавнего текста во входные данные.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-417">Add the most recently killed text to the input.</span></span>

- <span data-ttu-id="f1bd3-418">Emacs: `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-418">Emacs: `<Ctrl+y>`</span></span>

### <a name="yanklastarg"></a><span data-ttu-id="f1bd3-419">янкластарг</span><span class="sxs-lookup"><span data-stu-id="f1bd3-419">YankLastArg</span></span>

<span data-ttu-id="f1bd3-420">Янк последний аргумент из предыдущей строки журнала.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-420">Yank the last argument from the previous history line.</span></span> <span data-ttu-id="f1bd3-421">С аргументом при первом вызове он ведет себя так же, как Янкнсарг.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-421">With an argument, the first time it is invoked, behaves just like YankNthArg.</span></span> <span data-ttu-id="f1bd3-422">Если вызывается несколько раз, вместо этого выполняется итерация по журналу, а аргумент устанавливает направление (отрицательно меняет направление на противоположное).</span><span class="sxs-lookup"><span data-stu-id="f1bd3-422">If invoked multiple times, instead it iterates through history and arg sets the direction (negative reverses the direction.)</span></span>

- <span data-ttu-id="f1bd3-423">Процессор `<Alt+.>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-423">Cmd: `<Alt+.>`</span></span>
- <span data-ttu-id="f1bd3-424">Emacs: `<Alt+.>` , `<Alt+_>` , `<Escape,.>` , `<Escape,_>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-424">Emacs: `<Alt+.>`, `<Alt+_>`, `<Escape,.>`, `<Escape,_>`</span></span>

### <a name="yankntharg"></a><span data-ttu-id="f1bd3-425">янкнсарг</span><span class="sxs-lookup"><span data-stu-id="f1bd3-425">YankNthArg</span></span>

<span data-ttu-id="f1bd3-426">Янк первый аргумент (после команды) из предыдущей строки журнала.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-426">Yank the first argument (after the command) from the previous history line.</span></span>
<span data-ttu-id="f1bd3-427">При использовании аргумента Янк аргумент n (начиная с 0), если аргумент является отрицательным, начните с последнего аргумента.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-427">With an argument, yank the nth argument (starting from 0), if the argument is negative, start from the last argument.</span></span>

- <span data-ttu-id="f1bd3-428">Emacs: `<Ctrl+Alt+y>` , `<Escape,Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-428">Emacs: `<Ctrl+Alt+y>`, `<Escape,Ctrl+y>`</span></span>

### <a name="yankpop"></a><span data-ttu-id="f1bd3-429">янкпоп</span><span class="sxs-lookup"><span data-stu-id="f1bd3-429">YankPop</span></span>

<span data-ttu-id="f1bd3-430">Если предыдущая операция была Янк или Янкпоп, замените ранее янкед текст следующим уничтоженным текстом из Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-430">If the previous operation was Yank or YankPop, replace the previously yanked text with the next killed text from the kill-ring.</span></span>

- <span data-ttu-id="f1bd3-431">Emacs: `<Alt+y>` , `<Escape,y>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-431">Emacs: `<Alt+y>`, `<Escape,y>`</span></span>

## <a name="cursor-movement-functions"></a><span data-ttu-id="f1bd3-432">Функции перемещения курсора</span><span class="sxs-lookup"><span data-stu-id="f1bd3-432">Cursor movement functions</span></span>

### <a name="backwardchar"></a><span data-ttu-id="f1bd3-433">бакквардчар</span><span class="sxs-lookup"><span data-stu-id="f1bd3-433">BackwardChar</span></span>

<span data-ttu-id="f1bd3-434">Переместить курсор на один символ влево.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-434">Move the cursor one character to the left.</span></span> <span data-ttu-id="f1bd3-435">Это может переместить курсор к предыдущей строке многострочного ввода.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-435">This may move the cursor to the previous line of multi-line input.</span></span>

- <span data-ttu-id="f1bd3-436">Процессор `<LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-436">Cmd: `<LeftArrow>`</span></span>
- <span data-ttu-id="f1bd3-437">Emacs: `<LeftArrow>` , `<Ctrl+b>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-437">Emacs: `<LeftArrow>`, `<Ctrl+b>`</span></span>
- <span data-ttu-id="f1bd3-438">Режим вставки в VI: `<LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-438">Vi insert mode: `<LeftArrow>`</span></span>
- <span data-ttu-id="f1bd3-439">Режим команд VI: `<LeftArrow>` , `<Backspace>` , `<h>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-439">Vi command mode: `<LeftArrow>`, `<Backspace>`, `<h>`</span></span>

### <a name="backwardword"></a><span data-ttu-id="f1bd3-440">бакквардворд</span><span class="sxs-lookup"><span data-stu-id="f1bd3-440">BackwardWord</span></span>

<span data-ttu-id="f1bd3-441">Перемещение курсора назад к началу текущего слова или между словами, с начала предыдущего слова.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-441">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="f1bd3-442">Границы слов определяются с помощью настраиваемого набора символов.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-442">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="f1bd3-443">Процессор `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-443">Cmd: `<Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="f1bd3-444">Emacs: `<Alt+b>` , `<Escape,b>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-444">Emacs: `<Alt+b>`, `<Escape,b>`</span></span>
- <span data-ttu-id="f1bd3-445">Режим вставки в VI: `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-445">Vi insert mode: `<Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="f1bd3-446">Режим команд VI: `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-446">Vi command mode: `<Ctrl+LeftArrow>`</span></span>

### <a name="beginningofline"></a><span data-ttu-id="f1bd3-447">бегиннингофлине</span><span class="sxs-lookup"><span data-stu-id="f1bd3-447">BeginningOfLine</span></span>

<span data-ttu-id="f1bd3-448">Если входные данные имеют несколько строк, переместитесь в начало текущей строки или, если они уже находятся в начале строки, перейдите к началу входного элемента.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-448">If the input has multiple lines, move to the start of the current line, or if already at the start of the line, move to the start of the input.</span></span> <span data-ttu-id="f1bd3-449">Если входные данные имеют одну строку, переходите к началу входных данных.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-449">If the input has a single line, move to the start of the input.</span></span>

- <span data-ttu-id="f1bd3-450">Процессор `<Home>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-450">Cmd: `<Home>`</span></span>
- <span data-ttu-id="f1bd3-451">Emacs: `<Home>` , `<Ctrl+a>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-451">Emacs: `<Home>`, `<Ctrl+a>`</span></span>
- <span data-ttu-id="f1bd3-452">Режим вставки в VI: `<Home>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-452">Vi insert mode: `<Home>`</span></span>
- <span data-ttu-id="f1bd3-453">Режим команд VI: `<Home>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-453">Vi command mode: `<Home>`</span></span>

### <a name="endofline"></a><span data-ttu-id="f1bd3-454">ендофлине</span><span class="sxs-lookup"><span data-stu-id="f1bd3-454">EndOfLine</span></span>

<span data-ttu-id="f1bd3-455">Если входные данные имеют несколько строк, переместитесь в конец текущей строки или, если они уже находятся в конце строки, перейдите к концу входных данных.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-455">If the input has multiple lines, move to the end of the current line, or if already at the end of the line, move to the end of the input.</span></span> <span data-ttu-id="f1bd3-456">Если входные данные имеют одну строку, переходите к концу входных данных.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-456">If the input has a single line, move to the end of the input.</span></span>

- <span data-ttu-id="f1bd3-457">Процессор `<End>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-457">Cmd: `<End>`</span></span>
- <span data-ttu-id="f1bd3-458">Emacs: `<End>` , `<Ctrl+e>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-458">Emacs: `<End>`, `<Ctrl+e>`</span></span>
- <span data-ttu-id="f1bd3-459">Режим вставки в VI: `<End>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-459">Vi insert mode: `<End>`</span></span>

### <a name="forwardchar"></a><span data-ttu-id="f1bd3-460">форвардчар</span><span class="sxs-lookup"><span data-stu-id="f1bd3-460">ForwardChar</span></span>

<span data-ttu-id="f1bd3-461">Переместить курсор на один символ вправо.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-461">Move the cursor one character to the right.</span></span> <span data-ttu-id="f1bd3-462">Это может переместить курсор на следующую строку многострочного ввода.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-462">This may move the cursor to the next line of multi-line input.</span></span>

- <span data-ttu-id="f1bd3-463">Процессор `<RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-463">Cmd: `<RightArrow>`</span></span>
- <span data-ttu-id="f1bd3-464">Emacs: `<RightArrow>` , `<Ctrl+f>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-464">Emacs: `<RightArrow>`, `<Ctrl+f>`</span></span>
- <span data-ttu-id="f1bd3-465">Режим вставки в VI: `<RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-465">Vi insert mode: `<RightArrow>`</span></span>
- <span data-ttu-id="f1bd3-466">Режим команд VI: `<RightArrow>` , `<Space>` , `<l>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-466">Vi command mode: `<RightArrow>`, `<Space>`, `<l>`</span></span>

### <a name="forwardword"></a><span data-ttu-id="f1bd3-467">форвардворд</span><span class="sxs-lookup"><span data-stu-id="f1bd3-467">ForwardWord</span></span>

<span data-ttu-id="f1bd3-468">Переместить курсор вперед к концу текущего слова или между словами, до конца следующего слова.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-468">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="f1bd3-469">Границы слов определяются с помощью настраиваемого набора символов.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-469">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="f1bd3-470">Emacs: `<Alt+f>` , `<Escape,f>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-470">Emacs: `<Alt+f>`, `<Escape,f>`</span></span>

### <a name="gotobrace"></a><span data-ttu-id="f1bd3-471">GotoBrace</span><span class="sxs-lookup"><span data-stu-id="f1bd3-471">GotoBrace</span></span>

<span data-ttu-id="f1bd3-472">Перейдите к парной фигурной скобке, круглой скобке или квадратной скобке.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-472">Go to the matching brace, parenthesis, or square bracket.</span></span>

- <span data-ttu-id="f1bd3-473">Процессор `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-473">Cmd: `<Ctrl+]>`</span></span>
- <span data-ttu-id="f1bd3-474">Режим вставки в VI: `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-474">Vi insert mode: `<Ctrl+]>`</span></span>
- <span data-ttu-id="f1bd3-475">Режим команд VI: `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-475">Vi command mode: `<Ctrl+]>`</span></span>

### <a name="gotocolumn"></a><span data-ttu-id="f1bd3-476">готоколумн</span><span class="sxs-lookup"><span data-stu-id="f1bd3-476">GotoColumn</span></span>

<span data-ttu-id="f1bd3-477">Переход к столбцу, указанному аргументом arg.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-477">Move to the column indicated by arg.</span></span>

- <span data-ttu-id="f1bd3-478">Режим команд VI: `<|>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-478">Vi command mode: `<|>`</span></span>

### <a name="gotofirstnonblankofline"></a><span data-ttu-id="f1bd3-479">готофирстнонбланкофлине</span><span class="sxs-lookup"><span data-stu-id="f1bd3-479">GotoFirstNonBlankOfLine</span></span>

<span data-ttu-id="f1bd3-480">Переместить курсор к первому непустому символу в строке.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-480">Move the cursor to the first non-blank character in the line.</span></span>

- <span data-ttu-id="f1bd3-481">Режим команд VI: `<^>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-481">Vi command mode: `<^>`</span></span>

### <a name="movetoendofline"></a><span data-ttu-id="f1bd3-482">моветоендофлине</span><span class="sxs-lookup"><span data-stu-id="f1bd3-482">MoveToEndOfLine</span></span>

<span data-ttu-id="f1bd3-483">Переместить курсор в конец входных данных.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-483">Move the cursor to the end of the input.</span></span>

- <span data-ttu-id="f1bd3-484">Режим команд VI: `<End>` , `<$>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-484">Vi command mode: `<End>`, `<$>`</span></span>

### <a name="nextline"></a><span data-ttu-id="f1bd3-485">некстлине</span><span class="sxs-lookup"><span data-stu-id="f1bd3-485">NextLine</span></span>

<span data-ttu-id="f1bd3-486">Переместить курсор на следующую строку.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-486">Move the cursor to the next line.</span></span>

- <span data-ttu-id="f1bd3-487">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-487">Function is unbound.</span></span>

### <a name="nextword"></a><span data-ttu-id="f1bd3-488">некстворд</span><span class="sxs-lookup"><span data-stu-id="f1bd3-488">NextWord</span></span>

<span data-ttu-id="f1bd3-489">Переместить курсор вперед к началу следующего слова.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-489">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="f1bd3-490">Границы слов определяются с помощью настраиваемого набора символов.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-490">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="f1bd3-491">Процессор `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-491">Cmd: `<Ctrl+RightArrow>`</span></span>
- <span data-ttu-id="f1bd3-492">Режим вставки в VI: `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-492">Vi insert mode: `<Ctrl+RightArrow>`</span></span>
- <span data-ttu-id="f1bd3-493">Режим команд VI: `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-493">Vi command mode: `<Ctrl+RightArrow>`</span></span>

### <a name="nextwordend"></a><span data-ttu-id="f1bd3-494">некстворденд</span><span class="sxs-lookup"><span data-stu-id="f1bd3-494">NextWordEnd</span></span>

<span data-ttu-id="f1bd3-495">Переместить курсор вперед к концу текущего слова или между словами, до конца следующего слова.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-495">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="f1bd3-496">Границы слов определяются с помощью настраиваемого набора символов.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-496">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="f1bd3-497">Режим команд VI: `<e>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-497">Vi command mode: `<e>`</span></span>

### <a name="previousline"></a><span data-ttu-id="f1bd3-498">превиауслине</span><span class="sxs-lookup"><span data-stu-id="f1bd3-498">PreviousLine</span></span>

<span data-ttu-id="f1bd3-499">Переместить курсор на предыдущую строку.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-499">Move the cursor to the previous line.</span></span>

- <span data-ttu-id="f1bd3-500">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-500">Function is unbound.</span></span>

### <a name="shellbackwardword"></a><span data-ttu-id="f1bd3-501">шеллбакквардворд</span><span class="sxs-lookup"><span data-stu-id="f1bd3-501">ShellBackwardWord</span></span>

<span data-ttu-id="f1bd3-502">Перемещение курсора назад к началу текущего слова или между словами, с начала предыдущего слова.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-502">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="f1bd3-503">Границы слов определяются токенами PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-503">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="f1bd3-504">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-504">Function is unbound.</span></span>

### <a name="shellforwardword"></a><span data-ttu-id="f1bd3-505">шеллфорвардворд</span><span class="sxs-lookup"><span data-stu-id="f1bd3-505">ShellForwardWord</span></span>

<span data-ttu-id="f1bd3-506">Переместить курсор вперед к началу следующего слова.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-506">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="f1bd3-507">Границы слов определяются токенами PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-507">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="f1bd3-508">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-508">Function is unbound.</span></span>

### <a name="shellnextword"></a><span data-ttu-id="f1bd3-509">шеллнекстворд</span><span class="sxs-lookup"><span data-stu-id="f1bd3-509">ShellNextWord</span></span>

<span data-ttu-id="f1bd3-510">Переместить курсор вперед к концу текущего слова или между словами, до конца следующего слова.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-510">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="f1bd3-511">Границы слов определяются токенами PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-511">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="f1bd3-512">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-512">Function is unbound.</span></span>

### <a name="vibackwardword"></a><span data-ttu-id="f1bd3-513">вибакквардворд</span><span class="sxs-lookup"><span data-stu-id="f1bd3-513">ViBackwardWord</span></span>

<span data-ttu-id="f1bd3-514">Перемещение курсора назад к началу текущего слова или между словами, с начала предыдущего слова.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-514">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="f1bd3-515">Границы слов определяются с помощью настраиваемого набора символов.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-515">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="f1bd3-516">Режим команд VI: `<b>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-516">Vi command mode: `<b>`</span></span>

### <a name="viendofglob"></a><span data-ttu-id="f1bd3-517">виендофглоб</span><span class="sxs-lookup"><span data-stu-id="f1bd3-517">ViEndOfGlob</span></span>

<span data-ttu-id="f1bd3-518">Перемещает курсор в конец слова, используя только пробелы в качестве разделителей.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-518">Moves the cursor to the end of the word, using only white space as delimiters.</span></span>

- <span data-ttu-id="f1bd3-519">Режим команд VI: `<E>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-519">Vi command mode: `<E>`</span></span>

### <a name="viendofpreviousglob"></a><span data-ttu-id="f1bd3-520">виендофпревиаусглоб</span><span class="sxs-lookup"><span data-stu-id="f1bd3-520">ViEndOfPreviousGlob</span></span>

<span data-ttu-id="f1bd3-521">Переход к концу предыдущего слова с использованием только пробелов в качестве разделителя слов.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-521">Moves to the end of the previous word, using only white space as a word delimiter.</span></span>

- <span data-ttu-id="f1bd3-522">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-522">Function is unbound.</span></span>

### <a name="vigotobrace"></a><span data-ttu-id="f1bd3-523">виготобраце</span><span class="sxs-lookup"><span data-stu-id="f1bd3-523">ViGotoBrace</span></span>

<span data-ttu-id="f1bd3-524">Аналогичен Готобраце, но является символом, а не основан на токене.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-524">Similar to GotoBrace, but is character based instead of token based.</span></span>

- <span data-ttu-id="f1bd3-525">Режим команд VI: `<%>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-525">Vi command mode: `<%>`</span></span>

### <a name="vinextglob"></a><span data-ttu-id="f1bd3-526">винекстглоб</span><span class="sxs-lookup"><span data-stu-id="f1bd3-526">ViNextGlob</span></span>

<span data-ttu-id="f1bd3-527">Переход к следующему слову с использованием только пробелов в качестве разделителя слов.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-527">Moves to the next word, using only white space as a word delimiter.</span></span>

- <span data-ttu-id="f1bd3-528">Режим команд VI: `<W>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-528">Vi command mode: `<W>`</span></span>

### <a name="vinextword"></a><span data-ttu-id="f1bd3-529">винекстворд</span><span class="sxs-lookup"><span data-stu-id="f1bd3-529">ViNextWord</span></span>

<span data-ttu-id="f1bd3-530">Переместить курсор вперед к началу следующего слова.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-530">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="f1bd3-531">Границы слов определяются с помощью настраиваемого набора символов.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-531">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="f1bd3-532">Режим команд VI: `<w>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-532">Vi command mode: `<w>`</span></span>

## <a name="history-functions"></a><span data-ttu-id="f1bd3-533">Функции журнала</span><span class="sxs-lookup"><span data-stu-id="f1bd3-533">History functions</span></span>

### <a name="beginningofhistory"></a><span data-ttu-id="f1bd3-534">бегиннингофхистори</span><span class="sxs-lookup"><span data-stu-id="f1bd3-534">BeginningOfHistory</span></span>

<span data-ttu-id="f1bd3-535">Перейти к первому элементу в журнале.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-535">Move to the first item in the history.</span></span>

- <span data-ttu-id="f1bd3-536">Emacs: `<Alt+`<>\`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-536">Emacs: `<Alt+`<>\`</span></span>

### <a name="clearhistory"></a><span data-ttu-id="f1bd3-537">клеархистори</span><span class="sxs-lookup"><span data-stu-id="f1bd3-537">ClearHistory</span></span>

<span data-ttu-id="f1bd3-538">Очищает журнал в PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-538">Clears history in PSReadLine.</span></span> <span data-ttu-id="f1bd3-539">Это не влияет на журнал PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-539">This does not affect PowerShell history.</span></span>

- <span data-ttu-id="f1bd3-540">Процессор `<Alt+F7>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-540">Cmd: `<Alt+F7>`</span></span>

### <a name="endofhistory"></a><span data-ttu-id="f1bd3-541">ендофхистори</span><span class="sxs-lookup"><span data-stu-id="f1bd3-541">EndOfHistory</span></span>

<span data-ttu-id="f1bd3-542">Переход к последнему элементу (текущему входному объекту) в журнале.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-542">Move to the last item (the current input) in the history.</span></span>

- <span data-ttu-id="f1bd3-543">Emacs: `<Alt+>>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-543">Emacs: `<Alt+>>`</span></span>

### <a name="forwardsearchhistory"></a><span data-ttu-id="f1bd3-544">форвардсеарчхистори</span><span class="sxs-lookup"><span data-stu-id="f1bd3-544">ForwardSearchHistory</span></span>

<span data-ttu-id="f1bd3-545">Выполните добавочный поиск по журналу.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-545">Perform an incremental forward search through history.</span></span>

- <span data-ttu-id="f1bd3-546">Процессор `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-546">Cmd: `<Ctrl+s>`</span></span>
- <span data-ttu-id="f1bd3-547">Emacs: `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-547">Emacs: `<Ctrl+s>`</span></span>

### <a name="historysearchbackward"></a><span data-ttu-id="f1bd3-548">хисторисеарчбакквард</span><span class="sxs-lookup"><span data-stu-id="f1bd3-548">HistorySearchBackward</span></span>

<span data-ttu-id="f1bd3-549">Замените текущие входные данные элементом "Previous" из журнала PSReadLine, который соответствует символам между началом и входом и курсором.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-549">Replace the current input with the 'previous' item from PSReadLine history that matches the characters between the start and the input and the cursor.</span></span>

- <span data-ttu-id="f1bd3-550">Процессор `<F8>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-550">Cmd: `<F8>`</span></span>

### <a name="historysearchforward"></a><span data-ttu-id="f1bd3-551">хисторисеарчфорвард</span><span class="sxs-lookup"><span data-stu-id="f1bd3-551">HistorySearchForward</span></span>

<span data-ttu-id="f1bd3-552">Замените текущие входные данные элементом "Next" из журнала PSReadLine, который соответствует символам между началом и входом и курсором.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-552">Replace the current input with the 'next' item from PSReadLine history that matches the characters between the start and the input and the cursor.</span></span>

- <span data-ttu-id="f1bd3-553">Процессор `<Shift+F8>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-553">Cmd: `<Shift+F8>`</span></span>

### <a name="nexthistory"></a><span data-ttu-id="f1bd3-554">некссистори</span><span class="sxs-lookup"><span data-stu-id="f1bd3-554">NextHistory</span></span>

<span data-ttu-id="f1bd3-555">Замените текущие входные данные на элемент "Next" из журнала PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-555">Replace the current input with the 'next' item from PSReadLine history.</span></span>

- <span data-ttu-id="f1bd3-556">Процессор `<DownArrow>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-556">Cmd: `<DownArrow>`</span></span>
- <span data-ttu-id="f1bd3-557">Emacs: `<DownArrow>` , `<Ctrl+n>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-557">Emacs: `<DownArrow>`, `<Ctrl+n>`</span></span>
- <span data-ttu-id="f1bd3-558">Режим вставки в VI: `<DownArrow>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-558">Vi insert mode: `<DownArrow>`</span></span>
- <span data-ttu-id="f1bd3-559">Режим команд VI: `<DownArrow>` , `<j>` , `<+>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-559">Vi command mode: `<DownArrow>`, `<j>`, `<+>`</span></span>

### <a name="previoushistory"></a><span data-ttu-id="f1bd3-560">превиаушистори</span><span class="sxs-lookup"><span data-stu-id="f1bd3-560">PreviousHistory</span></span>

<span data-ttu-id="f1bd3-561">Замените текущие входные данные элементом "Previous" из журнала PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-561">Replace the current input with the 'previous' item from PSReadLine history.</span></span>

- <span data-ttu-id="f1bd3-562">Процессор `<UpArrow>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-562">Cmd: `<UpArrow>`</span></span>
- <span data-ttu-id="f1bd3-563">Emacs: `<UpArrow>` , `<Ctrl+p>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-563">Emacs: `<UpArrow>`, `<Ctrl+p>`</span></span>
- <span data-ttu-id="f1bd3-564">Режим вставки в VI: `<UpArrow>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-564">Vi insert mode: `<UpArrow>`</span></span>
- <span data-ttu-id="f1bd3-565">Режим команд VI: `<UpArrow>` , `<k>` , `<->`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-565">Vi command mode: `<UpArrow>`, `<k>`, `<->`</span></span>

### <a name="reversesearchhistory"></a><span data-ttu-id="f1bd3-566">реверсесеарчхистори</span><span class="sxs-lookup"><span data-stu-id="f1bd3-566">ReverseSearchHistory</span></span>

<span data-ttu-id="f1bd3-567">Выполните добавочный поиск по журналу.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-567">Perform an incremental backward search through history.</span></span>

- <span data-ttu-id="f1bd3-568">Процессор `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-568">Cmd: `<Ctrl+r>`</span></span>
- <span data-ttu-id="f1bd3-569">Emacs: `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-569">Emacs: `<Ctrl+r>`</span></span>

### <a name="visearchhistorybackward"></a><span data-ttu-id="f1bd3-570">висеарчхисторибакквард</span><span class="sxs-lookup"><span data-stu-id="f1bd3-570">ViSearchHistoryBackward</span></span>

<span data-ttu-id="f1bd3-571">Запрашивает строку поиска и инициирует поиск по запросу Акцептлине.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-571">Prompts for a search string and initiates search upon AcceptLine.</span></span>

- <span data-ttu-id="f1bd3-572">Режим вставки в VI: `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-572">Vi insert mode: `<Ctrl+r>`</span></span>
- <span data-ttu-id="f1bd3-573">Режим команд VI: `</>` , `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-573">Vi command mode: `</>`, `<Ctrl+r>`</span></span>

## <a name="completion-functions"></a><span data-ttu-id="f1bd3-574">Функции завершения</span><span class="sxs-lookup"><span data-stu-id="f1bd3-574">Completion functions</span></span>

### <a name="complete"></a><span data-ttu-id="f1bd3-575">Завершить</span><span class="sxs-lookup"><span data-stu-id="f1bd3-575">Complete</span></span>

<span data-ttu-id="f1bd3-576">Попытка выполнить завершение в тексте, окружающем курсор.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-576">Attempt to perform completion on the text surrounding the cursor.</span></span> <span data-ttu-id="f1bd3-577">Если существует несколько возможных завершений, для завершения используется самый длинный ненеоднозначный префикс.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-577">If there are multiple possible completions, the longest unambiguous prefix is used for completion.</span></span> <span data-ttu-id="f1bd3-578">При попытке выполнить наибольшее неоднозначное Завершение отображается список возможных завершений.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-578">If trying to complete the longest unambiguous completion, a list of possible completions is displayed.</span></span>

- <span data-ttu-id="f1bd3-579">Emacs: `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-579">Emacs: `<Tab>`</span></span>

### <a name="menucomplete"></a><span data-ttu-id="f1bd3-580">менукомплете</span><span class="sxs-lookup"><span data-stu-id="f1bd3-580">MenuComplete</span></span>

<span data-ttu-id="f1bd3-581">Попытка выполнить завершение в тексте, окружающем курсор.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-581">Attempt to perform completion on the text surrounding the cursor.</span></span> <span data-ttu-id="f1bd3-582">Если существует несколько возможных завершений, для завершения используется самый длинный ненеоднозначный префикс.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-582">If there are multiple possible completions, the longest unambiguous prefix is used for completion.</span></span> <span data-ttu-id="f1bd3-583">При попытке выполнить наибольшее неоднозначное Завершение отображается список возможных завершений.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-583">If trying to complete the longest unambiguous completion, a list of possible completions is displayed.</span></span>

- <span data-ttu-id="f1bd3-584">Процессор `<Ctrl+Space>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-584">Cmd: `<Ctrl+Space>`</span></span>
- <span data-ttu-id="f1bd3-585">Emacs: `<Ctrl+Space>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-585">Emacs: `<Ctrl+Space>`</span></span>

### <a name="possiblecompletions"></a><span data-ttu-id="f1bd3-586">поссиблекомплетионс</span><span class="sxs-lookup"><span data-stu-id="f1bd3-586">PossibleCompletions</span></span>

<span data-ttu-id="f1bd3-587">Отображение списка возможных завершений.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-587">Display the list of possible completions.</span></span>

- <span data-ttu-id="f1bd3-588">Emacs: `<Alt+=>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-588">Emacs: `<Alt+=>`</span></span>
- <span data-ttu-id="f1bd3-589">Режим вставки в VI: `<Ctrl+Space>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-589">Vi insert mode: `<Ctrl+Space>`</span></span>
- <span data-ttu-id="f1bd3-590">Режим команд VI: `<Ctrl+Space>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-590">Vi command mode: `<Ctrl+Space>`</span></span>

### <a name="tabcompletenext"></a><span data-ttu-id="f1bd3-591">табкомплетенекст</span><span class="sxs-lookup"><span data-stu-id="f1bd3-591">TabCompleteNext</span></span>

<span data-ttu-id="f1bd3-592">Попытайтесь завершить текст, окружающий курсор, с помощью следующего доступного завершения.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-592">Attempt to complete the text surrounding the cursor with the next available completion.</span></span>

- <span data-ttu-id="f1bd3-593">Процессор `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-593">Cmd: `<Tab>`</span></span>
- <span data-ttu-id="f1bd3-594">Режим команд VI: `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-594">Vi command mode: `<Tab>`</span></span>

### <a name="tabcompleteprevious"></a><span data-ttu-id="f1bd3-595">табкомплетепревиаус</span><span class="sxs-lookup"><span data-stu-id="f1bd3-595">TabCompletePrevious</span></span>

<span data-ttu-id="f1bd3-596">Попытайтесь завершить текст, окружающий курсор, с предыдущим доступным завершением.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-596">Attempt to complete the text surrounding the cursor with the previous available completion.</span></span>

- <span data-ttu-id="f1bd3-597">Процессор `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-597">Cmd: `<Shift+Tab>`</span></span>
- <span data-ttu-id="f1bd3-598">Режим команд VI: `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-598">Vi command mode: `<Shift+Tab>`</span></span>

### <a name="vitabcompletenext"></a><span data-ttu-id="f1bd3-599">витабкомплетенекст</span><span class="sxs-lookup"><span data-stu-id="f1bd3-599">ViTabCompleteNext</span></span>

<span data-ttu-id="f1bd3-600">При необходимости завершает текущую группу редактирования и вызывает Табкомплетенекст.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-600">Ends the current edit group, if needed, and invokes TabCompleteNext.</span></span>

- <span data-ttu-id="f1bd3-601">Режим вставки в VI: `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-601">Vi insert mode: `<Tab>`</span></span>

### <a name="vitabcompleteprevious"></a><span data-ttu-id="f1bd3-602">витабкомплетепревиаус</span><span class="sxs-lookup"><span data-stu-id="f1bd3-602">ViTabCompletePrevious</span></span>

<span data-ttu-id="f1bd3-603">При необходимости завершает текущую группу редактирования и вызывает Табкомплетепревиаус.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-603">Ends the current edit group, if needed, and invokes TabCompletePrevious.</span></span>

- <span data-ttu-id="f1bd3-604">Режим вставки в VI: `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-604">Vi insert mode: `<Shift+Tab>`</span></span>

## <a name="miscellaneous-functions"></a><span data-ttu-id="f1bd3-605">Прочие функции</span><span class="sxs-lookup"><span data-stu-id="f1bd3-605">Miscellaneous functions</span></span>

### <a name="capturescreen"></a><span data-ttu-id="f1bd3-606">каптурескрин</span><span class="sxs-lookup"><span data-stu-id="f1bd3-606">CaptureScreen</span></span>

<span data-ttu-id="f1bd3-607">Запуск интерактивной записи экрана — стрелки вверх и вниз выбор строк, ввод копирует выделенный текст в буфер обмена в виде текста и HTML.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-607">Start interactive screen capture - up/down arrows select lines, enter copies selected text to clipboard as text and html.</span></span>

- <span data-ttu-id="f1bd3-608">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-608">Function is unbound.</span></span>

### <a name="clearscreen"></a><span data-ttu-id="f1bd3-609">клеарскрин</span><span class="sxs-lookup"><span data-stu-id="f1bd3-609">ClearScreen</span></span>

<span data-ttu-id="f1bd3-610">Очистить экран и нарисовать текущую строку в верхней части экрана.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-610">Clear the screen and draw the current line at the top of the screen.</span></span>

- <span data-ttu-id="f1bd3-611">Процессор `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-611">Cmd: `<Ctrl+l>`</span></span>
- <span data-ttu-id="f1bd3-612">Emacs: `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-612">Emacs: `<Ctrl+l>`</span></span>
- <span data-ttu-id="f1bd3-613">Режим вставки в VI: `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-613">Vi insert mode: `<Ctrl+l>`</span></span>
- <span data-ttu-id="f1bd3-614">Режим команд VI: `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-614">Vi command mode: `<Ctrl+l>`</span></span>

### <a name="digitargument"></a><span data-ttu-id="f1bd3-615">дигитаргумент</span><span class="sxs-lookup"><span data-stu-id="f1bd3-615">DigitArgument</span></span>

<span data-ttu-id="f1bd3-616">Начните новый аргумент цифры для передачи другим функциям.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-616">Start a new digit argument to pass to other functions.</span></span>

- <span data-ttu-id="f1bd3-617">Cmd: `<Alt+0>` , `<Alt+1>` , `<Alt+2>` , `<Alt+3>` , `<Alt+4>` , `<Alt+5>` , `<Alt+6>` , `<Alt+7>` , `<Alt+8>` , `<Alt+9>` , `<Alt+->`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-617">Cmd: `<Alt+0>`, `<Alt+1>`, `<Alt+2>`, `<Alt+3>`, `<Alt+4>`, `<Alt+5>`, `<Alt+6>`, `<Alt+7>`, `<Alt+8>`, `<Alt+9>`, `<Alt+->`</span></span>
- <span data-ttu-id="f1bd3-618">Emacs: `<Alt+0>` , `<Alt+1>` , `<Alt+2>` , `<Alt+3>` , `<Alt+4>` , `<Alt+5>` , `<Alt+6>` , `<Alt+7>` , `<Alt+8>` , `<Alt+9>` , `<Alt+->`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-618">Emacs: `<Alt+0>`, `<Alt+1>`, `<Alt+2>`, `<Alt+3>`, `<Alt+4>`, `<Alt+5>`, `<Alt+6>`, `<Alt+7>`, `<Alt+8>`, `<Alt+9>`, `<Alt+->`</span></span>
- <span data-ttu-id="f1bd3-619">Режим команд VI: `<0>` , `<1>` , `<2>` , `<3>` , `<4>` , `<5>` , `<6>` , `<7>` , `<8>` , `<9>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-619">Vi command mode: `<0>`, `<1>`, `<2>`, `<3>`, `<4>`, `<5>`, `<6>`, `<7>`, `<8>`, `<9>`</span></span>

### <a name="invokeprompt"></a><span data-ttu-id="f1bd3-620">инвокепромпт</span><span class="sxs-lookup"><span data-stu-id="f1bd3-620">InvokePrompt</span></span>

<span data-ttu-id="f1bd3-621">Стирает текущий запрос и вызывает функцию Prompt для повторного вывода запроса.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-621">Erases the current prompt and calls the prompt function to redisplay the prompt.</span></span> <span data-ttu-id="f1bd3-622">Полезен для обработчиков пользовательских ключей, изменяющих состояние, например для изменения текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-622">Useful for custom key handlers that change state, e.g. change the current directory.</span></span>

- <span data-ttu-id="f1bd3-623">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-623">Function is unbound.</span></span>

### <a name="scrolldisplaydown"></a><span data-ttu-id="f1bd3-624">скроллдисплайдовн</span><span class="sxs-lookup"><span data-stu-id="f1bd3-624">ScrollDisplayDown</span></span>

<span data-ttu-id="f1bd3-625">Прокрутите экран вниз на один экран.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-625">Scroll the display down one screen.</span></span>

- <span data-ttu-id="f1bd3-626">Процессор `<PageDown>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-626">Cmd: `<PageDown>`</span></span>
- <span data-ttu-id="f1bd3-627">Emacs: `<PageDown>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-627">Emacs: `<PageDown>`</span></span>

### <a name="scrolldisplaydownline"></a><span data-ttu-id="f1bd3-628">скроллдисплайдовнлине</span><span class="sxs-lookup"><span data-stu-id="f1bd3-628">ScrollDisplayDownLine</span></span>

<span data-ttu-id="f1bd3-629">Прокрутите экран вниз на одну строку.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-629">Scroll the display down one line.</span></span>

- <span data-ttu-id="f1bd3-630">Процессор `<Ctrl+PageDown>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-630">Cmd: `<Ctrl+PageDown>`</span></span>
- <span data-ttu-id="f1bd3-631">Emacs: `<Ctrl+PageDown>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-631">Emacs: `<Ctrl+PageDown>`</span></span>

### <a name="scrolldisplaytocursor"></a><span data-ttu-id="f1bd3-632">скроллдисплайтокурсор</span><span class="sxs-lookup"><span data-stu-id="f1bd3-632">ScrollDisplayToCursor</span></span>

<span data-ttu-id="f1bd3-633">Прокрутить экран до курсора.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-633">Scroll the display to the cursor.</span></span>

- <span data-ttu-id="f1bd3-634">Emacs: `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-634">Emacs: `<Ctrl+End>`</span></span>

### <a name="scrolldisplaytop"></a><span data-ttu-id="f1bd3-635">скроллдисплайтоп</span><span class="sxs-lookup"><span data-stu-id="f1bd3-635">ScrollDisplayTop</span></span>

<span data-ttu-id="f1bd3-636">Прокрутите экран до верха.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-636">Scroll the display to the top.</span></span>

- <span data-ttu-id="f1bd3-637">Emacs: `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-637">Emacs: `<Ctrl+Home>`</span></span>

### <a name="scrolldisplayup"></a><span data-ttu-id="f1bd3-638">скроллдисплайуп</span><span class="sxs-lookup"><span data-stu-id="f1bd3-638">ScrollDisplayUp</span></span>

<span data-ttu-id="f1bd3-639">Прокрутите экран вверх на один экран.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-639">Scroll the display up one screen.</span></span>

- <span data-ttu-id="f1bd3-640">Процессор `<PageUp>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-640">Cmd: `<PageUp>`</span></span>
- <span data-ttu-id="f1bd3-641">Emacs: `<PageUp>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-641">Emacs: `<PageUp>`</span></span>

### <a name="scrolldisplayupline"></a><span data-ttu-id="f1bd3-642">скроллдисплайуплине</span><span class="sxs-lookup"><span data-stu-id="f1bd3-642">ScrollDisplayUpLine</span></span>

<span data-ttu-id="f1bd3-643">Прокрутите экран вверх на одну строку.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-643">Scroll the display up one line.</span></span>

- <span data-ttu-id="f1bd3-644">Процессор `<Ctrl+PageUp>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-644">Cmd: `<Ctrl+PageUp>`</span></span>
- <span data-ttu-id="f1bd3-645">Emacs: `<Ctrl+PageUp>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-645">Emacs: `<Ctrl+PageUp>`</span></span>

### <a name="selfinsert"></a><span data-ttu-id="f1bd3-646">селфинсерт</span><span class="sxs-lookup"><span data-stu-id="f1bd3-646">SelfInsert</span></span>

<span data-ttu-id="f1bd3-647">Вставьте ключ.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-647">Insert the key.</span></span>

- <span data-ttu-id="f1bd3-648">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-648">Function is unbound.</span></span>

### <a name="showkeybindings"></a><span data-ttu-id="f1bd3-649">шовкэйбиндингс</span><span class="sxs-lookup"><span data-stu-id="f1bd3-649">ShowKeyBindings</span></span>

<span data-ttu-id="f1bd3-650">Отображение всех связанных ключей.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-650">Show all bound keys.</span></span>

- <span data-ttu-id="f1bd3-651">Процессор `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-651">Cmd: `<Ctrl+Alt+?>`</span></span>
- <span data-ttu-id="f1bd3-652">Emacs: `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-652">Emacs: `<Ctrl+Alt+?>`</span></span>
- <span data-ttu-id="f1bd3-653">Режим вставки в VI: `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-653">Vi insert mode: `<Ctrl+Alt+?>`</span></span>

### <a name="vicommandmode"></a><span data-ttu-id="f1bd3-654">викоммандмоде</span><span class="sxs-lookup"><span data-stu-id="f1bd3-654">ViCommandMode</span></span>

<span data-ttu-id="f1bd3-655">Переключите текущий режим работы с Vi-Insert на VI-Command.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-655">Switch the current operating mode from Vi-Insert to Vi-Command.</span></span>

- <span data-ttu-id="f1bd3-656">Режим вставки в VI: `<Escape>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-656">Vi insert mode: `<Escape>`</span></span>

### <a name="vidigitargumentinchord"></a><span data-ttu-id="f1bd3-657">видигитаргументинчорд</span><span class="sxs-lookup"><span data-stu-id="f1bd3-657">ViDigitArgumentInChord</span></span>

<span data-ttu-id="f1bd3-658">Начните новый числовой аргумент, чтобы передать его другим функциям в одной из сочетаний VI.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-658">Start a new digit argument to pass to other functions while in one of vi's chords.</span></span>

- <span data-ttu-id="f1bd3-659">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-659">Function is unbound.</span></span>

### <a name="vieditvisually"></a><span data-ttu-id="f1bd3-660">виедитвисуалли</span><span class="sxs-lookup"><span data-stu-id="f1bd3-660">ViEditVisually</span></span>

<span data-ttu-id="f1bd3-661">Измените командную строку в текстовом редакторе, заданном $env: EDITOR или $env: VISUAL.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-661">Edit the command line in a text editor specified by $env:EDITOR or $env:VISUAL.</span></span>

- <span data-ttu-id="f1bd3-662">Emacs: `<Ctrl+x,Ctrl+e>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-662">Emacs: `<Ctrl+x,Ctrl+e>`</span></span>
- <span data-ttu-id="f1bd3-663">Режим команд VI: `<v>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-663">Vi command mode: `<v>`</span></span>

### <a name="viexit"></a><span data-ttu-id="f1bd3-664">виексит</span><span class="sxs-lookup"><span data-stu-id="f1bd3-664">ViExit</span></span>

<span data-ttu-id="f1bd3-665">Завершает работу оболочки.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-665">Exits the shell.</span></span>

- <span data-ttu-id="f1bd3-666">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-666">Function is unbound.</span></span>

### <a name="viinsertmode"></a><span data-ttu-id="f1bd3-667">виинсертмоде</span><span class="sxs-lookup"><span data-stu-id="f1bd3-667">ViInsertMode</span></span>

<span data-ttu-id="f1bd3-668">Переключитесь в режим вставки.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-668">Switch to Insert mode.</span></span>

- <span data-ttu-id="f1bd3-669">Режим команд VI: `<i>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-669">Vi command mode: `<i>`</span></span>

### <a name="whatiskey"></a><span data-ttu-id="f1bd3-670">вхатискэй</span><span class="sxs-lookup"><span data-stu-id="f1bd3-670">WhatIsKey</span></span>

<span data-ttu-id="f1bd3-671">Прочитайте ключ и расскажите, к чему привязан ключ.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-671">Read a key and tell me what the key is bound to.</span></span>

- <span data-ttu-id="f1bd3-672">Процессор `<Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-672">Cmd: `<Alt+?>`</span></span>
- <span data-ttu-id="f1bd3-673">Emacs: `<Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-673">Emacs: `<Alt+?>`</span></span>

## <a name="selection-functions"></a><span data-ttu-id="f1bd3-674">Функции выбора</span><span class="sxs-lookup"><span data-stu-id="f1bd3-674">Selection functions</span></span>

### <a name="exchangepointandmark"></a><span data-ttu-id="f1bd3-675">ексчанжепоинтандмарк</span><span class="sxs-lookup"><span data-stu-id="f1bd3-675">ExchangePointAndMark</span></span>

<span data-ttu-id="f1bd3-676">Курсор помещается в позицию метки, а метка перемещается в положение курсора.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-676">The cursor is placed at the location of the mark and the mark is moved to the location of the cursor.</span></span>

- <span data-ttu-id="f1bd3-677">Emacs: `<Ctrl+x,Ctrl+x>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-677">Emacs: `<Ctrl+x,Ctrl+x>`</span></span>

### <a name="selectall"></a><span data-ttu-id="f1bd3-678">SelectAll</span><span class="sxs-lookup"><span data-stu-id="f1bd3-678">SelectAll</span></span>

<span data-ttu-id="f1bd3-679">Выделите всю строку.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-679">Select the entire line.</span></span>

- <span data-ttu-id="f1bd3-680">Процессор `<Ctrl+a>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-680">Cmd: `<Ctrl+a>`</span></span>

### <a name="selectbackwardchar"></a><span data-ttu-id="f1bd3-681">селектбакквардчар</span><span class="sxs-lookup"><span data-stu-id="f1bd3-681">SelectBackwardChar</span></span>

<span data-ttu-id="f1bd3-682">Настройка текущего выделения для включения предыдущего символа.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-682">Adjust the current selection to include the previous character.</span></span>

- <span data-ttu-id="f1bd3-683">Процессор `<Shift+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-683">Cmd: `<Shift+LeftArrow>`</span></span>
- <span data-ttu-id="f1bd3-684">Emacs: `<Shift+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-684">Emacs: `<Shift+LeftArrow>`</span></span>

### <a name="selectbackwardsline"></a><span data-ttu-id="f1bd3-685">селектбакквардслине</span><span class="sxs-lookup"><span data-stu-id="f1bd3-685">SelectBackwardsLine</span></span>

<span data-ttu-id="f1bd3-686">Изменить текущее выделение, чтобы включить его от курсора до начала строки.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-686">Adjust the current selection to include from the cursor to the start of the line.</span></span>

- <span data-ttu-id="f1bd3-687">Процессор `<Shift+Home>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-687">Cmd: `<Shift+Home>`</span></span>
- <span data-ttu-id="f1bd3-688">Emacs: `<Shift+Home>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-688">Emacs: `<Shift+Home>`</span></span>

### <a name="selectbackwardword"></a><span data-ttu-id="f1bd3-689">селектбакквардворд</span><span class="sxs-lookup"><span data-stu-id="f1bd3-689">SelectBackwardWord</span></span>

<span data-ttu-id="f1bd3-690">Настройка текущего выделения для включения предыдущего слова.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-690">Adjust the current selection to include the previous word.</span></span>

- <span data-ttu-id="f1bd3-691">Процессор `<Shift+Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-691">Cmd: `<Shift+Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="f1bd3-692">Emacs: `<Alt+B>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-692">Emacs: `<Alt+B>`</span></span>

### <a name="selectforwardchar"></a><span data-ttu-id="f1bd3-693">селектфорвардчар</span><span class="sxs-lookup"><span data-stu-id="f1bd3-693">SelectForwardChar</span></span>

<span data-ttu-id="f1bd3-694">Измените текущее выделение, чтобы включить следующий символ.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-694">Adjust the current selection to include the next character.</span></span>

- <span data-ttu-id="f1bd3-695">Процессор `<Shift+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-695">Cmd: `<Shift+RightArrow>`</span></span>
- <span data-ttu-id="f1bd3-696">Emacs: `<Shift+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-696">Emacs: `<Shift+RightArrow>`</span></span>

### <a name="selectforwardword"></a><span data-ttu-id="f1bd3-697">селектфорвардворд</span><span class="sxs-lookup"><span data-stu-id="f1bd3-697">SelectForwardWord</span></span>

<span data-ttu-id="f1bd3-698">Измените текущее выделение, чтобы включить следующее слово с помощью Форвардворд.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-698">Adjust the current selection to include the next word using ForwardWord.</span></span>

- <span data-ttu-id="f1bd3-699">Emacs: `<Alt+F>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-699">Emacs: `<Alt+F>`</span></span>

### <a name="selectline"></a><span data-ttu-id="f1bd3-700">селектлине</span><span class="sxs-lookup"><span data-stu-id="f1bd3-700">SelectLine</span></span>

<span data-ttu-id="f1bd3-701">Настройка текущего выделения для включения курсора в конец строки.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-701">Adjust the current selection to include from the cursor to the end of the line.</span></span>

- <span data-ttu-id="f1bd3-702">Процессор `<Shift+End>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-702">Cmd: `<Shift+End>`</span></span>
- <span data-ttu-id="f1bd3-703">Emacs: `<Shift+End>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-703">Emacs: `<Shift+End>`</span></span>

### <a name="selectnextword"></a><span data-ttu-id="f1bd3-704">селектнекстворд</span><span class="sxs-lookup"><span data-stu-id="f1bd3-704">SelectNextWord</span></span>

<span data-ttu-id="f1bd3-705">Настройка текущего выделения для включения следующего слова.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-705">Adjust the current selection to include the next word.</span></span>

- <span data-ttu-id="f1bd3-706">Процессор `<Shift+Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-706">Cmd: `<Shift+Ctrl+RightArrow>`</span></span>

### <a name="selectshellbackwardword"></a><span data-ttu-id="f1bd3-707">селектшеллбакквардворд</span><span class="sxs-lookup"><span data-stu-id="f1bd3-707">SelectShellBackwardWord</span></span>

<span data-ttu-id="f1bd3-708">Измените текущее выделение, чтобы включить предыдущее слово с помощью Шеллбакквардворд.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-708">Adjust the current selection to include the previous word using ShellBackwardWord.</span></span>

- <span data-ttu-id="f1bd3-709">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-709">Function is unbound.</span></span>

### <a name="selectshellforwardword"></a><span data-ttu-id="f1bd3-710">селектшеллфорвардворд</span><span class="sxs-lookup"><span data-stu-id="f1bd3-710">SelectShellForwardWord</span></span>

<span data-ttu-id="f1bd3-711">Измените текущее выделение, чтобы включить следующее слово с помощью Шеллфорвардворд.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-711">Adjust the current selection to include the next word using ShellForwardWord.</span></span>

- <span data-ttu-id="f1bd3-712">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-712">Function is unbound.</span></span>

### <a name="selectshellnextword"></a><span data-ttu-id="f1bd3-713">селектшеллнекстворд</span><span class="sxs-lookup"><span data-stu-id="f1bd3-713">SelectShellNextWord</span></span>

<span data-ttu-id="f1bd3-714">Измените текущее выделение, чтобы включить следующее слово с помощью Шеллнекстворд.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-714">Adjust the current selection to include the next word using ShellNextWord.</span></span>

- <span data-ttu-id="f1bd3-715">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-715">Function is unbound.</span></span>

### <a name="setmark"></a><span data-ttu-id="f1bd3-716">сетмарк</span><span class="sxs-lookup"><span data-stu-id="f1bd3-716">SetMark</span></span>

<span data-ttu-id="f1bd3-717">Пометка текущего положения курсора для использования в последующей команде редактирования.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-717">Mark the current location of the cursor for use in a subsequent editing command.</span></span>

- <span data-ttu-id="f1bd3-718">Emacs: `<Ctrl+`>\`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-718">Emacs: `<Ctrl+`>\`</span></span>

## <a name="search-functions"></a><span data-ttu-id="f1bd3-719">Функции поиска</span><span class="sxs-lookup"><span data-stu-id="f1bd3-719">Search functions</span></span>

### <a name="charactersearch"></a><span data-ttu-id="f1bd3-720">чарактерсеарч</span><span class="sxs-lookup"><span data-stu-id="f1bd3-720">CharacterSearch</span></span>

<span data-ttu-id="f1bd3-721">Чтение символа и поиск вперед для следующего вхождения этого символа.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-721">Read a character and search forward for the next occurrence of that character.</span></span>
<span data-ttu-id="f1bd3-722">Если указан аргумент, то для n-го вхождения выполните поиск вперед (или назад, если отрицательное).</span><span class="sxs-lookup"><span data-stu-id="f1bd3-722">If an argument is specified, search forward (or backward if negative) for the nth occurrence.</span></span>

- <span data-ttu-id="f1bd3-723">Процессор `<F3>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-723">Cmd: `<F3>`</span></span>
- <span data-ttu-id="f1bd3-724">Emacs: `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-724">Emacs: `<Ctrl+]>`</span></span>
- <span data-ttu-id="f1bd3-725">Режим вставки в VI: `<F3>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-725">Vi insert mode: `<F3>`</span></span>
- <span data-ttu-id="f1bd3-726">Режим команд VI: `<F3>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-726">Vi command mode: `<F3>`</span></span>

### <a name="charactersearchbackward"></a><span data-ttu-id="f1bd3-727">чарактерсеарчбакквард</span><span class="sxs-lookup"><span data-stu-id="f1bd3-727">CharacterSearchBackward</span></span>

<span data-ttu-id="f1bd3-728">Чтение символа и поиск следующего вхождения этого символа в обратном направлении.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-728">Read a character and search backward for the next occurrence of that character.</span></span> <span data-ttu-id="f1bd3-729">Если аргумент указан, поиск в n-й последовательности осуществляется назад (или вперед, если отрицательное).</span><span class="sxs-lookup"><span data-stu-id="f1bd3-729">If an argument is specified, search backward (or forward if negative) for the nth occurrence.</span></span>

- <span data-ttu-id="f1bd3-730">Процессор `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-730">Cmd: `<Shift+F3>`</span></span>
- <span data-ttu-id="f1bd3-731">Emacs: `<Ctrl+Alt+]>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-731">Emacs: `<Ctrl+Alt+]>`</span></span>
- <span data-ttu-id="f1bd3-732">Режим вставки в VI: `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-732">Vi insert mode: `<Shift+F3>`</span></span>
- <span data-ttu-id="f1bd3-733">Режим команд VI: `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-733">Vi command mode: `<Shift+F3>`</span></span>

### <a name="repeatlastcharsearch"></a><span data-ttu-id="f1bd3-734">репеатластчарсеарч</span><span class="sxs-lookup"><span data-stu-id="f1bd3-734">RepeatLastCharSearch</span></span>

<span data-ttu-id="f1bd3-735">Повторите поиск последнего записанного символа.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-735">Repeat the last recorded character search.</span></span>

- <span data-ttu-id="f1bd3-736">Режим команд VI: `<;>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-736">Vi command mode: `<;>`</span></span>

### <a name="repeatlastcharsearchbackwards"></a><span data-ttu-id="f1bd3-737">репеатластчарсеарчбакквардс</span><span class="sxs-lookup"><span data-stu-id="f1bd3-737">RepeatLastCharSearchBackwards</span></span>

<span data-ttu-id="f1bd3-738">Повторите поиск последнего записанного символа, но в обратном направлении.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-738">Repeat the last recorded character search, but in the opposite direction.</span></span>

- <span data-ttu-id="f1bd3-739">Режим команд VI: `<,>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-739">Vi command mode: `<,>`</span></span>

### <a name="repeatsearch"></a><span data-ttu-id="f1bd3-740">репеатсеарч</span><span class="sxs-lookup"><span data-stu-id="f1bd3-740">RepeatSearch</span></span>

<span data-ttu-id="f1bd3-741">Повторите последний поиск в том же направлении, что и раньше.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-741">Repeat the last search in the same direction as before.</span></span>

- <span data-ttu-id="f1bd3-742">Режим команд VI: `<n>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-742">Vi command mode: `<n>`</span></span>

### <a name="repeatsearchbackward"></a><span data-ttu-id="f1bd3-743">репеатсеарчбакквард</span><span class="sxs-lookup"><span data-stu-id="f1bd3-743">RepeatSearchBackward</span></span>

<span data-ttu-id="f1bd3-744">Повторите последний поиск в том же направлении, что и раньше.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-744">Repeat the last search in the same direction as before.</span></span>

- <span data-ttu-id="f1bd3-745">Режим команд VI: `<N>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-745">Vi command mode: `<N>`</span></span>

### <a name="searchchar"></a><span data-ttu-id="f1bd3-746">сеарччар</span><span class="sxs-lookup"><span data-stu-id="f1bd3-746">SearchChar</span></span>

<span data-ttu-id="f1bd3-747">Прочитать следующий символ, затем найти его, перейти вперед, а затем отследить символ.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-747">Read the next character and then find it, going forward, and then back off a character.</span></span> <span data-ttu-id="f1bd3-748">Это относится к функциональным возможностям.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-748">This is for 't' functionality.</span></span>

- <span data-ttu-id="f1bd3-749">Режим команд VI: `<f>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-749">Vi command mode: `<f>`</span></span>

### <a name="searchcharbackward"></a><span data-ttu-id="f1bd3-750">сеарччарбакквард</span><span class="sxs-lookup"><span data-stu-id="f1bd3-750">SearchCharBackward</span></span>

<span data-ttu-id="f1bd3-751">Прочитать следующий символ, а затем найти его, вернуться назад, а затем отследить символ.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-751">Read the next character and then find it, going backward, and then back off a character.</span></span> <span data-ttu-id="f1bd3-752">Это относится к функциональным возможностям.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-752">This is for 'T' functionality.</span></span>

- <span data-ttu-id="f1bd3-753">Режим команд VI: `<F>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-753">Vi command mode: `<F>`</span></span>

### <a name="searchcharbackwardwithbackoff"></a><span data-ttu-id="f1bd3-754">сеарччарбакквардвисбаккофф</span><span class="sxs-lookup"><span data-stu-id="f1bd3-754">SearchCharBackwardWithBackoff</span></span>

<span data-ttu-id="f1bd3-755">Прочитать следующий символ, а затем найти его, вернуться назад, а затем отследить символ.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-755">Read the next character and then find it, going backward, and then back off a character.</span></span> <span data-ttu-id="f1bd3-756">Это относится к функциональным возможностям.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-756">This is for 'T' functionality.</span></span>

- <span data-ttu-id="f1bd3-757">Режим команд VI: `<T>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-757">Vi command mode: `<T>`</span></span>

### <a name="searchcharwithbackoff"></a><span data-ttu-id="f1bd3-758">сеарччарвисбаккофф</span><span class="sxs-lookup"><span data-stu-id="f1bd3-758">SearchCharWithBackoff</span></span>

<span data-ttu-id="f1bd3-759">Прочитать следующий символ, затем найти его, перейти вперед, а затем отследить символ.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-759">Read the next character and then find it, going forward, and then back off a character.</span></span> <span data-ttu-id="f1bd3-760">Это относится к функциональным возможностям.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-760">This is for 't' functionality.</span></span>

- <span data-ttu-id="f1bd3-761">Режим команд VI: `<t>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-761">Vi command mode: `<t>`</span></span>

### <a name="searchforward"></a><span data-ttu-id="f1bd3-762">сеарчфорвард</span><span class="sxs-lookup"><span data-stu-id="f1bd3-762">SearchForward</span></span>

<span data-ttu-id="f1bd3-763">Запрашивает строку поиска и инициирует поиск по запросу Акцептлине.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-763">Prompts for a search string and initiates search upon AcceptLine.</span></span>

- <span data-ttu-id="f1bd3-764">Режим вставки в VI: `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-764">Vi insert mode: `<Ctrl+s>`</span></span>
- <span data-ttu-id="f1bd3-765">Режим команд VI: `<?>` , `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="f1bd3-765">Vi command mode: `<?>`, `<Ctrl+s>`</span></span>

## <a name="custom-key-bindings"></a><span data-ttu-id="f1bd3-766">Пользовательские привязки клавиш</span><span class="sxs-lookup"><span data-stu-id="f1bd3-766">Custom Key Bindings</span></span>

<span data-ttu-id="f1bd3-767">PSReadLine поддерживает пользовательские привязки клавиш с помощью командлета `Set-PSReadLineKeyHandler` .</span><span class="sxs-lookup"><span data-stu-id="f1bd3-767">PSReadLine supports custom key bindings using the cmdlet `Set-PSReadLineKeyHandler`.</span></span> <span data-ttu-id="f1bd3-768">Большинство пользовательских привязок вызывают одну из приведенных выше функций, например</span><span class="sxs-lookup"><span data-stu-id="f1bd3-768">Most custom key bindings call one of the above functions, for example</span></span>

```powershell
Set-PSReadLineKeyHandler -Key UpArrow -Function HistorySearchBackward
```

<span data-ttu-id="f1bd3-769">Можно привязать ScriptBlock к ключу.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-769">You can bind a ScriptBlock to a key.</span></span> <span data-ttu-id="f1bd3-770">Блок ScriptBlock может выполнять практически все необходимые действия.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-770">The ScriptBlock can do pretty much anything you want.</span></span> <span data-ttu-id="f1bd3-771">Ниже приведены некоторые полезные примеры.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-771">Some useful examples include</span></span>

- <span data-ttu-id="f1bd3-772">Изменение командной строки</span><span class="sxs-lookup"><span data-stu-id="f1bd3-772">edit the command line</span></span>
- <span data-ttu-id="f1bd3-773">Открытие нового окна (например, Справка)</span><span class="sxs-lookup"><span data-stu-id="f1bd3-773">opening a new window (e.g. help)</span></span>
- <span data-ttu-id="f1bd3-774">Изменение каталогов без изменения командной строки</span><span class="sxs-lookup"><span data-stu-id="f1bd3-774">change directories without changing the command line</span></span>

<span data-ttu-id="f1bd3-775">Блок ScriptBlock получает два аргумента:</span><span class="sxs-lookup"><span data-stu-id="f1bd3-775">The ScriptBlock receives two arguments:</span></span>

- <span data-ttu-id="f1bd3-776">`$key` — Объект **[консолекэйинфо]** , который является ключом, запускающим пользовательскую привязку.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-776">`$key` - A **[ConsoleKeyInfo]** object that is the key that triggered the custom binding.</span></span> <span data-ttu-id="f1bd3-777">Если один и тот же блок сценария привязан к нескольким ключам и необходимо выполнять различные действия в зависимости от ключа, можно проверить $key.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-777">If you bind the same ScriptBlock to multiple keys and need to perform different actions depending on the key, you can check $key.</span></span> <span data-ttu-id="f1bd3-778">Многие пользовательские привязки игнорируют этот аргумент.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-778">Many custom bindings ignore this argument.</span></span>

- <span data-ttu-id="f1bd3-779">`$arg` — Произвольный аргумент.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-779">`$arg` - An arbitrary argument.</span></span> <span data-ttu-id="f1bd3-780">Чаще всего это будет целочисленный аргумент, который пользователь передает из ключевых привязок Дигитаргумент.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-780">Most often, this would be an integer argument that the user passes from the key bindings DigitArgument.</span></span> <span data-ttu-id="f1bd3-781">Если привязка не принимает аргументы, целесообразно проигнорировать этот аргумент.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-781">If your binding doesn't accept arguments, it's reasonable to ignore this argument.</span></span>

<span data-ttu-id="f1bd3-782">Рассмотрим пример, который добавляет в журнал командную строку, не выполняя ее.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-782">Let's take a look at an example that adds a command line to history without executing it.</span></span> <span data-ttu-id="f1bd3-783">Это полезно, если вы забыли сделать что-то, но не хотите повторно вводить уже введенную командную строку.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-783">This is useful when you realize you forgot to do something, but don't want to re-enter the command line you've already entered.</span></span>

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

<span data-ttu-id="f1bd3-784">В файле, `SamplePSReadLineProfile.ps1` который устанавливается в папку модуля PSReadLine, можно увидеть много других примеров.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-784">You can see many more examples in the file `SamplePSReadLineProfile.ps1` which is installed in the PSReadLine module folder.</span></span>

<span data-ttu-id="f1bd3-785">Большинство ключевых привязок используют некоторые вспомогательные функции для редактирования командной строки.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-785">Most key bindings use some helper functions for editing the command line.</span></span>
<span data-ttu-id="f1bd3-786">Эти API-интерфейсы описаны в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-786">Those APIs are documented in the next section.</span></span>

## <a name="custom-key-binding-support-apis"></a><span data-ttu-id="f1bd3-787">API поддержки пользовательского сочетания клавиш</span><span class="sxs-lookup"><span data-stu-id="f1bd3-787">Custom Key Binding Support APIs</span></span>

<span data-ttu-id="f1bd3-788">Следующие функции являются открытыми в Microsoft. PowerShell. Псконсолереадлине, но не могут быть напрямую привязаны к ключу.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-788">The following functions are public in Microsoft.PowerShell.PSConsoleReadLine, but cannot be directly bound to a key.</span></span> <span data-ttu-id="f1bd3-789">Большинство из них удобно использовать в пользовательских привязках клавиш.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-789">Most are useful in custom key bindings.</span></span>

```csharp
void AddToHistory(string command)
```

<span data-ttu-id="f1bd3-790">Добавьте командную строку в журнал, не выполняя ее.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-790">Add a command line to history without executing it.</span></span>

```csharp
void ClearKillRing()
```

<span data-ttu-id="f1bd3-791">Снимите флажок Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-791">Clear the kill-ring.</span></span>  <span data-ttu-id="f1bd3-792">Это в основном используется для тестирования.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-792">This is mostly used for testing.</span></span>

```csharp
void Delete(int start, int length)
```

<span data-ttu-id="f1bd3-793">Удалить символы длины из Start.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-793">Delete length characters from start.</span></span>  <span data-ttu-id="f1bd3-794">Эта операция поддерживает операцию отмены и повтора.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-794">This operation supports undo/redo.</span></span>

```csharp
void Ding()
```

<span data-ttu-id="f1bd3-795">Выполните действие DING, основанное на предпочтениях пользователей.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-795">Perform the Ding action based on the users preference.</span></span>

```csharp
void GetBufferState([ref] string input, [ref] int cursor)
void GetBufferState([ref] Ast ast, [ref] Token[] tokens,
  [ref] ParseError[] parseErrors, [ref] int cursor)
```

<span data-ttu-id="f1bd3-796">Эти две функции извлекают полезную информацию о текущем состоянии входного буфера.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-796">These two functions retrieve useful information about the current state of the input buffer.</span></span>  <span data-ttu-id="f1bd3-797">Первый из них чаще всего используется в простых случаях.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-797">The first is more commonly used for simple cases.</span></span>  <span data-ttu-id="f1bd3-798">Второй используется, если привязка делает что-то более сложное с AST.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-798">The second is used if your binding is doing something more advanced with the Ast.</span></span>

```csharp
IEnumerable[Microsoft.PowerShell.KeyHandler]
  GetKeyHandlers(bool includeBound, bool includeUnbound)

```

<span data-ttu-id="f1bd3-799">Эта функция используется Get-PSReadLineKeyHandler и, возможно, не полезна в пользовательской привязке ключа.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-799">This function is used by Get-PSReadLineKeyHandler and probably isn't useful in a custom key binding.</span></span>

```csharp
Microsoft.PowerShell.PSConsoleReadLineOptions GetOptions()
```

<span data-ttu-id="f1bd3-800">Эта функция используется Get-PSReadLineOption и, возможно, не слишком полезна в пользовательской привязке ключа.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-800">This function is used by Get-PSReadLineOption and probably isn't too useful in a custom key binding.</span></span>

```csharp
void GetSelectionState([ref] int start, [ref] int length)
```

<span data-ttu-id="f1bd3-801">Если в командной строке ничего не выбрано, значение-1 будет возвращено как в начале, так и в длине.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-801">If there is no selection on the command line, -1 will be returned in both start and length.</span></span> <span data-ttu-id="f1bd3-802">Если в командной строке имеется выделенный фрагмент, то начинается и длина выбора возвращается.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-802">If there is a selection on the command line, the start and length of the selection are returned.</span></span>

```csharp
void Insert(char c)
void Insert(string s)
```

<span data-ttu-id="f1bd3-803">Вставка символа или строки в курсоре.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-803">Insert a character or string at the cursor.</span></span>  <span data-ttu-id="f1bd3-804">Эта операция поддерживает операцию отмены и повтора.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-804">This operation supports undo/redo.</span></span>

```csharp
string ReadLine(runspace remoteRunspace,
  System.Management.Automation.EngineIntrinsics engineIntrinsics)
```

<span data-ttu-id="f1bd3-805">Это Главная точка входа для PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-805">This is the main entry point to PSReadLine.</span></span> <span data-ttu-id="f1bd3-806">Она не поддерживает рекурсию, поэтому она не полезна в пользовательской привязке ключа.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-806">It does not support recursion, so is not useful in a custom key binding.</span></span>

```csharp
void RemoveKeyHandler(string[] key)
```

<span data-ttu-id="f1bd3-807">Эта функция используется Remove-PSReadLineKeyHandler и, возможно, не слишком полезна в пользовательской привязке ключа.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-807">This function is used by Remove-PSReadLineKeyHandler and probably isn't too useful in a custom key binding.</span></span>

```csharp
void Replace(int start, int length, string replacement)
```

<span data-ttu-id="f1bd3-808">Замените некоторые входные данные.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-808">Replace some of the input.</span></span> <span data-ttu-id="f1bd3-809">Эта операция поддерживает операцию отмены и повтора.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-809">This operation supports undo/redo.</span></span> <span data-ttu-id="f1bd3-810">Это предпочтительнее удаление с последующим вставкой, так как оно обрабатывается как одно действие для отмены.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-810">This is preferred over Delete followed by Insert because it is treated as a single action for undo.</span></span>

```csharp
void SetCursorPosition(int cursor)
```

<span data-ttu-id="f1bd3-811">Переместить курсор к заданному смещению.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-811">Move the cursor to the given offset.</span></span> <span data-ttu-id="f1bd3-812">Перемещение курсора не ведется для отмены.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-812">Cursor movement is not tracked for undo.</span></span>

```csharp
void SetOptions(Microsoft.PowerShell.SetPSReadLineOption options)
```

<span data-ttu-id="f1bd3-813">Эта функция является вспомогательным методом, используемым командлетом Set-PSReadLineOption, но может быть полезен для пользовательской привязки ключа, которая хочет временно изменить параметр.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-813">This function is a helper method used by the cmdlet Set-PSReadLineOption, but might be useful to a custom key binding that wants to temporarily change a setting.</span></span>

```csharp
bool TryGetArgAsInt(System.Object arg, [ref] int numericArg,
  int defaultNumericArg)
```

<span data-ttu-id="f1bd3-814">Этот вспомогательный метод используется для пользовательских привязок, которые учитывают Дигитаргумент.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-814">This helper method is used for custom bindings that honor DigitArgument.</span></span> <span data-ttu-id="f1bd3-815">Обычный вызов выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="f1bd3-815">A typical call looks like</span></span>

```powershell
[int]$numericArg = 0
[Microsoft.PowerShell.PSConsoleReadLine]::TryGetArgAsInt($arg,
  [ref]$numericArg, 1)
```

## <a name="note"></a><span data-ttu-id="f1bd3-816">ПРИМЕЧАНИЕ</span><span class="sxs-lookup"><span data-stu-id="f1bd3-816">NOTE</span></span>

### <a name="powershell-compatibility"></a><span data-ttu-id="f1bd3-817">СОВМЕСТИМОСТЬ С POWERSHELL</span><span class="sxs-lookup"><span data-stu-id="f1bd3-817">POWERSHELL COMPATIBILITY</span></span>

<span data-ttu-id="f1bd3-818">Для PSReadLine требуется PowerShell 3,0, более поздней версии и узел консоли.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-818">PSReadLine requires PowerShell 3.0, or newer, and the console host.</span></span> <span data-ttu-id="f1bd3-819">Он не работает в интегрированной среде сценариев PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-819">It does not work in PowerShell ISE.</span></span> <span data-ttu-id="f1bd3-820">Она работает в консоли Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-820">It does work in the console of Visual Studio Code.</span></span>

### <a name="command-history"></a><span data-ttu-id="f1bd3-821">ЖУРНАЛ КОМАНД</span><span class="sxs-lookup"><span data-stu-id="f1bd3-821">COMMAND HISTORY</span></span>

<span data-ttu-id="f1bd3-822">PSReadLine поддерживает файл журнала, содержащий все команды и данные, введенные из командной строки.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-822">PSReadLine maintains a history file containing all the commands and data you have entered from the command line.</span></span> <span data-ttu-id="f1bd3-823">Это может быть конфиденциальные данные, включая пароли.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-823">This may contain sensitive data including passwords.</span></span> <span data-ttu-id="f1bd3-824">Например, при использовании `ConvertTo-SecureString` командлета пароль заносится в файл журнала в виде обычного текста.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-824">For example, if you use the `ConvertTo-SecureString` cmdlet the password is logged in the history file as plain text.</span></span> <span data-ttu-id="f1bd3-825">Файлы журнала — это файл с именем `$($host.Name)_history.txt` .</span><span class="sxs-lookup"><span data-stu-id="f1bd3-825">The history files is a file named `$($host.Name)_history.txt`.</span></span> <span data-ttu-id="f1bd3-826">В системах Windows файл журнала хранится в файле `$env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine` .</span><span class="sxs-lookup"><span data-stu-id="f1bd3-826">On Windows systems the history file is stored at `$env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine`.</span></span> <span data-ttu-id="f1bd3-827">В системах, отличных от Windows, файлы журнала хранятся в `$env:XDG_DATA_HOME/powershell/PSReadLine` или `$env:HOME/.local/share/powershell/PSReadLine` .</span><span class="sxs-lookup"><span data-stu-id="f1bd3-827">On non-Windows systems, the history files is stored at `$env:XDG_DATA_HOME/powershell/PSReadLine` or `$env:HOME/.local/share/powershell/PSReadLine`.</span></span>

### <a name="feedback--contributing-to-psreadline"></a><span data-ttu-id="f1bd3-828">ОБРАТная связь & участие в PSReadLine</span><span class="sxs-lookup"><span data-stu-id="f1bd3-828">FEEDBACK & CONTRIBUTING TO PSReadLine</span></span>

[<span data-ttu-id="f1bd3-829">PSReadLine на GitHub</span><span class="sxs-lookup"><span data-stu-id="f1bd3-829">PSReadLine on GitHub</span></span>](https://github.com/PowerShell/PSReadLine)

<span data-ttu-id="f1bd3-830">Вы можете отправить запрос на вытягивание или отправить отзыв на страницу GitHub.</span><span class="sxs-lookup"><span data-stu-id="f1bd3-830">Feel free to submit a pull request or submit feedback on the GitHub page.</span></span>

## <a name="see-also"></a><span data-ttu-id="f1bd3-831">СМ. ТАКЖЕ</span><span class="sxs-lookup"><span data-stu-id="f1bd3-831">SEE ALSO</span></span>

<span data-ttu-id="f1bd3-832">На PSReadLine сильно влияют библиотеки GNU [ReadLine](https://tiswww.case.edu/php/chet/readline/rltop.html) .</span><span class="sxs-lookup"><span data-stu-id="f1bd3-832">PSReadLine is heavily influenced by the GNU [readline](https://tiswww.case.edu/php/chet/readline/rltop.html) library.</span></span>
