---
description: PSReadLine предоставляет улучшенные возможности редактирования командной строки в консоли PowerShell.
keywords: powershell
Locale: en-US
ms.date: 02/10/2020
online version: https://docs.microsoft.com/powershell/module/psreadline/about/about_psreadline?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: О PSReadLine
ms.openlocfilehash: f5ae99a7c8bdae82372423a3e4d8261d95ab83d5
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "94692213"
---
# <a name="psreadline"></a><span data-ttu-id="5f29b-104">PSReadLine</span><span class="sxs-lookup"><span data-stu-id="5f29b-104">PSReadLine</span></span>

## <a name="about_psreadline"></a><span data-ttu-id="5f29b-105">about_PSReadLine</span><span class="sxs-lookup"><span data-stu-id="5f29b-105">about_PSReadLine</span></span>

## <a name="short-description"></a><span data-ttu-id="5f29b-106">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="5f29b-106">Short Description</span></span>

<span data-ttu-id="5f29b-107">PSReadLine предоставляет улучшенные возможности редактирования командной строки в консоли PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5f29b-107">PSReadLine provides an improved command-line editing experience in the PowerShell console.</span></span>

## <a name="long-description"></a><span data-ttu-id="5f29b-108">Полное описание</span><span class="sxs-lookup"><span data-stu-id="5f29b-108">Long Description</span></span>

<span data-ttu-id="5f29b-109">PSReadLine 2,0 предоставляет широкие возможности редактирования командной строки для консоли PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5f29b-109">PSReadLine 2.0 provides a powerful command-line editing experience for the PowerShell console.</span></span> <span data-ttu-id="5f29b-110">Консоль предоставляет следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="5f29b-110">It provides:</span></span>

- <span data-ttu-id="5f29b-111">Цветовое выделение синтаксиса командной строки</span><span class="sxs-lookup"><span data-stu-id="5f29b-111">Syntax coloring of the command line</span></span>
- <span data-ttu-id="5f29b-112">Визуальное обозначение синтаксических ошибок</span><span class="sxs-lookup"><span data-stu-id="5f29b-112">A visual indication of syntax errors</span></span>
- <span data-ttu-id="5f29b-113">Более эффективный многострочный интерфейс (как редактирование, так и журнал)</span><span class="sxs-lookup"><span data-stu-id="5f29b-113">A better multi-line experience (both editing and history)</span></span>
- <span data-ttu-id="5f29b-114">Настраиваемые сочетания клавиш</span><span class="sxs-lookup"><span data-stu-id="5f29b-114">Customizable key bindings</span></span>
- <span data-ttu-id="5f29b-115">Режимы работы cmd и Emacs</span><span class="sxs-lookup"><span data-stu-id="5f29b-115">Cmd and Emacs modes</span></span>
- <span data-ttu-id="5f29b-116">Множество параметров конфигурации</span><span class="sxs-lookup"><span data-stu-id="5f29b-116">Many configuration options</span></span>
- <span data-ttu-id="5f29b-117">Завершение стиля bash (необязательно в режиме cmd, по умолчанию в режиме Emacs)</span><span class="sxs-lookup"><span data-stu-id="5f29b-117">Bash style completion (optional in Cmd mode, default in Emacs mode)</span></span>
- <span data-ttu-id="5f29b-118">Emacs: Янк/Kill-Ring</span><span class="sxs-lookup"><span data-stu-id="5f29b-118">Emacs yank/kill-ring</span></span>
- <span data-ttu-id="5f29b-119">Перемещение и уничтожение токена PowerShell на основе маркеров "Word"</span><span class="sxs-lookup"><span data-stu-id="5f29b-119">PowerShell token based "word" movement and kill</span></span>

> [!NOTE]
> <span data-ttu-id="5f29b-120">Начиная с PowerShell 7,0, PowerShell пропускает автоматическую загрузку PSReadLine в Windows при обнаружении программы чтения с экрана.</span><span class="sxs-lookup"><span data-stu-id="5f29b-120">Beginning with PowerShell 7.0, PowerShell skips auto-loading PSReadLine on Windows if a screen reader program is detected.</span></span> <span data-ttu-id="5f29b-121">В настоящее время PSReadLine плохо работает с программами чтения с экрана.</span><span class="sxs-lookup"><span data-stu-id="5f29b-121">Currently, PSReadLine doesn't work well with the screen readers.</span></span> <span data-ttu-id="5f29b-122">Визуализация и форматирование по умолчанию для PowerShell 7,0 в Windows работают правильно.</span><span class="sxs-lookup"><span data-stu-id="5f29b-122">The default rendering and formatting of PowerShell 7.0 on Windows works properly.</span></span> <span data-ttu-id="5f29b-123">При необходимости модуль можно загрузить вручную.</span><span class="sxs-lookup"><span data-stu-id="5f29b-123">You can manually load the module if necessary.</span></span>

<span data-ttu-id="5f29b-124">В классе **[Microsoft. PowerShell. псконсолереадлине]** доступны следующие функции.</span><span class="sxs-lookup"><span data-stu-id="5f29b-124">The following functions are available in the class **[Microsoft.PowerShell.PSConsoleReadLine]**.</span></span>

## <a name="basic-editing-functions"></a><span data-ttu-id="5f29b-125">Базовые функции редактирования</span><span class="sxs-lookup"><span data-stu-id="5f29b-125">Basic editing functions</span></span>

### <a name="abort"></a><span data-ttu-id="5f29b-126">Прерывание</span><span class="sxs-lookup"><span data-stu-id="5f29b-126">Abort</span></span>

<span data-ttu-id="5f29b-127">Прервать текущее действие, например добавочный поиск по журналу.</span><span class="sxs-lookup"><span data-stu-id="5f29b-127">Abort current action, e.g. incremental history search.</span></span>

- <span data-ttu-id="5f29b-128">Emacs: `<Ctrl+g>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-128">Emacs: `<Ctrl+g>`</span></span>

### <a name="acceptandgetnext"></a><span data-ttu-id="5f29b-129">акцептанджетнекст</span><span class="sxs-lookup"><span data-stu-id="5f29b-129">AcceptAndGetNext</span></span>

<span data-ttu-id="5f29b-130">Попытка выполнить текущий вход.</span><span class="sxs-lookup"><span data-stu-id="5f29b-130">Attempt to execute the current input.</span></span> <span data-ttu-id="5f29b-131">Если его можно выполнить (например, Акцептлине), то следует отозвать следующий элемент из журнала при следующем вызове метода ReadLine.</span><span class="sxs-lookup"><span data-stu-id="5f29b-131">If it can be executed (like AcceptLine), then recall the next item from history the next time ReadLine is called.</span></span>

- <span data-ttu-id="5f29b-132">Emacs: `<Ctrl+o>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-132">Emacs: `<Ctrl+o>`</span></span>

### <a name="acceptline"></a><span data-ttu-id="5f29b-133">акцептлине</span><span class="sxs-lookup"><span data-stu-id="5f29b-133">AcceptLine</span></span>

<span data-ttu-id="5f29b-134">Попытка выполнить текущий вход.</span><span class="sxs-lookup"><span data-stu-id="5f29b-134">Attempt to execute the current input.</span></span> <span data-ttu-id="5f29b-135">Если текущий ввод неполон (например, отсутствует закрывающая круглая скобка, квадратная скобка или кавычка, запрос продолжения отображается на следующей строке, а PSReadLine ожидает ввода ключей для изменения текущих входных данных.</span><span class="sxs-lookup"><span data-stu-id="5f29b-135">If the current input is incomplete (for example there is a missing closing parenthesis, bracket, or quote, then the continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span>

- <span data-ttu-id="5f29b-136">Процессор `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-136">Cmd: `<Enter>`</span></span>
- <span data-ttu-id="5f29b-137">Emacs: `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-137">Emacs: `<Enter>`</span></span>
- <span data-ttu-id="5f29b-138">Режим вставки в VI: `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-138">Vi insert mode: `<Enter>`</span></span>

### <a name="addline"></a><span data-ttu-id="5f29b-139">аддлине</span><span class="sxs-lookup"><span data-stu-id="5f29b-139">AddLine</span></span>

<span data-ttu-id="5f29b-140">Запрос продолжения отображается на следующей строке, а PSReadLine ожидает ввода ключей для изменения текущих входных данных.</span><span class="sxs-lookup"><span data-stu-id="5f29b-140">The continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span> <span data-ttu-id="5f29b-141">Это полезно для ввода многострочных входных данных в виде одной команды, даже если одна строка завершается самим вводом.</span><span class="sxs-lookup"><span data-stu-id="5f29b-141">This is useful to enter multi-line input as a single command even when a single line is complete input by itself.</span></span>

- <span data-ttu-id="5f29b-142">Процессор `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-142">Cmd: `<Shift+Enter>`</span></span>
- <span data-ttu-id="5f29b-143">Emacs: `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-143">Emacs: `<Shift+Enter>`</span></span>
- <span data-ttu-id="5f29b-144">Режим вставки в VI: `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-144">Vi insert mode: `<Shift+Enter>`</span></span>
- <span data-ttu-id="5f29b-145">Режим команд VI: `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-145">Vi command mode: `<Shift+Enter>`</span></span>

### <a name="backwarddeletechar"></a><span data-ttu-id="5f29b-146">бакквардделетечар</span><span class="sxs-lookup"><span data-stu-id="5f29b-146">BackwardDeleteChar</span></span>

<span data-ttu-id="5f29b-147">Удалить символ перед курсором.</span><span class="sxs-lookup"><span data-stu-id="5f29b-147">Delete the character before the cursor.</span></span>

- <span data-ttu-id="5f29b-148">Cmd: `<Backspace>` , `<Ctrl+h>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-148">Cmd: `<Backspace>`, `<Ctrl+h>`</span></span>
- <span data-ttu-id="5f29b-149">Emacs: `<Backspace>` , `<Ctrl+Backspace>` , `<Ctrl+h>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-149">Emacs: `<Backspace>`, `<Ctrl+Backspace>`, `<Ctrl+h>`</span></span>
- <span data-ttu-id="5f29b-150">Режим вставки в VI: `<Backspace>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-150">Vi insert mode: `<Backspace>`</span></span>
- <span data-ttu-id="5f29b-151">Режим команд VI: `<X>` , `<d,h>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-151">Vi command mode: `<X>`, `<d,h>`</span></span>

### <a name="backwarddeleteline"></a><span data-ttu-id="5f29b-152">бакквардделетелине</span><span class="sxs-lookup"><span data-stu-id="5f29b-152">BackwardDeleteLine</span></span>

<span data-ttu-id="5f29b-153">Like Бакквардкилллине — удаляет текст с точки до начала строки, но не помещает удаленный текст в инструкцию KILL-Ring.</span><span class="sxs-lookup"><span data-stu-id="5f29b-153">Like BackwardKillLine - deletes text from the point to the start of the line, but does not put the deleted text in the kill-ring.</span></span>

- <span data-ttu-id="5f29b-154">Процессор `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-154">Cmd: `<Ctrl+Home>`</span></span>
- <span data-ttu-id="5f29b-155">Режим вставки в VI: `<Ctrl+u>` , `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-155">Vi insert mode: `<Ctrl+u>`, `<Ctrl+Home>`</span></span>
- <span data-ttu-id="5f29b-156">Режим команд VI: `<Ctrl+u>` , `<Ctrl+Home>` , `<d,0>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-156">Vi command mode: `<Ctrl+u>`, `<Ctrl+Home>`, `<d,0>`</span></span>

### <a name="backwarddeleteword"></a><span data-ttu-id="5f29b-157">бакквардделетеворд</span><span class="sxs-lookup"><span data-stu-id="5f29b-157">BackwardDeleteWord</span></span>

<span data-ttu-id="5f29b-158">Удаляет предыдущее слово.</span><span class="sxs-lookup"><span data-stu-id="5f29b-158">Deletes the previous word.</span></span>

- <span data-ttu-id="5f29b-159">Режим команд VI: `<Ctrl+w>` , `<d,b>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-159">Vi command mode: `<Ctrl+w>`, `<d,b>`</span></span>

### <a name="backwardkillline"></a><span data-ttu-id="5f29b-160">бакквардкилллине</span><span class="sxs-lookup"><span data-stu-id="5f29b-160">BackwardKillLine</span></span>

<span data-ttu-id="5f29b-161">Очистить входные данные от начала ввода до курсора.</span><span class="sxs-lookup"><span data-stu-id="5f29b-161">Clear the input from the start of the input to the cursor.</span></span> <span data-ttu-id="5f29b-162">Очистка текста помещается в буфер Kill.</span><span class="sxs-lookup"><span data-stu-id="5f29b-162">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="5f29b-163">Emacs: `<Ctrl+u>` , `<Ctrl+x,Backspace>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-163">Emacs: `<Ctrl+u>`, `<Ctrl+x,Backspace>`</span></span>

### <a name="backwardkillword"></a><span data-ttu-id="5f29b-164">бакквардкиллворд</span><span class="sxs-lookup"><span data-stu-id="5f29b-164">BackwardKillWord</span></span>

<span data-ttu-id="5f29b-165">Очистить ввод от начала текущего слова до курсора.</span><span class="sxs-lookup"><span data-stu-id="5f29b-165">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="5f29b-166">Если курсор находится между словами, входные данные очищаются от начала предыдущего слова до курсора.</span><span class="sxs-lookup"><span data-stu-id="5f29b-166">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="5f29b-167">Очистка текста помещается в буфер Kill.</span><span class="sxs-lookup"><span data-stu-id="5f29b-167">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="5f29b-168">Процессор `<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-168">Cmd: `<Ctrl+Backspace>`</span></span>
- <span data-ttu-id="5f29b-169">Emacs: `<Alt+Backspace>` , `<Escape,Backspace>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-169">Emacs: `<Alt+Backspace>`, `<Escape,Backspace>`</span></span>
- <span data-ttu-id="5f29b-170">Режим вставки в VI: `<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-170">Vi insert mode: `<Ctrl+Backspace>`</span></span>
- <span data-ttu-id="5f29b-171">Режим команд VI: `<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-171">Vi command mode: `<Ctrl+Backspace>`</span></span>

### <a name="cancelline"></a><span data-ttu-id="5f29b-172">канцеллине</span><span class="sxs-lookup"><span data-stu-id="5f29b-172">CancelLine</span></span>

<span data-ttu-id="5f29b-173">Отмена текущих входных данных с выходом на экран, но возврат к узлу, чтобы снова выполнить оценку запроса.</span><span class="sxs-lookup"><span data-stu-id="5f29b-173">Cancel the current input, leaving the input on the screen, but returns back to the host so the prompt is evaluated again.</span></span>

- <span data-ttu-id="5f29b-174">Режим вставки в VI: `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-174">Vi insert mode: `<Ctrl+c>`</span></span>
- <span data-ttu-id="5f29b-175">Режим команд VI: `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-175">Vi command mode: `<Ctrl+c>`</span></span>

### <a name="copy"></a><span data-ttu-id="5f29b-176">Копировать</span><span class="sxs-lookup"><span data-stu-id="5f29b-176">Copy</span></span>

<span data-ttu-id="5f29b-177">Копировать выбранный регион в буфер обмена системы.</span><span class="sxs-lookup"><span data-stu-id="5f29b-177">Copy selected region to the system clipboard.</span></span> <span data-ttu-id="5f29b-178">Если регион не выбран, скопируйте всю строку.</span><span class="sxs-lookup"><span data-stu-id="5f29b-178">If no region is selected, copy the whole line.</span></span>

- <span data-ttu-id="5f29b-179">Процессор `<Ctrl+C>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-179">Cmd: `<Ctrl+C>`</span></span>

### <a name="copyorcancelline"></a><span data-ttu-id="5f29b-180">копйорканцеллине</span><span class="sxs-lookup"><span data-stu-id="5f29b-180">CopyOrCancelLine</span></span>

<span data-ttu-id="5f29b-181">Если выбран текст, скопируйте в буфер обмена, в противном случае отмените строку.</span><span class="sxs-lookup"><span data-stu-id="5f29b-181">If text is selected, copy to the clipboard, otherwise cancel the line.</span></span>

- <span data-ttu-id="5f29b-182">Процессор `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-182">Cmd: `<Ctrl+c>`</span></span>
- <span data-ttu-id="5f29b-183">Emacs: `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-183">Emacs: `<Ctrl+c>`</span></span>

### <a name="cut"></a><span data-ttu-id="5f29b-184">Вырезать</span><span class="sxs-lookup"><span data-stu-id="5f29b-184">Cut</span></span>

<span data-ttu-id="5f29b-185">Удалить выбранный регион, поместив удаленный текст в системный буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="5f29b-185">Delete selected region placing deleted text in the system clipboard.</span></span>

- <span data-ttu-id="5f29b-186">Процессор `<Ctrl+x>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-186">Cmd: `<Ctrl+x>`</span></span>

### <a name="deletechar"></a><span data-ttu-id="5f29b-187">делетечар</span><span class="sxs-lookup"><span data-stu-id="5f29b-187">DeleteChar</span></span>

<span data-ttu-id="5f29b-188">Удалите символ под курсором.</span><span class="sxs-lookup"><span data-stu-id="5f29b-188">Delete the character under the cursor.</span></span>

- <span data-ttu-id="5f29b-189">Процессор `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-189">Cmd: `<Delete>`</span></span>
- <span data-ttu-id="5f29b-190">Emacs: `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-190">Emacs: `<Delete>`</span></span>
- <span data-ttu-id="5f29b-191">Режим вставки в VI: `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-191">Vi insert mode: `<Delete>`</span></span>
- <span data-ttu-id="5f29b-192">Режим команд VI: `<Delete>` , `<x>` , `<d,l>` , `<d,Space>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-192">Vi command mode: `<Delete>`, `<x>`, `<d,l>`, `<d,Space>`</span></span>

### <a name="deletecharorexit"></a><span data-ttu-id="5f29b-193">делетечарорексит</span><span class="sxs-lookup"><span data-stu-id="5f29b-193">DeleteCharOrExit</span></span>

<span data-ttu-id="5f29b-194">Удалите символ под курсором или, если строка пуста, завершите процесс.</span><span class="sxs-lookup"><span data-stu-id="5f29b-194">Delete the character under the cursor, or if the line is empty, exit the process.</span></span>

- <span data-ttu-id="5f29b-195">Emacs: `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-195">Emacs: `<Ctrl+d>`</span></span>

### <a name="deleteendofword"></a><span data-ttu-id="5f29b-196">делетиндофворд</span><span class="sxs-lookup"><span data-stu-id="5f29b-196">DeleteEndOfWord</span></span>

<span data-ttu-id="5f29b-197">Удалить до конца слова.</span><span class="sxs-lookup"><span data-stu-id="5f29b-197">Delete to the end of the word.</span></span>

- <span data-ttu-id="5f29b-198">Режим команд VI: `<d,e>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-198">Vi command mode: `<d,e>`</span></span>

### <a name="deleteline"></a><span data-ttu-id="5f29b-199">Сбой deleteline</span><span class="sxs-lookup"><span data-stu-id="5f29b-199">DeleteLine</span></span>

<span data-ttu-id="5f29b-200">Удаляет текущую строку, включая отмену.</span><span class="sxs-lookup"><span data-stu-id="5f29b-200">Deletes the current line, enabling undo.</span></span>

- <span data-ttu-id="5f29b-201">Режим команд VI: `<d,d>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-201">Vi command mode: `<d,d>`</span></span>

### <a name="deletelinetofirstchar"></a><span data-ttu-id="5f29b-202">делетелинетофирстчар</span><span class="sxs-lookup"><span data-stu-id="5f29b-202">DeleteLineToFirstChar</span></span>

<span data-ttu-id="5f29b-203">Удаляет текст из курсора на первый символ строки, отличный от пробела.</span><span class="sxs-lookup"><span data-stu-id="5f29b-203">Deletes text from the cursor to the first non-blank character of the line.</span></span>

- <span data-ttu-id="5f29b-204">Режим команд VI: `<d,^>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-204">Vi command mode: `<d,^>`</span></span>

### <a name="deletetoend"></a><span data-ttu-id="5f29b-205">делететоенд</span><span class="sxs-lookup"><span data-stu-id="5f29b-205">DeleteToEnd</span></span>

<span data-ttu-id="5f29b-206">Удалить до конца строки.</span><span class="sxs-lookup"><span data-stu-id="5f29b-206">Delete to the end of the line.</span></span>

- <span data-ttu-id="5f29b-207">Режим команд VI: `<D>` , `<d,$>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-207">Vi command mode: `<D>`, `<d,$>`</span></span>

### <a name="deleteword"></a><span data-ttu-id="5f29b-208">DeleteWord</span><span class="sxs-lookup"><span data-stu-id="5f29b-208">DeleteWord</span></span>

<span data-ttu-id="5f29b-209">Удалить следующее слово.</span><span class="sxs-lookup"><span data-stu-id="5f29b-209">Delete the next word.</span></span>

- <span data-ttu-id="5f29b-210">Режим команд VI: `<d,w>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-210">Vi command mode: `<d,w>`</span></span>

### <a name="forwarddeleteline"></a><span data-ttu-id="5f29b-211">форвардделетелине</span><span class="sxs-lookup"><span data-stu-id="5f29b-211">ForwardDeleteLine</span></span>

<span data-ttu-id="5f29b-212">Как и Форвардкилллине — удаляет текст с точки до конца строки, но не помещает удаленный текст в инструкцию KILL-Ring.</span><span class="sxs-lookup"><span data-stu-id="5f29b-212">Like ForwardKillLine - deletes text from the point to the end of the line, but does not put the deleted text in the kill-ring.</span></span>

- <span data-ttu-id="5f29b-213">Процессор `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-213">Cmd: `<Ctrl+End>`</span></span>
- <span data-ttu-id="5f29b-214">Режим вставки в VI: `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-214">Vi insert mode: `<Ctrl+End>`</span></span>
- <span data-ttu-id="5f29b-215">Режим команд VI: `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-215">Vi command mode: `<Ctrl+End>`</span></span>

### <a name="insertlineabove"></a><span data-ttu-id="5f29b-216">инсертлинеабове</span><span class="sxs-lookup"><span data-stu-id="5f29b-216">InsertLineAbove</span></span>

<span data-ttu-id="5f29b-217">Новая пустая строка создается над текущей строкой, независимо от того, где находится курсор на текущей строке.</span><span class="sxs-lookup"><span data-stu-id="5f29b-217">A new empty line is created above the current line regardless of where the cursor is on the current line.</span></span> <span data-ttu-id="5f29b-218">Курсор переместится в начало новой строки.</span><span class="sxs-lookup"><span data-stu-id="5f29b-218">The cursor moves to the beginning of the new line.</span></span>

- <span data-ttu-id="5f29b-219">Процессор `<Ctrl+Enter>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-219">Cmd: `<Ctrl+Enter>`</span></span>

### <a name="insertlinebelow"></a><span data-ttu-id="5f29b-220">инсертлинебелов</span><span class="sxs-lookup"><span data-stu-id="5f29b-220">InsertLineBelow</span></span>

<span data-ttu-id="5f29b-221">Новая пустая строка создается под текущей строкой независимо от того, где находится курсор на текущей строке.</span><span class="sxs-lookup"><span data-stu-id="5f29b-221">A new empty line is created below the current line regardless of where the cursor is on the current line.</span></span> <span data-ttu-id="5f29b-222">Курсор переместится в начало новой строки.</span><span class="sxs-lookup"><span data-stu-id="5f29b-222">The cursor moves to the beginning of the new line.</span></span>

- <span data-ttu-id="5f29b-223">Процессор `<Shift+Ctrl+Enter>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-223">Cmd: `<Shift+Ctrl+Enter>`</span></span>

### <a name="invertcase"></a><span data-ttu-id="5f29b-224">инверткасе</span><span class="sxs-lookup"><span data-stu-id="5f29b-224">InvertCase</span></span>

<span data-ttu-id="5f29b-225">Инвертировать регистр текущего символа и перейти к следующему.</span><span class="sxs-lookup"><span data-stu-id="5f29b-225">Invert the case of the current character and move to the next one.</span></span>

- <span data-ttu-id="5f29b-226">Режим команд VI: `<~>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-226">Vi command mode: `<~>`</span></span>

### <a name="killline"></a><span data-ttu-id="5f29b-227">килллине</span><span class="sxs-lookup"><span data-stu-id="5f29b-227">KillLine</span></span>

<span data-ttu-id="5f29b-228">Очистить входные данные от курсора до конца входных данных.</span><span class="sxs-lookup"><span data-stu-id="5f29b-228">Clear the input from the cursor to the end of the input.</span></span> <span data-ttu-id="5f29b-229">Очистка текста помещается в буфер Kill.</span><span class="sxs-lookup"><span data-stu-id="5f29b-229">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="5f29b-230">Emacs: `<Ctrl+k>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-230">Emacs: `<Ctrl+k>`</span></span>

### <a name="killregion"></a><span data-ttu-id="5f29b-231">киллрегион</span><span class="sxs-lookup"><span data-stu-id="5f29b-231">KillRegion</span></span>

<span data-ttu-id="5f29b-232">Удалить текст между курсором и меткой.</span><span class="sxs-lookup"><span data-stu-id="5f29b-232">Kill the text between the cursor and the mark.</span></span>

- <span data-ttu-id="5f29b-233">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="5f29b-233">Function is unbound.</span></span>

### <a name="killword"></a><span data-ttu-id="5f29b-234">киллворд</span><span class="sxs-lookup"><span data-stu-id="5f29b-234">KillWord</span></span>

<span data-ttu-id="5f29b-235">Очистить ввод от курсора до конца текущего слова.</span><span class="sxs-lookup"><span data-stu-id="5f29b-235">Clear the input from the cursor to the end of the current word.</span></span> <span data-ttu-id="5f29b-236">Если курсор находится между словами, входные данные очищаются от курсора до конца следующего слова.</span><span class="sxs-lookup"><span data-stu-id="5f29b-236">If the cursor is between words, the input is cleared from the cursor to the end of the next word.</span></span> <span data-ttu-id="5f29b-237">Очистка текста помещается в буфер Kill.</span><span class="sxs-lookup"><span data-stu-id="5f29b-237">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="5f29b-238">Процессор `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-238">Cmd: `<Ctrl+Delete>`</span></span>
- <span data-ttu-id="5f29b-239">Emacs: `<Alt+d>` , `<Escape,d>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-239">Emacs: `<Alt+d>`, `<Escape,d>`</span></span>
- <span data-ttu-id="5f29b-240">Режим вставки в VI: `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-240">Vi insert mode: `<Ctrl+Delete>`</span></span>
- <span data-ttu-id="5f29b-241">Режим команд VI: `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-241">Vi command mode: `<Ctrl+Delete>`</span></span>

### <a name="paste"></a><span data-ttu-id="5f29b-242">Вставить</span><span class="sxs-lookup"><span data-stu-id="5f29b-242">Paste</span></span>

<span data-ttu-id="5f29b-243">Вставка текста из буфера обмена системы.</span><span class="sxs-lookup"><span data-stu-id="5f29b-243">Paste text from the system clipboard.</span></span>

- <span data-ttu-id="5f29b-244">Cmd: `<Ctrl+v>` , `<Shift+Insert>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-244">Cmd: `<Ctrl+v>`, `<Shift+Insert>`</span></span>
- <span data-ttu-id="5f29b-245">Режим вставки в VI: `<Ctrl+v>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-245">Vi insert mode: `<Ctrl+v>`</span></span>
- <span data-ttu-id="5f29b-246">Режим команд VI: `<Ctrl+v>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-246">Vi command mode: `<Ctrl+v>`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5f29b-247">При использовании функции **вставки** все содержимое буфера буфера обмена вставляется во входной буфер PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="5f29b-247">When using the **Paste** function, the entire contents of the clipboard buffer is pasted into the input buffer of PSReadLine.</span></span> <span data-ttu-id="5f29b-248">Затем входной буфер передается средству синтаксического анализа PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5f29b-248">The input buffer is then passed to the PowerShell parser.</span></span> <span data-ttu-id="5f29b-249">Вход, вставленный с помощью консольного приложения, щелкните **правой кнопкой мыши** метод вставки, скопированный во входной буфер по одному символу за раз.</span><span class="sxs-lookup"><span data-stu-id="5f29b-249">Input pasted using the console application's **right-click** paste method is copied to the input buffer one character at a time.</span></span> <span data-ttu-id="5f29b-250">Входной буфер передается средству синтаксического анализа при копировании символа новой строки.</span><span class="sxs-lookup"><span data-stu-id="5f29b-250">The input buffer is passed to the parser when a newline character is copied.</span></span> <span data-ttu-id="5f29b-251">Поэтому входные данные анализируются по одной строке за раз.</span><span class="sxs-lookup"><span data-stu-id="5f29b-251">Therefore, the input is parsed one line at a time.</span></span> <span data-ttu-id="5f29b-252">Различие между методами вставки приводит к различному поведению при выполнении.</span><span class="sxs-lookup"><span data-stu-id="5f29b-252">The difference between paste methods results in different execution behavior.</span></span>

### <a name="pasteafter"></a><span data-ttu-id="5f29b-253">пастеафтер</span><span class="sxs-lookup"><span data-stu-id="5f29b-253">PasteAfter</span></span>

<span data-ttu-id="5f29b-254">Вставьте буфер обмена после курсора, переместив курсор в конец вставленного текста.</span><span class="sxs-lookup"><span data-stu-id="5f29b-254">Paste the clipboard after the cursor, moving the cursor to the end of the pasted text.</span></span>

- <span data-ttu-id="5f29b-255">Режим команд VI: `<p>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-255">Vi command mode: `<p>`</span></span>

### <a name="pastebefore"></a><span data-ttu-id="5f29b-256">пастебефоре</span><span class="sxs-lookup"><span data-stu-id="5f29b-256">PasteBefore</span></span>

<span data-ttu-id="5f29b-257">Вставьте буфер обмена перед курсором, переместив курсор в конец вставленного текста.</span><span class="sxs-lookup"><span data-stu-id="5f29b-257">Paste the clipboard before the cursor, moving the cursor to the end of the pasted text.</span></span>

- <span data-ttu-id="5f29b-258">Режим команд VI: `<P>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-258">Vi command mode: `<P>`</span></span>

### <a name="prependandaccept"></a><span data-ttu-id="5f29b-259">препендандакцепт</span><span class="sxs-lookup"><span data-stu-id="5f29b-259">PrependAndAccept</span></span>

<span data-ttu-id="5f29b-260">Добавьте в начало "#" и примите строку.</span><span class="sxs-lookup"><span data-stu-id="5f29b-260">Prepend a '#' and accept the line.</span></span>

- <span data-ttu-id="5f29b-261">Режим команд VI: `<#>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-261">Vi command mode: `<#>`</span></span>

### <a name="redo"></a><span data-ttu-id="5f29b-262">Повторить</span><span class="sxs-lookup"><span data-stu-id="5f29b-262">Redo</span></span>

<span data-ttu-id="5f29b-263">Отмена отмены.</span><span class="sxs-lookup"><span data-stu-id="5f29b-263">Undo an undo.</span></span>

- <span data-ttu-id="5f29b-264">Процессор `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-264">Cmd: `<Ctrl+y>`</span></span>
- <span data-ttu-id="5f29b-265">Режим вставки в VI: `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-265">Vi insert mode: `<Ctrl+y>`</span></span>
- <span data-ttu-id="5f29b-266">Режим команд VI: `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-266">Vi command mode: `<Ctrl+y>`</span></span>

### <a name="repeatlastcommand"></a><span data-ttu-id="5f29b-267">репеатласткомманд</span><span class="sxs-lookup"><span data-stu-id="5f29b-267">RepeatLastCommand</span></span>

<span data-ttu-id="5f29b-268">Повторите Последнее изменение текста.</span><span class="sxs-lookup"><span data-stu-id="5f29b-268">Repeat the last text modification.</span></span>

- <span data-ttu-id="5f29b-269">Режим команд VI: `<.>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-269">Vi command mode: `<.>`</span></span>

### <a name="revertline"></a><span data-ttu-id="5f29b-270">ревертлине</span><span class="sxs-lookup"><span data-stu-id="5f29b-270">RevertLine</span></span>

<span data-ttu-id="5f29b-271">Меняет все входные данные на текущие входные данные.</span><span class="sxs-lookup"><span data-stu-id="5f29b-271">Reverts all of the input to the current input.</span></span>

- <span data-ttu-id="5f29b-272">Процессор `<Escape>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-272">Cmd: `<Escape>`</span></span>
- <span data-ttu-id="5f29b-273">Emacs: `<Alt+r>` , `<Escape,r>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-273">Emacs: `<Alt+r>`, `<Escape,r>`</span></span>

### <a name="shellbackwardkillword"></a><span data-ttu-id="5f29b-274">шеллбакквардкиллворд</span><span class="sxs-lookup"><span data-stu-id="5f29b-274">ShellBackwardKillWord</span></span>

<span data-ttu-id="5f29b-275">Очистить ввод от начала текущего слова до курсора.</span><span class="sxs-lookup"><span data-stu-id="5f29b-275">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="5f29b-276">Если курсор находится между словами, входные данные очищаются от начала предыдущего слова до курсора.</span><span class="sxs-lookup"><span data-stu-id="5f29b-276">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="5f29b-277">Очистка текста помещается в буфер Kill.</span><span class="sxs-lookup"><span data-stu-id="5f29b-277">The cleared text is placed in the kill-ring.</span></span>

<span data-ttu-id="5f29b-278">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="5f29b-278">Function is unbound.</span></span>

### <a name="shellkillword"></a><span data-ttu-id="5f29b-279">шеллкиллворд</span><span class="sxs-lookup"><span data-stu-id="5f29b-279">ShellKillWord</span></span>

<span data-ttu-id="5f29b-280">Очистить ввод от курсора до конца текущего слова.</span><span class="sxs-lookup"><span data-stu-id="5f29b-280">Clear the input from the cursor to the end of the current word.</span></span> <span data-ttu-id="5f29b-281">Если курсор находится между словами, входные данные очищаются от курсора до конца следующего слова.</span><span class="sxs-lookup"><span data-stu-id="5f29b-281">If the cursor is between words, the input is cleared from the cursor to the end of the next word.</span></span> <span data-ttu-id="5f29b-282">Очистка текста помещается в буфер Kill.</span><span class="sxs-lookup"><span data-stu-id="5f29b-282">The cleared text is placed in the kill-ring.</span></span>

<span data-ttu-id="5f29b-283">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="5f29b-283">Function is unbound.</span></span>

### <a name="swapcharacters"></a><span data-ttu-id="5f29b-284">свапчарактерс</span><span class="sxs-lookup"><span data-stu-id="5f29b-284">SwapCharacters</span></span>

<span data-ttu-id="5f29b-285">Поменять местами текущий и тот же символ.</span><span class="sxs-lookup"><span data-stu-id="5f29b-285">Swap the current character and the one before it.</span></span>

- <span data-ttu-id="5f29b-286">Emacs: `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-286">Emacs: `<Ctrl+t>`</span></span>
- <span data-ttu-id="5f29b-287">Режим вставки в VI: `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-287">Vi insert mode: `<Ctrl+t>`</span></span>
- <span data-ttu-id="5f29b-288">Режим команд VI: `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-288">Vi command mode: `<Ctrl+t>`</span></span>

### <a name="undo"></a><span data-ttu-id="5f29b-289">Отменить</span><span class="sxs-lookup"><span data-stu-id="5f29b-289">Undo</span></span>

<span data-ttu-id="5f29b-290">Отмена предыдущего изменения.</span><span class="sxs-lookup"><span data-stu-id="5f29b-290">Undo a previous edit.</span></span>

- <span data-ttu-id="5f29b-291">Процессор `<Ctrl+z>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-291">Cmd: `<Ctrl+z>`</span></span>
- <span data-ttu-id="5f29b-292">Emacs: `<Ctrl+_>` , `<Ctrl+x,Ctrl+u>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-292">Emacs: `<Ctrl+_>`, `<Ctrl+x,Ctrl+u>`</span></span>
- <span data-ttu-id="5f29b-293">Режим вставки в VI: `<Ctrl+z>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-293">Vi insert mode: `<Ctrl+z>`</span></span>
- <span data-ttu-id="5f29b-294">Режим команд VI: `<Ctrl+z>` , `<u>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-294">Vi command mode: `<Ctrl+z>`, `<u>`</span></span>

### <a name="undoall"></a><span data-ttu-id="5f29b-295">ундоалл</span><span class="sxs-lookup"><span data-stu-id="5f29b-295">UndoAll</span></span>

<span data-ttu-id="5f29b-296">Отмена всех предыдущих изменений для строки.</span><span class="sxs-lookup"><span data-stu-id="5f29b-296">Undo all previous edits for line.</span></span>

- <span data-ttu-id="5f29b-297">Режим команд VI: `<U>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-297">Vi command mode: `<U>`</span></span>

### <a name="unixwordrubout"></a><span data-ttu-id="5f29b-298">униксвордрубаут</span><span class="sxs-lookup"><span data-stu-id="5f29b-298">UnixWordRubout</span></span>

<span data-ttu-id="5f29b-299">Очистить ввод от начала текущего слова до курсора.</span><span class="sxs-lookup"><span data-stu-id="5f29b-299">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="5f29b-300">Если курсор находится между словами, входные данные очищаются от начала предыдущего слова до курсора.</span><span class="sxs-lookup"><span data-stu-id="5f29b-300">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="5f29b-301">Очистка текста помещается в буфер Kill.</span><span class="sxs-lookup"><span data-stu-id="5f29b-301">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="5f29b-302">Emacs: `<Ctrl+w>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-302">Emacs: `<Ctrl+w>`</span></span>

### <a name="validateandacceptline"></a><span data-ttu-id="5f29b-303">валидатеандакцептлине</span><span class="sxs-lookup"><span data-stu-id="5f29b-303">ValidateAndAcceptLine</span></span>

<span data-ttu-id="5f29b-304">Попытка выполнить текущий вход.</span><span class="sxs-lookup"><span data-stu-id="5f29b-304">Attempt to execute the current input.</span></span> <span data-ttu-id="5f29b-305">Если текущий ввод неполон (например, отсутствует закрывающая круглая скобка, квадратная скобка или кавычка, запрос продолжения отображается на следующей строке, а PSReadLine ожидает ввода ключей для изменения текущих входных данных.</span><span class="sxs-lookup"><span data-stu-id="5f29b-305">If the current input is incomplete (for example there is a missing closing parenthesis, bracket, or quote, then the continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span>

- <span data-ttu-id="5f29b-306">Emacs: `<Ctrl+m>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-306">Emacs: `<Ctrl+m>`</span></span>

### <a name="viacceptline"></a><span data-ttu-id="5f29b-307">виакцептлине</span><span class="sxs-lookup"><span data-stu-id="5f29b-307">ViAcceptLine</span></span>

<span data-ttu-id="5f29b-308">Примите строку и переключитесь в режим вставки.</span><span class="sxs-lookup"><span data-stu-id="5f29b-308">Accept the line and switch to Insert mode.</span></span>

- <span data-ttu-id="5f29b-309">Режим команд VI: `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-309">Vi command mode: `<Enter>`</span></span>

### <a name="viacceptlineorexit"></a><span data-ttu-id="5f29b-310">виакцептлинеорексит</span><span class="sxs-lookup"><span data-stu-id="5f29b-310">ViAcceptLineOrExit</span></span>

<span data-ttu-id="5f29b-311">Как и Делетечарорексит в режиме Emacs, но принимает строку вместо удаления символа.</span><span class="sxs-lookup"><span data-stu-id="5f29b-311">Like DeleteCharOrExit in Emacs mode, but accepts the line instead of deleting a character.</span></span>

- <span data-ttu-id="5f29b-312">Режим вставки в VI: `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-312">Vi insert mode: `<Ctrl+d>`</span></span>
- <span data-ttu-id="5f29b-313">Режим команд VI: `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-313">Vi command mode: `<Ctrl+d>`</span></span>

### <a name="viappendline"></a><span data-ttu-id="5f29b-314">виаппендлине</span><span class="sxs-lookup"><span data-stu-id="5f29b-314">ViAppendLine</span></span>

<span data-ttu-id="5f29b-315">Новая строка вставляется под текущей строкой.</span><span class="sxs-lookup"><span data-stu-id="5f29b-315">A new line is inserted below the current line.</span></span>

- <span data-ttu-id="5f29b-316">Режим команд VI: `<o>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-316">Vi command mode: `<o>`</span></span>

### <a name="vibackwarddeleteglob"></a><span data-ttu-id="5f29b-317">вибакквардделетеглоб</span><span class="sxs-lookup"><span data-stu-id="5f29b-317">ViBackwardDeleteGlob</span></span>

<span data-ttu-id="5f29b-318">Удаляет предыдущее слово, используя только пробелы в качестве разделителя слов.</span><span class="sxs-lookup"><span data-stu-id="5f29b-318">Deletes the previous word, using only white space as the word delimiter.</span></span>

- <span data-ttu-id="5f29b-319">Режим команд VI: `<d,B>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-319">Vi command mode: `<d,B>`</span></span>

### <a name="vibackwardglob"></a><span data-ttu-id="5f29b-320">вибакквардглоб</span><span class="sxs-lookup"><span data-stu-id="5f29b-320">ViBackwardGlob</span></span>

<span data-ttu-id="5f29b-321">Перемещает курсор назад к началу предыдущего слова, используя только пробелы в качестве разделителей.</span><span class="sxs-lookup"><span data-stu-id="5f29b-321">Moves the cursor back to the beginning of the previous word, using only white space as delimiters.</span></span>

- <span data-ttu-id="5f29b-322">Режим команд VI: `<B>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-322">Vi command mode: `<B>`</span></span>

### <a name="videletebrace"></a><span data-ttu-id="5f29b-323">виделетебраце</span><span class="sxs-lookup"><span data-stu-id="5f29b-323">ViDeleteBrace</span></span>

<span data-ttu-id="5f29b-324">Найдите парную фигурную скобку, круглую скобку или квадратную скобку и удалите все содержимое внутри, включая фигурную скобку.</span><span class="sxs-lookup"><span data-stu-id="5f29b-324">Find the matching brace, parenthesis, or square bracket and delete all contents within, including the brace.</span></span>

- <span data-ttu-id="5f29b-325">Режим команд VI: `<d,%>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-325">Vi command mode: `<d,%>`</span></span>

### <a name="videleteendofglob"></a><span data-ttu-id="5f29b-326">виделетиндофглоб</span><span class="sxs-lookup"><span data-stu-id="5f29b-326">ViDeleteEndOfGlob</span></span>

<span data-ttu-id="5f29b-327">Удалить до конца слова.</span><span class="sxs-lookup"><span data-stu-id="5f29b-327">Delete to the end of the word.</span></span>

- <span data-ttu-id="5f29b-328">Режим команд VI: `<d,E>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-328">Vi command mode: `<d,E>`</span></span>

### <a name="videleteglob"></a><span data-ttu-id="5f29b-329">виделетеглоб</span><span class="sxs-lookup"><span data-stu-id="5f29b-329">ViDeleteGlob</span></span>

<span data-ttu-id="5f29b-330">Удалите следующий стандартная маска (слово, разделенное пробелами).</span><span class="sxs-lookup"><span data-stu-id="5f29b-330">Delete the next glob (white space delimited word).</span></span>

- <span data-ttu-id="5f29b-331">Режим команд VI: `<d,W>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-331">Vi command mode: `<d,W>`</span></span>

### <a name="videletetobeforechar"></a><span data-ttu-id="5f29b-332">виделететобефоречар</span><span class="sxs-lookup"><span data-stu-id="5f29b-332">ViDeleteToBeforeChar</span></span>

<span data-ttu-id="5f29b-333">Удаляет до заданного символа.</span><span class="sxs-lookup"><span data-stu-id="5f29b-333">Deletes until given character.</span></span>

- <span data-ttu-id="5f29b-334">Режим команд VI: `<d,t>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-334">Vi command mode: `<d,t>`</span></span>

### <a name="videletetobeforecharbackward"></a><span data-ttu-id="5f29b-335">виделететобефоречарбакквард</span><span class="sxs-lookup"><span data-stu-id="5f29b-335">ViDeleteToBeforeCharBackward</span></span>

<span data-ttu-id="5f29b-336">Удаляет до заданного символа.</span><span class="sxs-lookup"><span data-stu-id="5f29b-336">Deletes until given character.</span></span>

- <span data-ttu-id="5f29b-337">Режим команд VI: `<d,T>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-337">Vi command mode: `<d,T>`</span></span>

### <a name="videletetochar"></a><span data-ttu-id="5f29b-338">виделететочар</span><span class="sxs-lookup"><span data-stu-id="5f29b-338">ViDeleteToChar</span></span>

<span data-ttu-id="5f29b-339">Удаляет до заданного символа.</span><span class="sxs-lookup"><span data-stu-id="5f29b-339">Deletes until given character.</span></span>

- <span data-ttu-id="5f29b-340">Режим команд VI: `<d,f>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-340">Vi command mode: `<d,f>`</span></span>

### <a name="videletetocharbackward"></a><span data-ttu-id="5f29b-341">виделететочарбакквард</span><span class="sxs-lookup"><span data-stu-id="5f29b-341">ViDeleteToCharBackward</span></span>

<span data-ttu-id="5f29b-342">Удаляет обратную сторону до заданного символа.</span><span class="sxs-lookup"><span data-stu-id="5f29b-342">Deletes backwards until given character.</span></span>

- <span data-ttu-id="5f29b-343">Режим команд VI: `<d,F>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-343">Vi command mode: `<d,F>`</span></span>

### <a name="viinsertatbegining"></a><span data-ttu-id="5f29b-344">виинсертатбегининг</span><span class="sxs-lookup"><span data-stu-id="5f29b-344">ViInsertAtBegining</span></span>

<span data-ttu-id="5f29b-345">Переключитесь в режим вставки и поместите курсор в начало строки.</span><span class="sxs-lookup"><span data-stu-id="5f29b-345">Switch to Insert mode and position the cursor at the beginning of the line.</span></span>

- <span data-ttu-id="5f29b-346">Режим команд VI: `<I>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-346">Vi command mode: `<I>`</span></span>

### <a name="viinsertatend"></a><span data-ttu-id="5f29b-347">виинсертатенд</span><span class="sxs-lookup"><span data-stu-id="5f29b-347">ViInsertAtEnd</span></span>

<span data-ttu-id="5f29b-348">Переключитесь в режим вставки и поместите курсор в конец строки.</span><span class="sxs-lookup"><span data-stu-id="5f29b-348">Switch to Insert mode and position the cursor at the end of the line.</span></span>

- <span data-ttu-id="5f29b-349">Режим команд VI: `<A>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-349">Vi command mode: `<A>`</span></span>

### <a name="viinsertline"></a><span data-ttu-id="5f29b-350">виинсертлине</span><span class="sxs-lookup"><span data-stu-id="5f29b-350">ViInsertLine</span></span>

<span data-ttu-id="5f29b-351">Новая строка вставляется над текущей строкой.</span><span class="sxs-lookup"><span data-stu-id="5f29b-351">A new line is inserted above the current line.</span></span>

- <span data-ttu-id="5f29b-352">Режим команд VI: `<O>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-352">Vi command mode: `<O>`</span></span>

### <a name="viinsertwithappend"></a><span data-ttu-id="5f29b-353">виинсертвисаппенд</span><span class="sxs-lookup"><span data-stu-id="5f29b-353">ViInsertWithAppend</span></span>

<span data-ttu-id="5f29b-354">Добавление из текущей позицией строки.</span><span class="sxs-lookup"><span data-stu-id="5f29b-354">Append from the current line position.</span></span>

- <span data-ttu-id="5f29b-355">Режим команд VI: `<a>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-355">Vi command mode: `<a>`</span></span>

### <a name="viinsertwithdelete"></a><span data-ttu-id="5f29b-356">виинсертвисделете</span><span class="sxs-lookup"><span data-stu-id="5f29b-356">ViInsertWithDelete</span></span>

<span data-ttu-id="5f29b-357">Удалите текущий символ и переключитесь в режим вставки.</span><span class="sxs-lookup"><span data-stu-id="5f29b-357">Delete the current character and switch to Insert mode.</span></span>

- <span data-ttu-id="5f29b-358">Режим команд VI: `<s>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-358">Vi command mode: `<s>`</span></span>

### <a name="vijoinlines"></a><span data-ttu-id="5f29b-359">вижоинлинес</span><span class="sxs-lookup"><span data-stu-id="5f29b-359">ViJoinLines</span></span>

<span data-ttu-id="5f29b-360">Объединяет текущую строку и следующую строку.</span><span class="sxs-lookup"><span data-stu-id="5f29b-360">Joins the current line and the next line.</span></span>

- <span data-ttu-id="5f29b-361">Режим команд VI: `<J>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-361">Vi command mode: `<J>`</span></span>

### <a name="vireplaceline"></a><span data-ttu-id="5f29b-362">виреплацелине</span><span class="sxs-lookup"><span data-stu-id="5f29b-362">ViReplaceLine</span></span>

<span data-ttu-id="5f29b-363">Очистить всю командную строку.</span><span class="sxs-lookup"><span data-stu-id="5f29b-363">Erase the entire command line.</span></span>

- <span data-ttu-id="5f29b-364">Режим команд VI: `<S>` , `<c,c>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-364">Vi command mode: `<S>`, `<c,c>`</span></span>

### <a name="vireplacetobeforechar"></a><span data-ttu-id="5f29b-365">виреплацетобефоречар</span><span class="sxs-lookup"><span data-stu-id="5f29b-365">ViReplaceToBeforeChar</span></span>

<span data-ttu-id="5f29b-366">Заменяет заданный символ.</span><span class="sxs-lookup"><span data-stu-id="5f29b-366">Replaces until given character.</span></span>

- <span data-ttu-id="5f29b-367">Режим команд VI: `<c,t>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-367">Vi command mode: `<c,t>`</span></span>

### <a name="vireplacetobeforecharbackward"></a><span data-ttu-id="5f29b-368">виреплацетобефоречарбакквард</span><span class="sxs-lookup"><span data-stu-id="5f29b-368">ViReplaceToBeforeCharBackward</span></span>

<span data-ttu-id="5f29b-369">Заменяет заданный символ.</span><span class="sxs-lookup"><span data-stu-id="5f29b-369">Replaces until given character.</span></span>

- <span data-ttu-id="5f29b-370">Режим команд VI: `<c,T>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-370">Vi command mode: `<c,T>`</span></span>

### <a name="vireplacetochar"></a><span data-ttu-id="5f29b-371">виреплацеточар</span><span class="sxs-lookup"><span data-stu-id="5f29b-371">ViReplaceToChar</span></span>

<span data-ttu-id="5f29b-372">Удаляет до заданного символа.</span><span class="sxs-lookup"><span data-stu-id="5f29b-372">Deletes until given character.</span></span>

- <span data-ttu-id="5f29b-373">Режим команд VI: `<c,f>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-373">Vi command mode: `<c,f>`</span></span>

### <a name="vireplacetocharbackward"></a><span data-ttu-id="5f29b-374">виреплацеточарбакквард</span><span class="sxs-lookup"><span data-stu-id="5f29b-374">ViReplaceToCharBackward</span></span>

<span data-ttu-id="5f29b-375">Заменяет заданный символ.</span><span class="sxs-lookup"><span data-stu-id="5f29b-375">Replaces until given character.</span></span>

- <span data-ttu-id="5f29b-376">Режим команд VI: `<c,F>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-376">Vi command mode: `<c,F>`</span></span>

### <a name="viyankbeginningofline"></a><span data-ttu-id="5f29b-377">вийанкбегиннингофлине</span><span class="sxs-lookup"><span data-stu-id="5f29b-377">ViYankBeginningOfLine</span></span>

<span data-ttu-id="5f29b-378">Янк от начала буфера до курсора.</span><span class="sxs-lookup"><span data-stu-id="5f29b-378">Yank from the beginning of the buffer to the cursor.</span></span>

- <span data-ttu-id="5f29b-379">Режим команд VI: `<y,0>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-379">Vi command mode: `<y,0>`</span></span>

### <a name="viyankendofglob"></a><span data-ttu-id="5f29b-380">вийанкендофглоб</span><span class="sxs-lookup"><span data-stu-id="5f29b-380">ViYankEndOfGlob</span></span>

<span data-ttu-id="5f29b-381">Янк от курсора до конца слова.</span><span class="sxs-lookup"><span data-stu-id="5f29b-381">Yank from the cursor to the end of the WORD(s).</span></span>

- <span data-ttu-id="5f29b-382">Режим команд VI: `<y,E>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-382">Vi command mode: `<y,E>`</span></span>

### <a name="viyankendofword"></a><span data-ttu-id="5f29b-383">вийанкендофворд</span><span class="sxs-lookup"><span data-stu-id="5f29b-383">ViYankEndOfWord</span></span>

<span data-ttu-id="5f29b-384">Янк от курсора до конца слова.</span><span class="sxs-lookup"><span data-stu-id="5f29b-384">Yank from the cursor to the end of the word(s).</span></span>

- <span data-ttu-id="5f29b-385">Режим команд VI: `<y,e>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-385">Vi command mode: `<y,e>`</span></span>

### <a name="viyankleft"></a><span data-ttu-id="5f29b-386">вийанклефт</span><span class="sxs-lookup"><span data-stu-id="5f29b-386">ViYankLeft</span></span>

<span data-ttu-id="5f29b-387">Янк символы слева от курсора.</span><span class="sxs-lookup"><span data-stu-id="5f29b-387">Yank character(s) to the left of the cursor.</span></span>

- <span data-ttu-id="5f29b-388">Режим команд VI: `<y,h>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-388">Vi command mode: `<y,h>`</span></span>

### <a name="viyankline"></a><span data-ttu-id="5f29b-389">вийанклине</span><span class="sxs-lookup"><span data-stu-id="5f29b-389">ViYankLine</span></span>

<span data-ttu-id="5f29b-390">Янк весь буфер.</span><span class="sxs-lookup"><span data-stu-id="5f29b-390">Yank the entire buffer.</span></span>

- <span data-ttu-id="5f29b-391">Режим команд VI: `<y,y>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-391">Vi command mode: `<y,y>`</span></span>

### <a name="viyanknextglob"></a><span data-ttu-id="5f29b-392">вийанкнекстглоб</span><span class="sxs-lookup"><span data-stu-id="5f29b-392">ViYankNextGlob</span></span>

<span data-ttu-id="5f29b-393">Янк от курсора до начала следующего слова.</span><span class="sxs-lookup"><span data-stu-id="5f29b-393">Yank from cursor to the start of the next WORD(s).</span></span>

- <span data-ttu-id="5f29b-394">Режим команд VI: `<y,W>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-394">Vi command mode: `<y,W>`</span></span>

### <a name="viyanknextword"></a><span data-ttu-id="5f29b-395">вийанкнекстворд</span><span class="sxs-lookup"><span data-stu-id="5f29b-395">ViYankNextWord</span></span>

<span data-ttu-id="5f29b-396">Янк слова после курсора.</span><span class="sxs-lookup"><span data-stu-id="5f29b-396">Yank the word(s) after the cursor.</span></span>

- <span data-ttu-id="5f29b-397">Режим команд VI: `<y,w>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-397">Vi command mode: `<y,w>`</span></span>

### <a name="viyankpercent"></a><span data-ttu-id="5f29b-398">вийанкперцент</span><span class="sxs-lookup"><span data-stu-id="5f29b-398">ViYankPercent</span></span>

<span data-ttu-id="5f29b-399">Янк в парную фигурную скобку.</span><span class="sxs-lookup"><span data-stu-id="5f29b-399">Yank to/from matching brace.</span></span>

- <span data-ttu-id="5f29b-400">Режим команд VI: `<y,%>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-400">Vi command mode: `<y,%>`</span></span>

### <a name="viyankpreviousglob"></a><span data-ttu-id="5f29b-401">вийанкпревиаусглоб</span><span class="sxs-lookup"><span data-stu-id="5f29b-401">ViYankPreviousGlob</span></span>

<span data-ttu-id="5f29b-402">Янк от начала слов до курсора.</span><span class="sxs-lookup"><span data-stu-id="5f29b-402">Yank from beginning of the WORD(s) to cursor.</span></span>

- <span data-ttu-id="5f29b-403">Режим команд VI: `<y,B>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-403">Vi command mode: `<y,B>`</span></span>

### <a name="viyankpreviousword"></a><span data-ttu-id="5f29b-404">вийанкпревиаусворд</span><span class="sxs-lookup"><span data-stu-id="5f29b-404">ViYankPreviousWord</span></span>

<span data-ttu-id="5f29b-405">Янк слова перед курсором.</span><span class="sxs-lookup"><span data-stu-id="5f29b-405">Yank the word(s) before the cursor.</span></span>

- <span data-ttu-id="5f29b-406">Режим команд VI: `<y,b>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-406">Vi command mode: `<y,b>`</span></span>

### <a name="viyankright"></a><span data-ttu-id="5f29b-407">вийанкригхт</span><span class="sxs-lookup"><span data-stu-id="5f29b-407">ViYankRight</span></span>

<span data-ttu-id="5f29b-408">Янк символы в положении и справа от курсора.</span><span class="sxs-lookup"><span data-stu-id="5f29b-408">Yank character(s) under and to the right of the cursor.</span></span>

- <span data-ttu-id="5f29b-409">Режим команд VI: `<y,l>` , `<y,Space>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-409">Vi command mode: `<y,l>`, `<y,Space>`</span></span>

### <a name="viyanktoendofline"></a><span data-ttu-id="5f29b-410">вийанктоендофлине</span><span class="sxs-lookup"><span data-stu-id="5f29b-410">ViYankToEndOfLine</span></span>

<span data-ttu-id="5f29b-411">Янк от курсора до конца буфера.</span><span class="sxs-lookup"><span data-stu-id="5f29b-411">Yank from the cursor to the end of the buffer.</span></span>

- <span data-ttu-id="5f29b-412">Режим команд VI: `<y,$>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-412">Vi command mode: `<y,$>`</span></span>

### <a name="viyanktofirstchar"></a><span data-ttu-id="5f29b-413">вийанктофирстчар</span><span class="sxs-lookup"><span data-stu-id="5f29b-413">ViYankToFirstChar</span></span>

<span data-ttu-id="5f29b-414">Янк от первого символа, отличного от пробела, к курсору.</span><span class="sxs-lookup"><span data-stu-id="5f29b-414">Yank from the first non-whitespace character to the cursor.</span></span>

- <span data-ttu-id="5f29b-415">Режим команд VI: `<y,^>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-415">Vi command mode: `<y,^>`</span></span>

### <a name="yank"></a><span data-ttu-id="5f29b-416">янк</span><span class="sxs-lookup"><span data-stu-id="5f29b-416">Yank</span></span>

<span data-ttu-id="5f29b-417">Добавление последнего недавнего текста во входные данные.</span><span class="sxs-lookup"><span data-stu-id="5f29b-417">Add the most recently killed text to the input.</span></span>

- <span data-ttu-id="5f29b-418">Emacs: `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-418">Emacs: `<Ctrl+y>`</span></span>

### <a name="yanklastarg"></a><span data-ttu-id="5f29b-419">янкластарг</span><span class="sxs-lookup"><span data-stu-id="5f29b-419">YankLastArg</span></span>

<span data-ttu-id="5f29b-420">Янк последний аргумент из предыдущей строки журнала.</span><span class="sxs-lookup"><span data-stu-id="5f29b-420">Yank the last argument from the previous history line.</span></span> <span data-ttu-id="5f29b-421">С аргументом при первом вызове он ведет себя так же, как Янкнсарг.</span><span class="sxs-lookup"><span data-stu-id="5f29b-421">With an argument, the first time it is invoked, behaves just like YankNthArg.</span></span> <span data-ttu-id="5f29b-422">Если вызывается несколько раз, вместо этого выполняется итерация по журналу, а аргумент устанавливает направление (отрицательно меняет направление на противоположное).</span><span class="sxs-lookup"><span data-stu-id="5f29b-422">If invoked multiple times, instead it iterates through history and arg sets the direction (negative reverses the direction.)</span></span>

- <span data-ttu-id="5f29b-423">Процессор `<Alt+.>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-423">Cmd: `<Alt+.>`</span></span>
- <span data-ttu-id="5f29b-424">Emacs: `<Alt+.>` , `<Alt+_>` , `<Escape,.>` , `<Escape,_>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-424">Emacs: `<Alt+.>`, `<Alt+_>`, `<Escape,.>`, `<Escape,_>`</span></span>

### <a name="yankntharg"></a><span data-ttu-id="5f29b-425">янкнсарг</span><span class="sxs-lookup"><span data-stu-id="5f29b-425">YankNthArg</span></span>

<span data-ttu-id="5f29b-426">Янк первый аргумент (после команды) из предыдущей строки журнала.</span><span class="sxs-lookup"><span data-stu-id="5f29b-426">Yank the first argument (after the command) from the previous history line.</span></span>
<span data-ttu-id="5f29b-427">При использовании аргумента Янк аргумент n (начиная с 0), если аргумент является отрицательным, начните с последнего аргумента.</span><span class="sxs-lookup"><span data-stu-id="5f29b-427">With an argument, yank the nth argument (starting from 0), if the argument is negative, start from the last argument.</span></span>

- <span data-ttu-id="5f29b-428">Emacs: `<Ctrl+Alt+y>` , `<Escape,Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-428">Emacs: `<Ctrl+Alt+y>`, `<Escape,Ctrl+y>`</span></span>

### <a name="yankpop"></a><span data-ttu-id="5f29b-429">янкпоп</span><span class="sxs-lookup"><span data-stu-id="5f29b-429">YankPop</span></span>

<span data-ttu-id="5f29b-430">Если предыдущая операция была Янк или Янкпоп, замените ранее янкед текст следующим уничтоженным текстом из Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="5f29b-430">If the previous operation was Yank or YankPop, replace the previously yanked text with the next killed text from the kill-ring.</span></span>

- <span data-ttu-id="5f29b-431">Emacs: `<Alt+y>` , `<Escape,y>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-431">Emacs: `<Alt+y>`, `<Escape,y>`</span></span>

## <a name="cursor-movement-functions"></a><span data-ttu-id="5f29b-432">Функции перемещения курсора</span><span class="sxs-lookup"><span data-stu-id="5f29b-432">Cursor movement functions</span></span>

### <a name="backwardchar"></a><span data-ttu-id="5f29b-433">бакквардчар</span><span class="sxs-lookup"><span data-stu-id="5f29b-433">BackwardChar</span></span>

<span data-ttu-id="5f29b-434">Переместить курсор на один символ влево.</span><span class="sxs-lookup"><span data-stu-id="5f29b-434">Move the cursor one character to the left.</span></span> <span data-ttu-id="5f29b-435">Это может переместить курсор к предыдущей строке многострочного ввода.</span><span class="sxs-lookup"><span data-stu-id="5f29b-435">This may move the cursor to the previous line of multi-line input.</span></span>

- <span data-ttu-id="5f29b-436">Процессор `<LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-436">Cmd: `<LeftArrow>`</span></span>
- <span data-ttu-id="5f29b-437">Emacs: `<LeftArrow>` , `<Ctrl+b>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-437">Emacs: `<LeftArrow>`, `<Ctrl+b>`</span></span>
- <span data-ttu-id="5f29b-438">Режим вставки в VI: `<LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-438">Vi insert mode: `<LeftArrow>`</span></span>
- <span data-ttu-id="5f29b-439">Режим команд VI: `<LeftArrow>` , `<Backspace>` , `<h>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-439">Vi command mode: `<LeftArrow>`, `<Backspace>`, `<h>`</span></span>

### <a name="backwardword"></a><span data-ttu-id="5f29b-440">бакквардворд</span><span class="sxs-lookup"><span data-stu-id="5f29b-440">BackwardWord</span></span>

<span data-ttu-id="5f29b-441">Перемещение курсора назад к началу текущего слова или между словами, с начала предыдущего слова.</span><span class="sxs-lookup"><span data-stu-id="5f29b-441">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="5f29b-442">Границы слов определяются с помощью настраиваемого набора символов.</span><span class="sxs-lookup"><span data-stu-id="5f29b-442">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="5f29b-443">Процессор `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-443">Cmd: `<Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="5f29b-444">Emacs: `<Alt+b>` , `<Escape,b>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-444">Emacs: `<Alt+b>`, `<Escape,b>`</span></span>
- <span data-ttu-id="5f29b-445">Режим вставки в VI: `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-445">Vi insert mode: `<Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="5f29b-446">Режим команд VI: `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-446">Vi command mode: `<Ctrl+LeftArrow>`</span></span>

### <a name="beginningofline"></a><span data-ttu-id="5f29b-447">бегиннингофлине</span><span class="sxs-lookup"><span data-stu-id="5f29b-447">BeginningOfLine</span></span>

<span data-ttu-id="5f29b-448">Если входные данные имеют несколько строк, переместитесь в начало текущей строки или, если они уже находятся в начале строки, перейдите к началу входного элемента.</span><span class="sxs-lookup"><span data-stu-id="5f29b-448">If the input has multiple lines, move to the start of the current line, or if already at the start of the line, move to the start of the input.</span></span> <span data-ttu-id="5f29b-449">Если входные данные имеют одну строку, переходите к началу входных данных.</span><span class="sxs-lookup"><span data-stu-id="5f29b-449">If the input has a single line, move to the start of the input.</span></span>

- <span data-ttu-id="5f29b-450">Процессор `<Home>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-450">Cmd: `<Home>`</span></span>
- <span data-ttu-id="5f29b-451">Emacs: `<Home>` , `<Ctrl+a>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-451">Emacs: `<Home>`, `<Ctrl+a>`</span></span>
- <span data-ttu-id="5f29b-452">Режим вставки в VI: `<Home>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-452">Vi insert mode: `<Home>`</span></span>
- <span data-ttu-id="5f29b-453">Режим команд VI: `<Home>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-453">Vi command mode: `<Home>`</span></span>

### <a name="endofline"></a><span data-ttu-id="5f29b-454">ендофлине</span><span class="sxs-lookup"><span data-stu-id="5f29b-454">EndOfLine</span></span>

<span data-ttu-id="5f29b-455">Если входные данные имеют несколько строк, переместитесь в конец текущей строки или, если они уже находятся в конце строки, перейдите к концу входных данных.</span><span class="sxs-lookup"><span data-stu-id="5f29b-455">If the input has multiple lines, move to the end of the current line, or if already at the end of the line, move to the end of the input.</span></span> <span data-ttu-id="5f29b-456">Если входные данные имеют одну строку, переходите к концу входных данных.</span><span class="sxs-lookup"><span data-stu-id="5f29b-456">If the input has a single line, move to the end of the input.</span></span>

- <span data-ttu-id="5f29b-457">Процессор `<End>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-457">Cmd: `<End>`</span></span>
- <span data-ttu-id="5f29b-458">Emacs: `<End>` , `<Ctrl+e>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-458">Emacs: `<End>`, `<Ctrl+e>`</span></span>
- <span data-ttu-id="5f29b-459">Режим вставки в VI: `<End>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-459">Vi insert mode: `<End>`</span></span>

### <a name="forwardchar"></a><span data-ttu-id="5f29b-460">форвардчар</span><span class="sxs-lookup"><span data-stu-id="5f29b-460">ForwardChar</span></span>

<span data-ttu-id="5f29b-461">Переместить курсор на один символ вправо.</span><span class="sxs-lookup"><span data-stu-id="5f29b-461">Move the cursor one character to the right.</span></span> <span data-ttu-id="5f29b-462">Это может переместить курсор на следующую строку многострочного ввода.</span><span class="sxs-lookup"><span data-stu-id="5f29b-462">This may move the cursor to the next line of multi-line input.</span></span>

- <span data-ttu-id="5f29b-463">Процессор `<RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-463">Cmd: `<RightArrow>`</span></span>
- <span data-ttu-id="5f29b-464">Emacs: `<RightArrow>` , `<Ctrl+f>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-464">Emacs: `<RightArrow>`, `<Ctrl+f>`</span></span>
- <span data-ttu-id="5f29b-465">Режим вставки в VI: `<RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-465">Vi insert mode: `<RightArrow>`</span></span>
- <span data-ttu-id="5f29b-466">Режим команд VI: `<RightArrow>` , `<Space>` , `<l>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-466">Vi command mode: `<RightArrow>`, `<Space>`, `<l>`</span></span>

### <a name="forwardword"></a><span data-ttu-id="5f29b-467">форвардворд</span><span class="sxs-lookup"><span data-stu-id="5f29b-467">ForwardWord</span></span>

<span data-ttu-id="5f29b-468">Переместить курсор вперед к концу текущего слова или между словами, до конца следующего слова.</span><span class="sxs-lookup"><span data-stu-id="5f29b-468">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="5f29b-469">Границы слов определяются с помощью настраиваемого набора символов.</span><span class="sxs-lookup"><span data-stu-id="5f29b-469">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="5f29b-470">Emacs: `<Alt+f>` , `<Escape,f>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-470">Emacs: `<Alt+f>`, `<Escape,f>`</span></span>

### <a name="gotobrace"></a><span data-ttu-id="5f29b-471">GotoBrace</span><span class="sxs-lookup"><span data-stu-id="5f29b-471">GotoBrace</span></span>

<span data-ttu-id="5f29b-472">Перейдите к парной фигурной скобке, круглой скобке или квадратной скобке.</span><span class="sxs-lookup"><span data-stu-id="5f29b-472">Go to the matching brace, parenthesis, or square bracket.</span></span>

- <span data-ttu-id="5f29b-473">Процессор `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-473">Cmd: `<Ctrl+]>`</span></span>
- <span data-ttu-id="5f29b-474">Режим вставки в VI: `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-474">Vi insert mode: `<Ctrl+]>`</span></span>
- <span data-ttu-id="5f29b-475">Режим команд VI: `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-475">Vi command mode: `<Ctrl+]>`</span></span>

### <a name="gotocolumn"></a><span data-ttu-id="5f29b-476">готоколумн</span><span class="sxs-lookup"><span data-stu-id="5f29b-476">GotoColumn</span></span>

<span data-ttu-id="5f29b-477">Переход к столбцу, указанному аргументом arg.</span><span class="sxs-lookup"><span data-stu-id="5f29b-477">Move to the column indicated by arg.</span></span>

- <span data-ttu-id="5f29b-478">Режим команд VI: `<|>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-478">Vi command mode: `<|>`</span></span>

### <a name="gotofirstnonblankofline"></a><span data-ttu-id="5f29b-479">готофирстнонбланкофлине</span><span class="sxs-lookup"><span data-stu-id="5f29b-479">GotoFirstNonBlankOfLine</span></span>

<span data-ttu-id="5f29b-480">Переместить курсор к первому непустому символу в строке.</span><span class="sxs-lookup"><span data-stu-id="5f29b-480">Move the cursor to the first non-blank character in the line.</span></span>

- <span data-ttu-id="5f29b-481">Режим команд VI: `<^>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-481">Vi command mode: `<^>`</span></span>

### <a name="movetoendofline"></a><span data-ttu-id="5f29b-482">моветоендофлине</span><span class="sxs-lookup"><span data-stu-id="5f29b-482">MoveToEndOfLine</span></span>

<span data-ttu-id="5f29b-483">Переместить курсор в конец входных данных.</span><span class="sxs-lookup"><span data-stu-id="5f29b-483">Move the cursor to the end of the input.</span></span>

- <span data-ttu-id="5f29b-484">Режим команд VI: `<End>` , `<$>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-484">Vi command mode: `<End>`, `<$>`</span></span>

### <a name="nextline"></a><span data-ttu-id="5f29b-485">некстлине</span><span class="sxs-lookup"><span data-stu-id="5f29b-485">NextLine</span></span>

<span data-ttu-id="5f29b-486">Переместить курсор на следующую строку.</span><span class="sxs-lookup"><span data-stu-id="5f29b-486">Move the cursor to the next line.</span></span>

- <span data-ttu-id="5f29b-487">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="5f29b-487">Function is unbound.</span></span>

### <a name="nextword"></a><span data-ttu-id="5f29b-488">некстворд</span><span class="sxs-lookup"><span data-stu-id="5f29b-488">NextWord</span></span>

<span data-ttu-id="5f29b-489">Переместить курсор вперед к началу следующего слова.</span><span class="sxs-lookup"><span data-stu-id="5f29b-489">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="5f29b-490">Границы слов определяются с помощью настраиваемого набора символов.</span><span class="sxs-lookup"><span data-stu-id="5f29b-490">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="5f29b-491">Процессор `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-491">Cmd: `<Ctrl+RightArrow>`</span></span>
- <span data-ttu-id="5f29b-492">Режим вставки в VI: `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-492">Vi insert mode: `<Ctrl+RightArrow>`</span></span>
- <span data-ttu-id="5f29b-493">Режим команд VI: `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-493">Vi command mode: `<Ctrl+RightArrow>`</span></span>

### <a name="nextwordend"></a><span data-ttu-id="5f29b-494">некстворденд</span><span class="sxs-lookup"><span data-stu-id="5f29b-494">NextWordEnd</span></span>

<span data-ttu-id="5f29b-495">Переместить курсор вперед к концу текущего слова или между словами, до конца следующего слова.</span><span class="sxs-lookup"><span data-stu-id="5f29b-495">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="5f29b-496">Границы слов определяются с помощью настраиваемого набора символов.</span><span class="sxs-lookup"><span data-stu-id="5f29b-496">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="5f29b-497">Режим команд VI: `<e>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-497">Vi command mode: `<e>`</span></span>

### <a name="previousline"></a><span data-ttu-id="5f29b-498">превиауслине</span><span class="sxs-lookup"><span data-stu-id="5f29b-498">PreviousLine</span></span>

<span data-ttu-id="5f29b-499">Переместить курсор на предыдущую строку.</span><span class="sxs-lookup"><span data-stu-id="5f29b-499">Move the cursor to the previous line.</span></span>

- <span data-ttu-id="5f29b-500">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="5f29b-500">Function is unbound.</span></span>

### <a name="shellbackwardword"></a><span data-ttu-id="5f29b-501">шеллбакквардворд</span><span class="sxs-lookup"><span data-stu-id="5f29b-501">ShellBackwardWord</span></span>

<span data-ttu-id="5f29b-502">Перемещение курсора назад к началу текущего слова или между словами, с начала предыдущего слова.</span><span class="sxs-lookup"><span data-stu-id="5f29b-502">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="5f29b-503">Границы слов определяются токенами PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5f29b-503">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="5f29b-504">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="5f29b-504">Function is unbound.</span></span>

### <a name="shellforwardword"></a><span data-ttu-id="5f29b-505">шеллфорвардворд</span><span class="sxs-lookup"><span data-stu-id="5f29b-505">ShellForwardWord</span></span>

<span data-ttu-id="5f29b-506">Переместить курсор вперед к началу следующего слова.</span><span class="sxs-lookup"><span data-stu-id="5f29b-506">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="5f29b-507">Границы слов определяются токенами PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5f29b-507">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="5f29b-508">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="5f29b-508">Function is unbound.</span></span>

### <a name="shellnextword"></a><span data-ttu-id="5f29b-509">шеллнекстворд</span><span class="sxs-lookup"><span data-stu-id="5f29b-509">ShellNextWord</span></span>

<span data-ttu-id="5f29b-510">Переместить курсор вперед к концу текущего слова или между словами, до конца следующего слова.</span><span class="sxs-lookup"><span data-stu-id="5f29b-510">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="5f29b-511">Границы слов определяются токенами PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5f29b-511">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="5f29b-512">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="5f29b-512">Function is unbound.</span></span>

### <a name="vibackwardword"></a><span data-ttu-id="5f29b-513">вибакквардворд</span><span class="sxs-lookup"><span data-stu-id="5f29b-513">ViBackwardWord</span></span>

<span data-ttu-id="5f29b-514">Перемещение курсора назад к началу текущего слова или между словами, с начала предыдущего слова.</span><span class="sxs-lookup"><span data-stu-id="5f29b-514">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="5f29b-515">Границы слов определяются с помощью настраиваемого набора символов.</span><span class="sxs-lookup"><span data-stu-id="5f29b-515">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="5f29b-516">Режим команд VI: `<b>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-516">Vi command mode: `<b>`</span></span>

### <a name="viendofglob"></a><span data-ttu-id="5f29b-517">виендофглоб</span><span class="sxs-lookup"><span data-stu-id="5f29b-517">ViEndOfGlob</span></span>

<span data-ttu-id="5f29b-518">Перемещает курсор в конец слова, используя только пробелы в качестве разделителей.</span><span class="sxs-lookup"><span data-stu-id="5f29b-518">Moves the cursor to the end of the word, using only white space as delimiters.</span></span>

- <span data-ttu-id="5f29b-519">Режим команд VI: `<E>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-519">Vi command mode: `<E>`</span></span>

### <a name="viendofpreviousglob"></a><span data-ttu-id="5f29b-520">виендофпревиаусглоб</span><span class="sxs-lookup"><span data-stu-id="5f29b-520">ViEndOfPreviousGlob</span></span>

<span data-ttu-id="5f29b-521">Переход к концу предыдущего слова с использованием только пробелов в качестве разделителя слов.</span><span class="sxs-lookup"><span data-stu-id="5f29b-521">Moves to the end of the previous word, using only white space as a word delimiter.</span></span>

- <span data-ttu-id="5f29b-522">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="5f29b-522">Function is unbound.</span></span>

### <a name="vigotobrace"></a><span data-ttu-id="5f29b-523">виготобраце</span><span class="sxs-lookup"><span data-stu-id="5f29b-523">ViGotoBrace</span></span>

<span data-ttu-id="5f29b-524">Аналогичен Готобраце, но является символом, а не основан на токене.</span><span class="sxs-lookup"><span data-stu-id="5f29b-524">Similar to GotoBrace, but is character based instead of token based.</span></span>

- <span data-ttu-id="5f29b-525">Режим команд VI: `<%>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-525">Vi command mode: `<%>`</span></span>

### <a name="vinextglob"></a><span data-ttu-id="5f29b-526">винекстглоб</span><span class="sxs-lookup"><span data-stu-id="5f29b-526">ViNextGlob</span></span>

<span data-ttu-id="5f29b-527">Переход к следующему слову с использованием только пробелов в качестве разделителя слов.</span><span class="sxs-lookup"><span data-stu-id="5f29b-527">Moves to the next word, using only white space as a word delimiter.</span></span>

- <span data-ttu-id="5f29b-528">Режим команд VI: `<W>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-528">Vi command mode: `<W>`</span></span>

### <a name="vinextword"></a><span data-ttu-id="5f29b-529">винекстворд</span><span class="sxs-lookup"><span data-stu-id="5f29b-529">ViNextWord</span></span>

<span data-ttu-id="5f29b-530">Переместить курсор вперед к началу следующего слова.</span><span class="sxs-lookup"><span data-stu-id="5f29b-530">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="5f29b-531">Границы слов определяются с помощью настраиваемого набора символов.</span><span class="sxs-lookup"><span data-stu-id="5f29b-531">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="5f29b-532">Режим команд VI: `<w>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-532">Vi command mode: `<w>`</span></span>

## <a name="history-functions"></a><span data-ttu-id="5f29b-533">Функции журнала</span><span class="sxs-lookup"><span data-stu-id="5f29b-533">History functions</span></span>

### <a name="beginningofhistory"></a><span data-ttu-id="5f29b-534">бегиннингофхистори</span><span class="sxs-lookup"><span data-stu-id="5f29b-534">BeginningOfHistory</span></span>

<span data-ttu-id="5f29b-535">Перейти к первому элементу в журнале.</span><span class="sxs-lookup"><span data-stu-id="5f29b-535">Move to the first item in the history.</span></span>

- <span data-ttu-id="5f29b-536">Emacs: `<Alt+`<>\`</span><span class="sxs-lookup"><span data-stu-id="5f29b-536">Emacs: `<Alt+`<>\`</span></span>

### <a name="clearhistory"></a><span data-ttu-id="5f29b-537">клеархистори</span><span class="sxs-lookup"><span data-stu-id="5f29b-537">ClearHistory</span></span>

<span data-ttu-id="5f29b-538">Очищает журнал в PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="5f29b-538">Clears history in PSReadLine.</span></span> <span data-ttu-id="5f29b-539">Это не влияет на журнал PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5f29b-539">This does not affect PowerShell history.</span></span>

- <span data-ttu-id="5f29b-540">Процессор `<Alt+F7>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-540">Cmd: `<Alt+F7>`</span></span>

### <a name="endofhistory"></a><span data-ttu-id="5f29b-541">ендофхистори</span><span class="sxs-lookup"><span data-stu-id="5f29b-541">EndOfHistory</span></span>

<span data-ttu-id="5f29b-542">Переход к последнему элементу (текущему входному объекту) в журнале.</span><span class="sxs-lookup"><span data-stu-id="5f29b-542">Move to the last item (the current input) in the history.</span></span>

- <span data-ttu-id="5f29b-543">Emacs: `<Alt+>>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-543">Emacs: `<Alt+>>`</span></span>

### <a name="forwardsearchhistory"></a><span data-ttu-id="5f29b-544">форвардсеарчхистори</span><span class="sxs-lookup"><span data-stu-id="5f29b-544">ForwardSearchHistory</span></span>

<span data-ttu-id="5f29b-545">Выполните добавочный поиск по журналу.</span><span class="sxs-lookup"><span data-stu-id="5f29b-545">Perform an incremental forward search through history.</span></span>

- <span data-ttu-id="5f29b-546">Процессор `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-546">Cmd: `<Ctrl+s>`</span></span>
- <span data-ttu-id="5f29b-547">Emacs: `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-547">Emacs: `<Ctrl+s>`</span></span>

### <a name="historysearchbackward"></a><span data-ttu-id="5f29b-548">хисторисеарчбакквард</span><span class="sxs-lookup"><span data-stu-id="5f29b-548">HistorySearchBackward</span></span>

<span data-ttu-id="5f29b-549">Замените текущие входные данные элементом "Previous" из журнала PSReadLine, который соответствует символам между началом и входом и курсором.</span><span class="sxs-lookup"><span data-stu-id="5f29b-549">Replace the current input with the 'previous' item from PSReadLine history that matches the characters between the start and the input and the cursor.</span></span>

- <span data-ttu-id="5f29b-550">Процессор `<F8>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-550">Cmd: `<F8>`</span></span>

### <a name="historysearchforward"></a><span data-ttu-id="5f29b-551">хисторисеарчфорвард</span><span class="sxs-lookup"><span data-stu-id="5f29b-551">HistorySearchForward</span></span>

<span data-ttu-id="5f29b-552">Замените текущие входные данные элементом "Next" из журнала PSReadLine, который соответствует символам между началом и входом и курсором.</span><span class="sxs-lookup"><span data-stu-id="5f29b-552">Replace the current input with the 'next' item from PSReadLine history that matches the characters between the start and the input and the cursor.</span></span>

- <span data-ttu-id="5f29b-553">Процессор `<Shift+F8>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-553">Cmd: `<Shift+F8>`</span></span>

### <a name="nexthistory"></a><span data-ttu-id="5f29b-554">некссистори</span><span class="sxs-lookup"><span data-stu-id="5f29b-554">NextHistory</span></span>

<span data-ttu-id="5f29b-555">Замените текущие входные данные на элемент "Next" из журнала PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="5f29b-555">Replace the current input with the 'next' item from PSReadLine history.</span></span>

- <span data-ttu-id="5f29b-556">Процессор `<DownArrow>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-556">Cmd: `<DownArrow>`</span></span>
- <span data-ttu-id="5f29b-557">Emacs: `<DownArrow>` , `<Ctrl+n>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-557">Emacs: `<DownArrow>`, `<Ctrl+n>`</span></span>
- <span data-ttu-id="5f29b-558">Режим вставки в VI: `<DownArrow>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-558">Vi insert mode: `<DownArrow>`</span></span>
- <span data-ttu-id="5f29b-559">Режим команд VI: `<DownArrow>` , `<j>` , `<+>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-559">Vi command mode: `<DownArrow>`, `<j>`, `<+>`</span></span>

### <a name="previoushistory"></a><span data-ttu-id="5f29b-560">превиаушистори</span><span class="sxs-lookup"><span data-stu-id="5f29b-560">PreviousHistory</span></span>

<span data-ttu-id="5f29b-561">Замените текущие входные данные элементом "Previous" из журнала PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="5f29b-561">Replace the current input with the 'previous' item from PSReadLine history.</span></span>

- <span data-ttu-id="5f29b-562">Процессор `<UpArrow>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-562">Cmd: `<UpArrow>`</span></span>
- <span data-ttu-id="5f29b-563">Emacs: `<UpArrow>` , `<Ctrl+p>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-563">Emacs: `<UpArrow>`, `<Ctrl+p>`</span></span>
- <span data-ttu-id="5f29b-564">Режим вставки в VI: `<UpArrow>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-564">Vi insert mode: `<UpArrow>`</span></span>
- <span data-ttu-id="5f29b-565">Режим команд VI: `<UpArrow>` , `<k>` , `<->`</span><span class="sxs-lookup"><span data-stu-id="5f29b-565">Vi command mode: `<UpArrow>`, `<k>`, `<->`</span></span>

### <a name="reversesearchhistory"></a><span data-ttu-id="5f29b-566">реверсесеарчхистори</span><span class="sxs-lookup"><span data-stu-id="5f29b-566">ReverseSearchHistory</span></span>

<span data-ttu-id="5f29b-567">Выполните добавочный поиск по журналу.</span><span class="sxs-lookup"><span data-stu-id="5f29b-567">Perform an incremental backward search through history.</span></span>

- <span data-ttu-id="5f29b-568">Процессор `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-568">Cmd: `<Ctrl+r>`</span></span>
- <span data-ttu-id="5f29b-569">Emacs: `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-569">Emacs: `<Ctrl+r>`</span></span>

### <a name="visearchhistorybackward"></a><span data-ttu-id="5f29b-570">висеарчхисторибакквард</span><span class="sxs-lookup"><span data-stu-id="5f29b-570">ViSearchHistoryBackward</span></span>

<span data-ttu-id="5f29b-571">Запрашивает строку поиска и инициирует поиск по запросу Акцептлине.</span><span class="sxs-lookup"><span data-stu-id="5f29b-571">Prompts for a search string and initiates search upon AcceptLine.</span></span>

- <span data-ttu-id="5f29b-572">Режим вставки в VI: `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-572">Vi insert mode: `<Ctrl+r>`</span></span>
- <span data-ttu-id="5f29b-573">Режим команд VI: `</>` , `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-573">Vi command mode: `</>`, `<Ctrl+r>`</span></span>

## <a name="completion-functions"></a><span data-ttu-id="5f29b-574">Функции завершения</span><span class="sxs-lookup"><span data-stu-id="5f29b-574">Completion functions</span></span>

### <a name="complete"></a><span data-ttu-id="5f29b-575">Завершить</span><span class="sxs-lookup"><span data-stu-id="5f29b-575">Complete</span></span>

<span data-ttu-id="5f29b-576">Попытка выполнить завершение в тексте, окружающем курсор.</span><span class="sxs-lookup"><span data-stu-id="5f29b-576">Attempt to perform completion on the text surrounding the cursor.</span></span> <span data-ttu-id="5f29b-577">Если существует несколько возможных завершений, для завершения используется самый длинный ненеоднозначный префикс.</span><span class="sxs-lookup"><span data-stu-id="5f29b-577">If there are multiple possible completions, the longest unambiguous prefix is used for completion.</span></span> <span data-ttu-id="5f29b-578">При попытке выполнить наибольшее неоднозначное Завершение отображается список возможных завершений.</span><span class="sxs-lookup"><span data-stu-id="5f29b-578">If trying to complete the longest unambiguous completion, a list of possible completions is displayed.</span></span>

- <span data-ttu-id="5f29b-579">Emacs: `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-579">Emacs: `<Tab>`</span></span>

### <a name="menucomplete"></a><span data-ttu-id="5f29b-580">менукомплете</span><span class="sxs-lookup"><span data-stu-id="5f29b-580">MenuComplete</span></span>

<span data-ttu-id="5f29b-581">Попытка выполнить завершение в тексте, окружающем курсор.</span><span class="sxs-lookup"><span data-stu-id="5f29b-581">Attempt to perform completion on the text surrounding the cursor.</span></span> <span data-ttu-id="5f29b-582">Если существует несколько возможных завершений, для завершения используется самый длинный ненеоднозначный префикс.</span><span class="sxs-lookup"><span data-stu-id="5f29b-582">If there are multiple possible completions, the longest unambiguous prefix is used for completion.</span></span> <span data-ttu-id="5f29b-583">При попытке выполнить наибольшее неоднозначное Завершение отображается список возможных завершений.</span><span class="sxs-lookup"><span data-stu-id="5f29b-583">If trying to complete the longest unambiguous completion, a list of possible completions is displayed.</span></span>

- <span data-ttu-id="5f29b-584">Процессор `<Ctrl+Space>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-584">Cmd: `<Ctrl+Space>`</span></span>
- <span data-ttu-id="5f29b-585">Emacs: `<Ctrl+Space>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-585">Emacs: `<Ctrl+Space>`</span></span>

### <a name="possiblecompletions"></a><span data-ttu-id="5f29b-586">поссиблекомплетионс</span><span class="sxs-lookup"><span data-stu-id="5f29b-586">PossibleCompletions</span></span>

<span data-ttu-id="5f29b-587">Отображение списка возможных завершений.</span><span class="sxs-lookup"><span data-stu-id="5f29b-587">Display the list of possible completions.</span></span>

- <span data-ttu-id="5f29b-588">Emacs: `<Alt+=>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-588">Emacs: `<Alt+=>`</span></span>
- <span data-ttu-id="5f29b-589">Режим вставки в VI: `<Ctrl+Space>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-589">Vi insert mode: `<Ctrl+Space>`</span></span>
- <span data-ttu-id="5f29b-590">Режим команд VI: `<Ctrl+Space>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-590">Vi command mode: `<Ctrl+Space>`</span></span>

### <a name="tabcompletenext"></a><span data-ttu-id="5f29b-591">табкомплетенекст</span><span class="sxs-lookup"><span data-stu-id="5f29b-591">TabCompleteNext</span></span>

<span data-ttu-id="5f29b-592">Попытайтесь завершить текст, окружающий курсор, с помощью следующего доступного завершения.</span><span class="sxs-lookup"><span data-stu-id="5f29b-592">Attempt to complete the text surrounding the cursor with the next available completion.</span></span>

- <span data-ttu-id="5f29b-593">Процессор `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-593">Cmd: `<Tab>`</span></span>
- <span data-ttu-id="5f29b-594">Режим команд VI: `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-594">Vi command mode: `<Tab>`</span></span>

### <a name="tabcompleteprevious"></a><span data-ttu-id="5f29b-595">табкомплетепревиаус</span><span class="sxs-lookup"><span data-stu-id="5f29b-595">TabCompletePrevious</span></span>

<span data-ttu-id="5f29b-596">Попытайтесь завершить текст, окружающий курсор, с предыдущим доступным завершением.</span><span class="sxs-lookup"><span data-stu-id="5f29b-596">Attempt to complete the text surrounding the cursor with the previous available completion.</span></span>

- <span data-ttu-id="5f29b-597">Процессор `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-597">Cmd: `<Shift+Tab>`</span></span>
- <span data-ttu-id="5f29b-598">Режим команд VI: `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-598">Vi command mode: `<Shift+Tab>`</span></span>

### <a name="vitabcompletenext"></a><span data-ttu-id="5f29b-599">витабкомплетенекст</span><span class="sxs-lookup"><span data-stu-id="5f29b-599">ViTabCompleteNext</span></span>

<span data-ttu-id="5f29b-600">При необходимости завершает текущую группу редактирования и вызывает Табкомплетенекст.</span><span class="sxs-lookup"><span data-stu-id="5f29b-600">Ends the current edit group, if needed, and invokes TabCompleteNext.</span></span>

- <span data-ttu-id="5f29b-601">Режим вставки в VI: `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-601">Vi insert mode: `<Tab>`</span></span>

### <a name="vitabcompleteprevious"></a><span data-ttu-id="5f29b-602">витабкомплетепревиаус</span><span class="sxs-lookup"><span data-stu-id="5f29b-602">ViTabCompletePrevious</span></span>

<span data-ttu-id="5f29b-603">При необходимости завершает текущую группу редактирования и вызывает Табкомплетепревиаус.</span><span class="sxs-lookup"><span data-stu-id="5f29b-603">Ends the current edit group, if needed, and invokes TabCompletePrevious.</span></span>

- <span data-ttu-id="5f29b-604">Режим вставки в VI: `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-604">Vi insert mode: `<Shift+Tab>`</span></span>

## <a name="miscellaneous-functions"></a><span data-ttu-id="5f29b-605">Прочие функции</span><span class="sxs-lookup"><span data-stu-id="5f29b-605">Miscellaneous functions</span></span>

### <a name="capturescreen"></a><span data-ttu-id="5f29b-606">каптурескрин</span><span class="sxs-lookup"><span data-stu-id="5f29b-606">CaptureScreen</span></span>

<span data-ttu-id="5f29b-607">Запуск интерактивной записи экрана — стрелки вверх и вниз выбор строк, ввод копирует выделенный текст в буфер обмена в виде текста и HTML.</span><span class="sxs-lookup"><span data-stu-id="5f29b-607">Start interactive screen capture - up/down arrows select lines, enter copies selected text to clipboard as text and html.</span></span>

- <span data-ttu-id="5f29b-608">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="5f29b-608">Function is unbound.</span></span>

### <a name="clearscreen"></a><span data-ttu-id="5f29b-609">клеарскрин</span><span class="sxs-lookup"><span data-stu-id="5f29b-609">ClearScreen</span></span>

<span data-ttu-id="5f29b-610">Очистить экран и нарисовать текущую строку в верхней части экрана.</span><span class="sxs-lookup"><span data-stu-id="5f29b-610">Clear the screen and draw the current line at the top of the screen.</span></span>

- <span data-ttu-id="5f29b-611">Процессор `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-611">Cmd: `<Ctrl+l>`</span></span>
- <span data-ttu-id="5f29b-612">Emacs: `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-612">Emacs: `<Ctrl+l>`</span></span>
- <span data-ttu-id="5f29b-613">Режим вставки в VI: `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-613">Vi insert mode: `<Ctrl+l>`</span></span>
- <span data-ttu-id="5f29b-614">Режим команд VI: `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-614">Vi command mode: `<Ctrl+l>`</span></span>

### <a name="digitargument"></a><span data-ttu-id="5f29b-615">дигитаргумент</span><span class="sxs-lookup"><span data-stu-id="5f29b-615">DigitArgument</span></span>

<span data-ttu-id="5f29b-616">Начните новый аргумент цифры для передачи другим функциям.</span><span class="sxs-lookup"><span data-stu-id="5f29b-616">Start a new digit argument to pass to other functions.</span></span>

- <span data-ttu-id="5f29b-617">Cmd: `<Alt+0>` , `<Alt+1>` , `<Alt+2>` , `<Alt+3>` , `<Alt+4>` , `<Alt+5>` , `<Alt+6>` , `<Alt+7>` , `<Alt+8>` , `<Alt+9>` , `<Alt+->`</span><span class="sxs-lookup"><span data-stu-id="5f29b-617">Cmd: `<Alt+0>`, `<Alt+1>`, `<Alt+2>`, `<Alt+3>`, `<Alt+4>`, `<Alt+5>`, `<Alt+6>`, `<Alt+7>`, `<Alt+8>`, `<Alt+9>`, `<Alt+->`</span></span>
- <span data-ttu-id="5f29b-618">Emacs: `<Alt+0>` , `<Alt+1>` , `<Alt+2>` , `<Alt+3>` , `<Alt+4>` , `<Alt+5>` , `<Alt+6>` , `<Alt+7>` , `<Alt+8>` , `<Alt+9>` , `<Alt+->`</span><span class="sxs-lookup"><span data-stu-id="5f29b-618">Emacs: `<Alt+0>`, `<Alt+1>`, `<Alt+2>`, `<Alt+3>`, `<Alt+4>`, `<Alt+5>`, `<Alt+6>`, `<Alt+7>`, `<Alt+8>`, `<Alt+9>`, `<Alt+->`</span></span>
- <span data-ttu-id="5f29b-619">Режим команд VI: `<0>` , `<1>` , `<2>` , `<3>` , `<4>` , `<5>` , `<6>` , `<7>` , `<8>` , `<9>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-619">Vi command mode: `<0>`, `<1>`, `<2>`, `<3>`, `<4>`, `<5>`, `<6>`, `<7>`, `<8>`, `<9>`</span></span>

### <a name="invokeprompt"></a><span data-ttu-id="5f29b-620">инвокепромпт</span><span class="sxs-lookup"><span data-stu-id="5f29b-620">InvokePrompt</span></span>

<span data-ttu-id="5f29b-621">Стирает текущий запрос и вызывает функцию Prompt для повторного вывода запроса.</span><span class="sxs-lookup"><span data-stu-id="5f29b-621">Erases the current prompt and calls the prompt function to redisplay the prompt.</span></span> <span data-ttu-id="5f29b-622">Полезен для обработчиков пользовательских ключей, изменяющих состояние, например для изменения текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="5f29b-622">Useful for custom key handlers that change state, e.g. change the current directory.</span></span>

- <span data-ttu-id="5f29b-623">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="5f29b-623">Function is unbound.</span></span>

### <a name="scrolldisplaydown"></a><span data-ttu-id="5f29b-624">скроллдисплайдовн</span><span class="sxs-lookup"><span data-stu-id="5f29b-624">ScrollDisplayDown</span></span>

<span data-ttu-id="5f29b-625">Прокрутите экран вниз на один экран.</span><span class="sxs-lookup"><span data-stu-id="5f29b-625">Scroll the display down one screen.</span></span>

- <span data-ttu-id="5f29b-626">Процессор `<PageDown>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-626">Cmd: `<PageDown>`</span></span>
- <span data-ttu-id="5f29b-627">Emacs: `<PageDown>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-627">Emacs: `<PageDown>`</span></span>

### <a name="scrolldisplaydownline"></a><span data-ttu-id="5f29b-628">скроллдисплайдовнлине</span><span class="sxs-lookup"><span data-stu-id="5f29b-628">ScrollDisplayDownLine</span></span>

<span data-ttu-id="5f29b-629">Прокрутите экран вниз на одну строку.</span><span class="sxs-lookup"><span data-stu-id="5f29b-629">Scroll the display down one line.</span></span>

- <span data-ttu-id="5f29b-630">Процессор `<Ctrl+PageDown>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-630">Cmd: `<Ctrl+PageDown>`</span></span>
- <span data-ttu-id="5f29b-631">Emacs: `<Ctrl+PageDown>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-631">Emacs: `<Ctrl+PageDown>`</span></span>

### <a name="scrolldisplaytocursor"></a><span data-ttu-id="5f29b-632">скроллдисплайтокурсор</span><span class="sxs-lookup"><span data-stu-id="5f29b-632">ScrollDisplayToCursor</span></span>

<span data-ttu-id="5f29b-633">Прокрутить экран до курсора.</span><span class="sxs-lookup"><span data-stu-id="5f29b-633">Scroll the display to the cursor.</span></span>

- <span data-ttu-id="5f29b-634">Emacs: `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-634">Emacs: `<Ctrl+End>`</span></span>

### <a name="scrolldisplaytop"></a><span data-ttu-id="5f29b-635">скроллдисплайтоп</span><span class="sxs-lookup"><span data-stu-id="5f29b-635">ScrollDisplayTop</span></span>

<span data-ttu-id="5f29b-636">Прокрутите экран до верха.</span><span class="sxs-lookup"><span data-stu-id="5f29b-636">Scroll the display to the top.</span></span>

- <span data-ttu-id="5f29b-637">Emacs: `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-637">Emacs: `<Ctrl+Home>`</span></span>

### <a name="scrolldisplayup"></a><span data-ttu-id="5f29b-638">скроллдисплайуп</span><span class="sxs-lookup"><span data-stu-id="5f29b-638">ScrollDisplayUp</span></span>

<span data-ttu-id="5f29b-639">Прокрутите экран вверх на один экран.</span><span class="sxs-lookup"><span data-stu-id="5f29b-639">Scroll the display up one screen.</span></span>

- <span data-ttu-id="5f29b-640">Процессор `<PageUp>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-640">Cmd: `<PageUp>`</span></span>
- <span data-ttu-id="5f29b-641">Emacs: `<PageUp>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-641">Emacs: `<PageUp>`</span></span>

### <a name="scrolldisplayupline"></a><span data-ttu-id="5f29b-642">скроллдисплайуплине</span><span class="sxs-lookup"><span data-stu-id="5f29b-642">ScrollDisplayUpLine</span></span>

<span data-ttu-id="5f29b-643">Прокрутите экран вверх на одну строку.</span><span class="sxs-lookup"><span data-stu-id="5f29b-643">Scroll the display up one line.</span></span>

- <span data-ttu-id="5f29b-644">Процессор `<Ctrl+PageUp>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-644">Cmd: `<Ctrl+PageUp>`</span></span>
- <span data-ttu-id="5f29b-645">Emacs: `<Ctrl+PageUp>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-645">Emacs: `<Ctrl+PageUp>`</span></span>

### <a name="selfinsert"></a><span data-ttu-id="5f29b-646">селфинсерт</span><span class="sxs-lookup"><span data-stu-id="5f29b-646">SelfInsert</span></span>

<span data-ttu-id="5f29b-647">Вставьте ключ.</span><span class="sxs-lookup"><span data-stu-id="5f29b-647">Insert the key.</span></span>

- <span data-ttu-id="5f29b-648">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="5f29b-648">Function is unbound.</span></span>

### <a name="showkeybindings"></a><span data-ttu-id="5f29b-649">шовкэйбиндингс</span><span class="sxs-lookup"><span data-stu-id="5f29b-649">ShowKeyBindings</span></span>

<span data-ttu-id="5f29b-650">Отображение всех связанных ключей.</span><span class="sxs-lookup"><span data-stu-id="5f29b-650">Show all bound keys.</span></span>

- <span data-ttu-id="5f29b-651">Процессор `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-651">Cmd: `<Ctrl+Alt+?>`</span></span>
- <span data-ttu-id="5f29b-652">Emacs: `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-652">Emacs: `<Ctrl+Alt+?>`</span></span>
- <span data-ttu-id="5f29b-653">Режим вставки в VI: `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-653">Vi insert mode: `<Ctrl+Alt+?>`</span></span>

### <a name="vicommandmode"></a><span data-ttu-id="5f29b-654">викоммандмоде</span><span class="sxs-lookup"><span data-stu-id="5f29b-654">ViCommandMode</span></span>

<span data-ttu-id="5f29b-655">Переключите текущий режим работы с Vi-Insert на VI-Command.</span><span class="sxs-lookup"><span data-stu-id="5f29b-655">Switch the current operating mode from Vi-Insert to Vi-Command.</span></span>

- <span data-ttu-id="5f29b-656">Режим вставки в VI: `<Escape>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-656">Vi insert mode: `<Escape>`</span></span>

### <a name="vidigitargumentinchord"></a><span data-ttu-id="5f29b-657">видигитаргументинчорд</span><span class="sxs-lookup"><span data-stu-id="5f29b-657">ViDigitArgumentInChord</span></span>

<span data-ttu-id="5f29b-658">Начните новый числовой аргумент, чтобы передать его другим функциям в одной из сочетаний VI.</span><span class="sxs-lookup"><span data-stu-id="5f29b-658">Start a new digit argument to pass to other functions while in one of vi's chords.</span></span>

- <span data-ttu-id="5f29b-659">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="5f29b-659">Function is unbound.</span></span>

### <a name="vieditvisually"></a><span data-ttu-id="5f29b-660">виедитвисуалли</span><span class="sxs-lookup"><span data-stu-id="5f29b-660">ViEditVisually</span></span>

<span data-ttu-id="5f29b-661">Измените командную строку в текстовом редакторе, заданном $env: EDITOR или $env: VISUAL.</span><span class="sxs-lookup"><span data-stu-id="5f29b-661">Edit the command line in a text editor specified by $env:EDITOR or $env:VISUAL.</span></span>

- <span data-ttu-id="5f29b-662">Emacs: `<Ctrl+x,Ctrl+e>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-662">Emacs: `<Ctrl+x,Ctrl+e>`</span></span>
- <span data-ttu-id="5f29b-663">Режим команд VI: `<v>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-663">Vi command mode: `<v>`</span></span>

### <a name="viexit"></a><span data-ttu-id="5f29b-664">виексит</span><span class="sxs-lookup"><span data-stu-id="5f29b-664">ViExit</span></span>

<span data-ttu-id="5f29b-665">Завершает работу оболочки.</span><span class="sxs-lookup"><span data-stu-id="5f29b-665">Exits the shell.</span></span>

- <span data-ttu-id="5f29b-666">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="5f29b-666">Function is unbound.</span></span>

### <a name="viinsertmode"></a><span data-ttu-id="5f29b-667">виинсертмоде</span><span class="sxs-lookup"><span data-stu-id="5f29b-667">ViInsertMode</span></span>

<span data-ttu-id="5f29b-668">Переключитесь в режим вставки.</span><span class="sxs-lookup"><span data-stu-id="5f29b-668">Switch to Insert mode.</span></span>

- <span data-ttu-id="5f29b-669">Режим команд VI: `<i>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-669">Vi command mode: `<i>`</span></span>

### <a name="whatiskey"></a><span data-ttu-id="5f29b-670">вхатискэй</span><span class="sxs-lookup"><span data-stu-id="5f29b-670">WhatIsKey</span></span>

<span data-ttu-id="5f29b-671">Прочитайте ключ и расскажите, к чему привязан ключ.</span><span class="sxs-lookup"><span data-stu-id="5f29b-671">Read a key and tell me what the key is bound to.</span></span>

- <span data-ttu-id="5f29b-672">Процессор `<Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-672">Cmd: `<Alt+?>`</span></span>
- <span data-ttu-id="5f29b-673">Emacs: `<Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-673">Emacs: `<Alt+?>`</span></span>

## <a name="selection-functions"></a><span data-ttu-id="5f29b-674">Функции выбора</span><span class="sxs-lookup"><span data-stu-id="5f29b-674">Selection functions</span></span>

### <a name="exchangepointandmark"></a><span data-ttu-id="5f29b-675">ексчанжепоинтандмарк</span><span class="sxs-lookup"><span data-stu-id="5f29b-675">ExchangePointAndMark</span></span>

<span data-ttu-id="5f29b-676">Курсор помещается в позицию метки, а метка перемещается в положение курсора.</span><span class="sxs-lookup"><span data-stu-id="5f29b-676">The cursor is placed at the location of the mark and the mark is moved to the location of the cursor.</span></span>

- <span data-ttu-id="5f29b-677">Emacs: `<Ctrl+x,Ctrl+x>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-677">Emacs: `<Ctrl+x,Ctrl+x>`</span></span>

### <a name="selectall"></a><span data-ttu-id="5f29b-678">SelectAll</span><span class="sxs-lookup"><span data-stu-id="5f29b-678">SelectAll</span></span>

<span data-ttu-id="5f29b-679">Выделите всю строку.</span><span class="sxs-lookup"><span data-stu-id="5f29b-679">Select the entire line.</span></span>

- <span data-ttu-id="5f29b-680">Процессор `<Ctrl+a>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-680">Cmd: `<Ctrl+a>`</span></span>

### <a name="selectbackwardchar"></a><span data-ttu-id="5f29b-681">селектбакквардчар</span><span class="sxs-lookup"><span data-stu-id="5f29b-681">SelectBackwardChar</span></span>

<span data-ttu-id="5f29b-682">Настройка текущего выделения для включения предыдущего символа.</span><span class="sxs-lookup"><span data-stu-id="5f29b-682">Adjust the current selection to include the previous character.</span></span>

- <span data-ttu-id="5f29b-683">Процессор `<Shift+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-683">Cmd: `<Shift+LeftArrow>`</span></span>
- <span data-ttu-id="5f29b-684">Emacs: `<Shift+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-684">Emacs: `<Shift+LeftArrow>`</span></span>

### <a name="selectbackwardsline"></a><span data-ttu-id="5f29b-685">селектбакквардслине</span><span class="sxs-lookup"><span data-stu-id="5f29b-685">SelectBackwardsLine</span></span>

<span data-ttu-id="5f29b-686">Изменить текущее выделение, чтобы включить его от курсора до начала строки.</span><span class="sxs-lookup"><span data-stu-id="5f29b-686">Adjust the current selection to include from the cursor to the start of the line.</span></span>

- <span data-ttu-id="5f29b-687">Процессор `<Shift+Home>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-687">Cmd: `<Shift+Home>`</span></span>
- <span data-ttu-id="5f29b-688">Emacs: `<Shift+Home>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-688">Emacs: `<Shift+Home>`</span></span>

### <a name="selectbackwardword"></a><span data-ttu-id="5f29b-689">селектбакквардворд</span><span class="sxs-lookup"><span data-stu-id="5f29b-689">SelectBackwardWord</span></span>

<span data-ttu-id="5f29b-690">Настройка текущего выделения для включения предыдущего слова.</span><span class="sxs-lookup"><span data-stu-id="5f29b-690">Adjust the current selection to include the previous word.</span></span>

- <span data-ttu-id="5f29b-691">Процессор `<Shift+Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-691">Cmd: `<Shift+Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="5f29b-692">Emacs: `<Alt+B>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-692">Emacs: `<Alt+B>`</span></span>

### <a name="selectforwardchar"></a><span data-ttu-id="5f29b-693">селектфорвардчар</span><span class="sxs-lookup"><span data-stu-id="5f29b-693">SelectForwardChar</span></span>

<span data-ttu-id="5f29b-694">Измените текущее выделение, чтобы включить следующий символ.</span><span class="sxs-lookup"><span data-stu-id="5f29b-694">Adjust the current selection to include the next character.</span></span>

- <span data-ttu-id="5f29b-695">Процессор `<Shift+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-695">Cmd: `<Shift+RightArrow>`</span></span>
- <span data-ttu-id="5f29b-696">Emacs: `<Shift+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-696">Emacs: `<Shift+RightArrow>`</span></span>

### <a name="selectforwardword"></a><span data-ttu-id="5f29b-697">селектфорвардворд</span><span class="sxs-lookup"><span data-stu-id="5f29b-697">SelectForwardWord</span></span>

<span data-ttu-id="5f29b-698">Измените текущее выделение, чтобы включить следующее слово с помощью Форвардворд.</span><span class="sxs-lookup"><span data-stu-id="5f29b-698">Adjust the current selection to include the next word using ForwardWord.</span></span>

- <span data-ttu-id="5f29b-699">Emacs: `<Alt+F>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-699">Emacs: `<Alt+F>`</span></span>

### <a name="selectline"></a><span data-ttu-id="5f29b-700">селектлине</span><span class="sxs-lookup"><span data-stu-id="5f29b-700">SelectLine</span></span>

<span data-ttu-id="5f29b-701">Настройка текущего выделения для включения курсора в конец строки.</span><span class="sxs-lookup"><span data-stu-id="5f29b-701">Adjust the current selection to include from the cursor to the end of the line.</span></span>

- <span data-ttu-id="5f29b-702">Процессор `<Shift+End>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-702">Cmd: `<Shift+End>`</span></span>
- <span data-ttu-id="5f29b-703">Emacs: `<Shift+End>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-703">Emacs: `<Shift+End>`</span></span>

### <a name="selectnextword"></a><span data-ttu-id="5f29b-704">селектнекстворд</span><span class="sxs-lookup"><span data-stu-id="5f29b-704">SelectNextWord</span></span>

<span data-ttu-id="5f29b-705">Настройка текущего выделения для включения следующего слова.</span><span class="sxs-lookup"><span data-stu-id="5f29b-705">Adjust the current selection to include the next word.</span></span>

- <span data-ttu-id="5f29b-706">Процессор `<Shift+Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-706">Cmd: `<Shift+Ctrl+RightArrow>`</span></span>

### <a name="selectshellbackwardword"></a><span data-ttu-id="5f29b-707">селектшеллбакквардворд</span><span class="sxs-lookup"><span data-stu-id="5f29b-707">SelectShellBackwardWord</span></span>

<span data-ttu-id="5f29b-708">Измените текущее выделение, чтобы включить предыдущее слово с помощью Шеллбакквардворд.</span><span class="sxs-lookup"><span data-stu-id="5f29b-708">Adjust the current selection to include the previous word using ShellBackwardWord.</span></span>

- <span data-ttu-id="5f29b-709">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="5f29b-709">Function is unbound.</span></span>

### <a name="selectshellforwardword"></a><span data-ttu-id="5f29b-710">селектшеллфорвардворд</span><span class="sxs-lookup"><span data-stu-id="5f29b-710">SelectShellForwardWord</span></span>

<span data-ttu-id="5f29b-711">Измените текущее выделение, чтобы включить следующее слово с помощью Шеллфорвардворд.</span><span class="sxs-lookup"><span data-stu-id="5f29b-711">Adjust the current selection to include the next word using ShellForwardWord.</span></span>

- <span data-ttu-id="5f29b-712">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="5f29b-712">Function is unbound.</span></span>

### <a name="selectshellnextword"></a><span data-ttu-id="5f29b-713">селектшеллнекстворд</span><span class="sxs-lookup"><span data-stu-id="5f29b-713">SelectShellNextWord</span></span>

<span data-ttu-id="5f29b-714">Измените текущее выделение, чтобы включить следующее слово с помощью Шеллнекстворд.</span><span class="sxs-lookup"><span data-stu-id="5f29b-714">Adjust the current selection to include the next word using ShellNextWord.</span></span>

- <span data-ttu-id="5f29b-715">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="5f29b-715">Function is unbound.</span></span>

### <a name="setmark"></a><span data-ttu-id="5f29b-716">сетмарк</span><span class="sxs-lookup"><span data-stu-id="5f29b-716">SetMark</span></span>

<span data-ttu-id="5f29b-717">Пометка текущего положения курсора для использования в последующей команде редактирования.</span><span class="sxs-lookup"><span data-stu-id="5f29b-717">Mark the current location of the cursor for use in a subsequent editing command.</span></span>

- <span data-ttu-id="5f29b-718">Emacs: `<Ctrl+`>\`</span><span class="sxs-lookup"><span data-stu-id="5f29b-718">Emacs: `<Ctrl+`>\`</span></span>

## <a name="search-functions"></a><span data-ttu-id="5f29b-719">Функции поиска</span><span class="sxs-lookup"><span data-stu-id="5f29b-719">Search functions</span></span>

### <a name="charactersearch"></a><span data-ttu-id="5f29b-720">чарактерсеарч</span><span class="sxs-lookup"><span data-stu-id="5f29b-720">CharacterSearch</span></span>

<span data-ttu-id="5f29b-721">Чтение символа и поиск вперед для следующего вхождения этого символа.</span><span class="sxs-lookup"><span data-stu-id="5f29b-721">Read a character and search forward for the next occurrence of that character.</span></span>
<span data-ttu-id="5f29b-722">Если указан аргумент, то для n-го вхождения выполните поиск вперед (или назад, если отрицательное).</span><span class="sxs-lookup"><span data-stu-id="5f29b-722">If an argument is specified, search forward (or backward if negative) for the nth occurrence.</span></span>

- <span data-ttu-id="5f29b-723">Процессор `<F3>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-723">Cmd: `<F3>`</span></span>
- <span data-ttu-id="5f29b-724">Emacs: `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-724">Emacs: `<Ctrl+]>`</span></span>
- <span data-ttu-id="5f29b-725">Режим вставки в VI: `<F3>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-725">Vi insert mode: `<F3>`</span></span>
- <span data-ttu-id="5f29b-726">Режим команд VI: `<F3>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-726">Vi command mode: `<F3>`</span></span>

### <a name="charactersearchbackward"></a><span data-ttu-id="5f29b-727">чарактерсеарчбакквард</span><span class="sxs-lookup"><span data-stu-id="5f29b-727">CharacterSearchBackward</span></span>

<span data-ttu-id="5f29b-728">Чтение символа и поиск следующего вхождения этого символа в обратном направлении.</span><span class="sxs-lookup"><span data-stu-id="5f29b-728">Read a character and search backward for the next occurrence of that character.</span></span> <span data-ttu-id="5f29b-729">Если аргумент указан, поиск в n-й последовательности осуществляется назад (или вперед, если отрицательное).</span><span class="sxs-lookup"><span data-stu-id="5f29b-729">If an argument is specified, search backward (or forward if negative) for the nth occurrence.</span></span>

- <span data-ttu-id="5f29b-730">Процессор `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-730">Cmd: `<Shift+F3>`</span></span>
- <span data-ttu-id="5f29b-731">Emacs: `<Ctrl+Alt+]>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-731">Emacs: `<Ctrl+Alt+]>`</span></span>
- <span data-ttu-id="5f29b-732">Режим вставки в VI: `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-732">Vi insert mode: `<Shift+F3>`</span></span>
- <span data-ttu-id="5f29b-733">Режим команд VI: `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-733">Vi command mode: `<Shift+F3>`</span></span>

### <a name="repeatlastcharsearch"></a><span data-ttu-id="5f29b-734">репеатластчарсеарч</span><span class="sxs-lookup"><span data-stu-id="5f29b-734">RepeatLastCharSearch</span></span>

<span data-ttu-id="5f29b-735">Повторите поиск последнего записанного символа.</span><span class="sxs-lookup"><span data-stu-id="5f29b-735">Repeat the last recorded character search.</span></span>

- <span data-ttu-id="5f29b-736">Режим команд VI: `<;>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-736">Vi command mode: `<;>`</span></span>

### <a name="repeatlastcharsearchbackwards"></a><span data-ttu-id="5f29b-737">репеатластчарсеарчбакквардс</span><span class="sxs-lookup"><span data-stu-id="5f29b-737">RepeatLastCharSearchBackwards</span></span>

<span data-ttu-id="5f29b-738">Повторите поиск последнего записанного символа, но в обратном направлении.</span><span class="sxs-lookup"><span data-stu-id="5f29b-738">Repeat the last recorded character search, but in the opposite direction.</span></span>

- <span data-ttu-id="5f29b-739">Режим команд VI: `<,>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-739">Vi command mode: `<,>`</span></span>

### <a name="repeatsearch"></a><span data-ttu-id="5f29b-740">репеатсеарч</span><span class="sxs-lookup"><span data-stu-id="5f29b-740">RepeatSearch</span></span>

<span data-ttu-id="5f29b-741">Повторите последний поиск в том же направлении, что и раньше.</span><span class="sxs-lookup"><span data-stu-id="5f29b-741">Repeat the last search in the same direction as before.</span></span>

- <span data-ttu-id="5f29b-742">Режим команд VI: `<n>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-742">Vi command mode: `<n>`</span></span>

### <a name="repeatsearchbackward"></a><span data-ttu-id="5f29b-743">репеатсеарчбакквард</span><span class="sxs-lookup"><span data-stu-id="5f29b-743">RepeatSearchBackward</span></span>

<span data-ttu-id="5f29b-744">Повторите последний поиск в том же направлении, что и раньше.</span><span class="sxs-lookup"><span data-stu-id="5f29b-744">Repeat the last search in the same direction as before.</span></span>

- <span data-ttu-id="5f29b-745">Режим команд VI: `<N>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-745">Vi command mode: `<N>`</span></span>

### <a name="searchchar"></a><span data-ttu-id="5f29b-746">сеарччар</span><span class="sxs-lookup"><span data-stu-id="5f29b-746">SearchChar</span></span>

<span data-ttu-id="5f29b-747">Прочитать следующий символ, затем найти его, перейти вперед, а затем отследить символ.</span><span class="sxs-lookup"><span data-stu-id="5f29b-747">Read the next character and then find it, going forward, and then back off a character.</span></span> <span data-ttu-id="5f29b-748">Это относится к функциональным возможностям.</span><span class="sxs-lookup"><span data-stu-id="5f29b-748">This is for 't' functionality.</span></span>

- <span data-ttu-id="5f29b-749">Режим команд VI: `<f>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-749">Vi command mode: `<f>`</span></span>

### <a name="searchcharbackward"></a><span data-ttu-id="5f29b-750">сеарччарбакквард</span><span class="sxs-lookup"><span data-stu-id="5f29b-750">SearchCharBackward</span></span>

<span data-ttu-id="5f29b-751">Прочитать следующий символ, а затем найти его, вернуться назад, а затем отследить символ.</span><span class="sxs-lookup"><span data-stu-id="5f29b-751">Read the next character and then find it, going backward, and then back off a character.</span></span> <span data-ttu-id="5f29b-752">Это относится к функциональным возможностям.</span><span class="sxs-lookup"><span data-stu-id="5f29b-752">This is for 'T' functionality.</span></span>

- <span data-ttu-id="5f29b-753">Режим команд VI: `<F>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-753">Vi command mode: `<F>`</span></span>

### <a name="searchcharbackwardwithbackoff"></a><span data-ttu-id="5f29b-754">сеарччарбакквардвисбаккофф</span><span class="sxs-lookup"><span data-stu-id="5f29b-754">SearchCharBackwardWithBackoff</span></span>

<span data-ttu-id="5f29b-755">Прочитать следующий символ, а затем найти его, вернуться назад, а затем отследить символ.</span><span class="sxs-lookup"><span data-stu-id="5f29b-755">Read the next character and then find it, going backward, and then back off a character.</span></span> <span data-ttu-id="5f29b-756">Это относится к функциональным возможностям.</span><span class="sxs-lookup"><span data-stu-id="5f29b-756">This is for 'T' functionality.</span></span>

- <span data-ttu-id="5f29b-757">Режим команд VI: `<T>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-757">Vi command mode: `<T>`</span></span>

### <a name="searchcharwithbackoff"></a><span data-ttu-id="5f29b-758">сеарччарвисбаккофф</span><span class="sxs-lookup"><span data-stu-id="5f29b-758">SearchCharWithBackoff</span></span>

<span data-ttu-id="5f29b-759">Прочитать следующий символ, затем найти его, перейти вперед, а затем отследить символ.</span><span class="sxs-lookup"><span data-stu-id="5f29b-759">Read the next character and then find it, going forward, and then back off a character.</span></span> <span data-ttu-id="5f29b-760">Это относится к функциональным возможностям.</span><span class="sxs-lookup"><span data-stu-id="5f29b-760">This is for 't' functionality.</span></span>

- <span data-ttu-id="5f29b-761">Режим команд VI: `<t>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-761">Vi command mode: `<t>`</span></span>

### <a name="searchforward"></a><span data-ttu-id="5f29b-762">сеарчфорвард</span><span class="sxs-lookup"><span data-stu-id="5f29b-762">SearchForward</span></span>

<span data-ttu-id="5f29b-763">Запрашивает строку поиска и инициирует поиск по запросу Акцептлине.</span><span class="sxs-lookup"><span data-stu-id="5f29b-763">Prompts for a search string and initiates search upon AcceptLine.</span></span>

- <span data-ttu-id="5f29b-764">Режим вставки в VI: `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-764">Vi insert mode: `<Ctrl+s>`</span></span>
- <span data-ttu-id="5f29b-765">Режим команд VI: `<?>` , `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="5f29b-765">Vi command mode: `<?>`, `<Ctrl+s>`</span></span>

## <a name="custom-key-bindings"></a><span data-ttu-id="5f29b-766">Пользовательские привязки клавиш</span><span class="sxs-lookup"><span data-stu-id="5f29b-766">Custom Key Bindings</span></span>

<span data-ttu-id="5f29b-767">PSReadLine поддерживает пользовательские привязки клавиш с помощью командлета `Set-PSReadLineKeyHandler` .</span><span class="sxs-lookup"><span data-stu-id="5f29b-767">PSReadLine supports custom key bindings using the cmdlet `Set-PSReadLineKeyHandler`.</span></span> <span data-ttu-id="5f29b-768">Большинство пользовательских привязок вызывают одну из приведенных выше функций, например</span><span class="sxs-lookup"><span data-stu-id="5f29b-768">Most custom key bindings call one of the above functions, for example</span></span>

```powershell
Set-PSReadLineKeyHandler -Key UpArrow -Function HistorySearchBackward
```

<span data-ttu-id="5f29b-769">Можно привязать ScriptBlock к ключу.</span><span class="sxs-lookup"><span data-stu-id="5f29b-769">You can bind a ScriptBlock to a key.</span></span> <span data-ttu-id="5f29b-770">Блок ScriptBlock может выполнять практически все необходимые действия.</span><span class="sxs-lookup"><span data-stu-id="5f29b-770">The ScriptBlock can do pretty much anything you want.</span></span> <span data-ttu-id="5f29b-771">Ниже приведены некоторые полезные примеры.</span><span class="sxs-lookup"><span data-stu-id="5f29b-771">Some useful examples include</span></span>

- <span data-ttu-id="5f29b-772">Изменение командной строки</span><span class="sxs-lookup"><span data-stu-id="5f29b-772">edit the command line</span></span>
- <span data-ttu-id="5f29b-773">Открытие нового окна (например, Справка)</span><span class="sxs-lookup"><span data-stu-id="5f29b-773">opening a new window (e.g. help)</span></span>
- <span data-ttu-id="5f29b-774">Изменение каталогов без изменения командной строки</span><span class="sxs-lookup"><span data-stu-id="5f29b-774">change directories without changing the command line</span></span>

<span data-ttu-id="5f29b-775">Блок ScriptBlock получает два аргумента:</span><span class="sxs-lookup"><span data-stu-id="5f29b-775">The ScriptBlock receives two arguments:</span></span>

- <span data-ttu-id="5f29b-776">`$key` — Объект **[консолекэйинфо]** , который является ключом, запускающим пользовательскую привязку.</span><span class="sxs-lookup"><span data-stu-id="5f29b-776">`$key` - A **[ConsoleKeyInfo]** object that is the key that triggered the custom binding.</span></span> <span data-ttu-id="5f29b-777">Если один и тот же блок сценария привязан к нескольким ключам и необходимо выполнять различные действия в зависимости от ключа, можно проверить $key.</span><span class="sxs-lookup"><span data-stu-id="5f29b-777">If you bind the same ScriptBlock to multiple keys and need to perform different actions depending on the key, you can check $key.</span></span> <span data-ttu-id="5f29b-778">Многие пользовательские привязки игнорируют этот аргумент.</span><span class="sxs-lookup"><span data-stu-id="5f29b-778">Many custom bindings ignore this argument.</span></span>

- <span data-ttu-id="5f29b-779">`$arg` — Произвольный аргумент.</span><span class="sxs-lookup"><span data-stu-id="5f29b-779">`$arg` - An arbitrary argument.</span></span> <span data-ttu-id="5f29b-780">Чаще всего это будет целочисленный аргумент, который пользователь передает из ключевых привязок Дигитаргумент.</span><span class="sxs-lookup"><span data-stu-id="5f29b-780">Most often, this would be an integer argument that the user passes from the key bindings DigitArgument.</span></span> <span data-ttu-id="5f29b-781">Если привязка не принимает аргументы, целесообразно проигнорировать этот аргумент.</span><span class="sxs-lookup"><span data-stu-id="5f29b-781">If your binding doesn't accept arguments, it's reasonable to ignore this argument.</span></span>

<span data-ttu-id="5f29b-782">Рассмотрим пример, который добавляет в журнал командную строку, не выполняя ее.</span><span class="sxs-lookup"><span data-stu-id="5f29b-782">Let's take a look at an example that adds a command line to history without executing it.</span></span> <span data-ttu-id="5f29b-783">Это полезно, если вы забыли сделать что-то, но не хотите повторно вводить уже введенную командную строку.</span><span class="sxs-lookup"><span data-stu-id="5f29b-783">This is useful when you realize you forgot to do something, but don't want to re-enter the command line you've already entered.</span></span>

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

<span data-ttu-id="5f29b-784">В файле, `SamplePSReadLineProfile.ps1` который устанавливается в папку модуля PSReadLine, можно увидеть много других примеров.</span><span class="sxs-lookup"><span data-stu-id="5f29b-784">You can see many more examples in the file `SamplePSReadLineProfile.ps1` which is installed in the PSReadLine module folder.</span></span>

<span data-ttu-id="5f29b-785">Большинство ключевых привязок используют некоторые вспомогательные функции для редактирования командной строки.</span><span class="sxs-lookup"><span data-stu-id="5f29b-785">Most key bindings use some helper functions for editing the command line.</span></span>
<span data-ttu-id="5f29b-786">Эти API-интерфейсы описаны в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="5f29b-786">Those APIs are documented in the next section.</span></span>

## <a name="custom-key-binding-support-apis"></a><span data-ttu-id="5f29b-787">API поддержки пользовательского сочетания клавиш</span><span class="sxs-lookup"><span data-stu-id="5f29b-787">Custom Key Binding Support APIs</span></span>

<span data-ttu-id="5f29b-788">Следующие функции являются открытыми в Microsoft. PowerShell. Псконсолереадлине, но не могут быть напрямую привязаны к ключу.</span><span class="sxs-lookup"><span data-stu-id="5f29b-788">The following functions are public in Microsoft.PowerShell.PSConsoleReadLine, but cannot be directly bound to a key.</span></span> <span data-ttu-id="5f29b-789">Большинство из них удобно использовать в пользовательских привязках клавиш.</span><span class="sxs-lookup"><span data-stu-id="5f29b-789">Most are useful in custom key bindings.</span></span>

```csharp
void AddToHistory(string command)
```

<span data-ttu-id="5f29b-790">Добавьте командную строку в журнал, не выполняя ее.</span><span class="sxs-lookup"><span data-stu-id="5f29b-790">Add a command line to history without executing it.</span></span>

```csharp
void ClearKillRing()
```

<span data-ttu-id="5f29b-791">Снимите флажок Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="5f29b-791">Clear the kill-ring.</span></span>  <span data-ttu-id="5f29b-792">Это в основном используется для тестирования.</span><span class="sxs-lookup"><span data-stu-id="5f29b-792">This is mostly used for testing.</span></span>

```csharp
void Delete(int start, int length)
```

<span data-ttu-id="5f29b-793">Удалить символы длины из Start.</span><span class="sxs-lookup"><span data-stu-id="5f29b-793">Delete length characters from start.</span></span>  <span data-ttu-id="5f29b-794">Эта операция поддерживает операцию отмены и повтора.</span><span class="sxs-lookup"><span data-stu-id="5f29b-794">This operation supports undo/redo.</span></span>

```csharp
void Ding()
```

<span data-ttu-id="5f29b-795">Выполните действие DING, основанное на предпочтениях пользователей.</span><span class="sxs-lookup"><span data-stu-id="5f29b-795">Perform the Ding action based on the users preference.</span></span>

```csharp
void GetBufferState([ref] string input, [ref] int cursor)
void GetBufferState([ref] Ast ast, [ref] Token[] tokens,
  [ref] ParseError[] parseErrors, [ref] int cursor)
```

<span data-ttu-id="5f29b-796">Эти две функции извлекают полезную информацию о текущем состоянии входного буфера.</span><span class="sxs-lookup"><span data-stu-id="5f29b-796">These two functions retrieve useful information about the current state of the input buffer.</span></span>  <span data-ttu-id="5f29b-797">Первый из них чаще всего используется в простых случаях.</span><span class="sxs-lookup"><span data-stu-id="5f29b-797">The first is more commonly used for simple cases.</span></span>  <span data-ttu-id="5f29b-798">Второй используется, если привязка делает что-то более сложное с AST.</span><span class="sxs-lookup"><span data-stu-id="5f29b-798">The second is used if your binding is doing something more advanced with the Ast.</span></span>

```csharp
IEnumerable[Microsoft.PowerShell.KeyHandler]
  GetKeyHandlers(bool includeBound, bool includeUnbound)

```

<span data-ttu-id="5f29b-799">Эта функция используется Get-PSReadLineKeyHandler и, возможно, не полезна в пользовательской привязке ключа.</span><span class="sxs-lookup"><span data-stu-id="5f29b-799">This function is used by Get-PSReadLineKeyHandler and probably isn't useful in a custom key binding.</span></span>

```csharp
Microsoft.PowerShell.PSConsoleReadLineOptions GetOptions()
```

<span data-ttu-id="5f29b-800">Эта функция используется Get-PSReadLineOption и, возможно, не слишком полезна в пользовательской привязке ключа.</span><span class="sxs-lookup"><span data-stu-id="5f29b-800">This function is used by Get-PSReadLineOption and probably isn't too useful in a custom key binding.</span></span>

```csharp
void GetSelectionState([ref] int start, [ref] int length)
```

<span data-ttu-id="5f29b-801">Если в командной строке ничего не выбрано, значение-1 будет возвращено как в начале, так и в длине.</span><span class="sxs-lookup"><span data-stu-id="5f29b-801">If there is no selection on the command line, -1 will be returned in both start and length.</span></span> <span data-ttu-id="5f29b-802">Если в командной строке имеется выделенный фрагмент, то начинается и длина выбора возвращается.</span><span class="sxs-lookup"><span data-stu-id="5f29b-802">If there is a selection on the command line, the start and length of the selection are returned.</span></span>

```csharp
void Insert(char c)
void Insert(string s)
```

<span data-ttu-id="5f29b-803">Вставка символа или строки в курсоре.</span><span class="sxs-lookup"><span data-stu-id="5f29b-803">Insert a character or string at the cursor.</span></span>  <span data-ttu-id="5f29b-804">Эта операция поддерживает операцию отмены и повтора.</span><span class="sxs-lookup"><span data-stu-id="5f29b-804">This operation supports undo/redo.</span></span>

```csharp
string ReadLine(runspace remoteRunspace,
  System.Management.Automation.EngineIntrinsics engineIntrinsics)
```

<span data-ttu-id="5f29b-805">Это Главная точка входа для PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="5f29b-805">This is the main entry point to PSReadLine.</span></span> <span data-ttu-id="5f29b-806">Она не поддерживает рекурсию, поэтому она не полезна в пользовательской привязке ключа.</span><span class="sxs-lookup"><span data-stu-id="5f29b-806">It does not support recursion, so is not useful in a custom key binding.</span></span>

```csharp
void RemoveKeyHandler(string[] key)
```

<span data-ttu-id="5f29b-807">Эта функция используется Remove-PSReadLineKeyHandler и, возможно, не слишком полезна в пользовательской привязке ключа.</span><span class="sxs-lookup"><span data-stu-id="5f29b-807">This function is used by Remove-PSReadLineKeyHandler and probably isn't too useful in a custom key binding.</span></span>

```csharp
void Replace(int start, int length, string replacement)
```

<span data-ttu-id="5f29b-808">Замените некоторые входные данные.</span><span class="sxs-lookup"><span data-stu-id="5f29b-808">Replace some of the input.</span></span> <span data-ttu-id="5f29b-809">Эта операция поддерживает операцию отмены и повтора.</span><span class="sxs-lookup"><span data-stu-id="5f29b-809">This operation supports undo/redo.</span></span> <span data-ttu-id="5f29b-810">Это предпочтительнее удаление с последующим вставкой, так как оно обрабатывается как одно действие для отмены.</span><span class="sxs-lookup"><span data-stu-id="5f29b-810">This is preferred over Delete followed by Insert because it is treated as a single action for undo.</span></span>

```csharp
void SetCursorPosition(int cursor)
```

<span data-ttu-id="5f29b-811">Переместить курсор к заданному смещению.</span><span class="sxs-lookup"><span data-stu-id="5f29b-811">Move the cursor to the given offset.</span></span> <span data-ttu-id="5f29b-812">Перемещение курсора не ведется для отмены.</span><span class="sxs-lookup"><span data-stu-id="5f29b-812">Cursor movement is not tracked for undo.</span></span>

```csharp
void SetOptions(Microsoft.PowerShell.SetPSReadLineOption options)
```

<span data-ttu-id="5f29b-813">Эта функция является вспомогательным методом, используемым командлетом Set-PSReadLineOption, но может быть полезен для пользовательской привязки ключа, которая хочет временно изменить параметр.</span><span class="sxs-lookup"><span data-stu-id="5f29b-813">This function is a helper method used by the cmdlet Set-PSReadLineOption, but might be useful to a custom key binding that wants to temporarily change a setting.</span></span>

```csharp
bool TryGetArgAsInt(System.Object arg, [ref] int numericArg,
  int defaultNumericArg)
```

<span data-ttu-id="5f29b-814">Этот вспомогательный метод используется для пользовательских привязок, которые учитывают Дигитаргумент.</span><span class="sxs-lookup"><span data-stu-id="5f29b-814">This helper method is used for custom bindings that honor DigitArgument.</span></span> <span data-ttu-id="5f29b-815">Обычный вызов выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="5f29b-815">A typical call looks like</span></span>

```powershell
[int]$numericArg = 0
[Microsoft.PowerShell.PSConsoleReadLine]::TryGetArgAsInt($arg,
  [ref]$numericArg, 1)
```

## <a name="note"></a><span data-ttu-id="5f29b-816">Примечание</span><span class="sxs-lookup"><span data-stu-id="5f29b-816">Note</span></span>

### <a name="command-history"></a><span data-ttu-id="5f29b-817">Журнал команд</span><span class="sxs-lookup"><span data-stu-id="5f29b-817">Command History</span></span>

<span data-ttu-id="5f29b-818">PSReadLine поддерживает файл журнала, содержащий все команды и данные, введенные из командной строки.</span><span class="sxs-lookup"><span data-stu-id="5f29b-818">PSReadLine maintains a history file containing all the commands and data you have entered from the command line.</span></span> <span data-ttu-id="5f29b-819">Это может быть конфиденциальные данные, включая пароли.</span><span class="sxs-lookup"><span data-stu-id="5f29b-819">This may contain sensitive data including passwords.</span></span> <span data-ttu-id="5f29b-820">Например, при использовании `ConvertTo-SecureString` командлета пароль заносится в файл журнала в виде обычного текста.</span><span class="sxs-lookup"><span data-stu-id="5f29b-820">For example, if you use the `ConvertTo-SecureString` cmdlet the password is logged in the history file as plain text.</span></span> <span data-ttu-id="5f29b-821">Файлы журнала — это файл с именем `$($host.Name)_history.txt` .</span><span class="sxs-lookup"><span data-stu-id="5f29b-821">The history files is a file named `$($host.Name)_history.txt`.</span></span> <span data-ttu-id="5f29b-822">В системах Windows файл журнала хранится в файле `$env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine` .</span><span class="sxs-lookup"><span data-stu-id="5f29b-822">On Windows systems the history file is stored at `$env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine`.</span></span> <span data-ttu-id="5f29b-823">В системах, отличных от Windows, файлы журнала хранятся в `$env:XDG_DATA_HOME/powershell/PSReadLine` или `$env:HOME/.local/share/powershell/PSReadLine` .</span><span class="sxs-lookup"><span data-stu-id="5f29b-823">On non-Windows systems, the history files is stored at `$env:XDG_DATA_HOME/powershell/PSReadLine` or `$env:HOME/.local/share/powershell/PSReadLine`.</span></span>

### <a name="feedback--contributing-to-psreadline"></a><span data-ttu-id="5f29b-824">Обратная связь & участие в PSReadLine</span><span class="sxs-lookup"><span data-stu-id="5f29b-824">Feedback & Contributing To PSReadLine</span></span>

[<span data-ttu-id="5f29b-825">PSReadLine на GitHub</span><span class="sxs-lookup"><span data-stu-id="5f29b-825">PSReadLine on GitHub</span></span>](https://github.com/PowerShell/PSReadLine)

<span data-ttu-id="5f29b-826">Вы можете отправить запрос на вытягивание или отправить отзыв на страницу GitHub.</span><span class="sxs-lookup"><span data-stu-id="5f29b-826">Feel free to submit a pull request or submit feedback on the GitHub page.</span></span>

## <a name="see-also"></a><span data-ttu-id="5f29b-827">См. также:</span><span class="sxs-lookup"><span data-stu-id="5f29b-827">See Also</span></span>

<span data-ttu-id="5f29b-828">На PSReadLine сильно влияют библиотеки GNU [ReadLine](https://tiswww.case.edu/php/chet/readline/rltop.html) .</span><span class="sxs-lookup"><span data-stu-id="5f29b-828">PSReadLine is heavily influenced by the GNU [readline](https://tiswww.case.edu/php/chet/readline/rltop.html) library.</span></span>
