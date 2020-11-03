---
description: PSReadLine предоставляет улучшенные возможности редактирования командной строки в консоли PowerShell.
keywords: powershell
Locale: en-US
ms.date: 02/10/2020
online version: https://docs.microsoft.com/powershell/module/psreadline/about/about_psreadline?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: О PSReadLine
ms.openlocfilehash: 1188b8dc0b4099a7c1dcc472e3b02c2d4fa908bc
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231069"
---
# <a name="psreadline"></a><span data-ttu-id="bda18-104">PSReadLine</span><span class="sxs-lookup"><span data-stu-id="bda18-104">PSReadLine</span></span>

## <a name="about_psreadline"></a><span data-ttu-id="bda18-105">about_PSReadLine</span><span class="sxs-lookup"><span data-stu-id="bda18-105">about_PSReadLine</span></span>

## <a name="short-description"></a><span data-ttu-id="bda18-106">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="bda18-106">SHORT DESCRIPTION</span></span>

<span data-ttu-id="bda18-107">PSReadLine предоставляет улучшенные возможности редактирования командной строки в консоли PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bda18-107">PSReadLine provides an improved command-line editing experience in the PowerShell console.</span></span>

## <a name="long-description"></a><span data-ttu-id="bda18-108">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="bda18-108">LONG DESCRIPTION</span></span>

<span data-ttu-id="bda18-109">PSReadLine 2,0 предоставляет широкие возможности редактирования командной строки для консоли PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bda18-109">PSReadLine 2.0 provides a powerful command-line editing experience for the PowerShell console.</span></span> <span data-ttu-id="bda18-110">Консоль предоставляет следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="bda18-110">It provides:</span></span>

- <span data-ttu-id="bda18-111">Цветовое выделение синтаксиса командной строки</span><span class="sxs-lookup"><span data-stu-id="bda18-111">Syntax coloring of the command line</span></span>
- <span data-ttu-id="bda18-112">Визуальное обозначение синтаксических ошибок</span><span class="sxs-lookup"><span data-stu-id="bda18-112">A visual indication of syntax errors</span></span>
- <span data-ttu-id="bda18-113">Более эффективный многострочный интерфейс (как редактирование, так и журнал)</span><span class="sxs-lookup"><span data-stu-id="bda18-113">A better multi-line experience (both editing and history)</span></span>
- <span data-ttu-id="bda18-114">Настраиваемые сочетания клавиш</span><span class="sxs-lookup"><span data-stu-id="bda18-114">Customizable key bindings</span></span>
- <span data-ttu-id="bda18-115">Режимы работы cmd и Emacs</span><span class="sxs-lookup"><span data-stu-id="bda18-115">Cmd and Emacs modes</span></span>
- <span data-ttu-id="bda18-116">Множество параметров конфигурации</span><span class="sxs-lookup"><span data-stu-id="bda18-116">Many configuration options</span></span>
- <span data-ttu-id="bda18-117">Завершение стиля bash (необязательно в режиме cmd, по умолчанию в режиме Emacs)</span><span class="sxs-lookup"><span data-stu-id="bda18-117">Bash style completion (optional in Cmd mode, default in Emacs mode)</span></span>
- <span data-ttu-id="bda18-118">Emacs: Янк/Kill-Ring</span><span class="sxs-lookup"><span data-stu-id="bda18-118">Emacs yank/kill-ring</span></span>
- <span data-ttu-id="bda18-119">Перемещение и уничтожение токена PowerShell на основе маркеров "Word"</span><span class="sxs-lookup"><span data-stu-id="bda18-119">PowerShell token based "word" movement and kill</span></span>

<span data-ttu-id="bda18-120">В классе **[Microsoft. PowerShell. псконсолереадлине]** доступны следующие функции.</span><span class="sxs-lookup"><span data-stu-id="bda18-120">The following functions are available in the class **[Microsoft.PowerShell.PSConsoleReadLine]**.</span></span>

> [!NOTE]
> <span data-ttu-id="bda18-121">Начиная с PowerShell 7,0, PowerShell пропускает автоматическую загрузку PSReadLine в Windows при обнаружении программы чтения с экрана.</span><span class="sxs-lookup"><span data-stu-id="bda18-121">Beginning with PowerShell 7.0, PowerShell skips auto-loading PSReadLine on Windows if a screen reader program is detected.</span></span> <span data-ttu-id="bda18-122">В настоящее время PSReadLine плохо работает с программами чтения с экрана.</span><span class="sxs-lookup"><span data-stu-id="bda18-122">Currently, PSReadLine doesn't work well with the screen readers.</span></span> <span data-ttu-id="bda18-123">Визуализация и форматирование по умолчанию для PowerShell 7,0 в Windows работают правильно.</span><span class="sxs-lookup"><span data-stu-id="bda18-123">The default rendering and formatting of PowerShell 7.0 on Windows works properly.</span></span> <span data-ttu-id="bda18-124">При необходимости модуль можно загрузить вручную.</span><span class="sxs-lookup"><span data-stu-id="bda18-124">You can manually load the module if necessary.</span></span>

## <a name="basic-editing-functions"></a><span data-ttu-id="bda18-125">Базовые функции редактирования</span><span class="sxs-lookup"><span data-stu-id="bda18-125">Basic editing functions</span></span>

### <a name="abort"></a><span data-ttu-id="bda18-126">Прерывание</span><span class="sxs-lookup"><span data-stu-id="bda18-126">Abort</span></span>

<span data-ttu-id="bda18-127">Прервать текущее действие, например добавочный поиск по журналу.</span><span class="sxs-lookup"><span data-stu-id="bda18-127">Abort current action, e.g. incremental history search.</span></span>

- <span data-ttu-id="bda18-128">Emacs: `<Ctrl+g>`</span><span class="sxs-lookup"><span data-stu-id="bda18-128">Emacs: `<Ctrl+g>`</span></span>

### <a name="acceptandgetnext"></a><span data-ttu-id="bda18-129">акцептанджетнекст</span><span class="sxs-lookup"><span data-stu-id="bda18-129">AcceptAndGetNext</span></span>

<span data-ttu-id="bda18-130">Попытка выполнить текущий вход.</span><span class="sxs-lookup"><span data-stu-id="bda18-130">Attempt to execute the current input.</span></span> <span data-ttu-id="bda18-131">Если его можно выполнить (например, Акцептлине), то следует отозвать следующий элемент из журнала при следующем вызове метода ReadLine.</span><span class="sxs-lookup"><span data-stu-id="bda18-131">If it can be executed (like AcceptLine), then recall the next item from history the next time ReadLine is called.</span></span>

- <span data-ttu-id="bda18-132">Emacs: `<Ctrl+o>`</span><span class="sxs-lookup"><span data-stu-id="bda18-132">Emacs: `<Ctrl+o>`</span></span>

### <a name="acceptline"></a><span data-ttu-id="bda18-133">акцептлине</span><span class="sxs-lookup"><span data-stu-id="bda18-133">AcceptLine</span></span>

<span data-ttu-id="bda18-134">Попытка выполнить текущий вход.</span><span class="sxs-lookup"><span data-stu-id="bda18-134">Attempt to execute the current input.</span></span> <span data-ttu-id="bda18-135">Если текущий ввод неполон (например, отсутствует закрывающая круглая скобка, квадратная скобка или кавычка, запрос продолжения отображается на следующей строке, а PSReadLine ожидает ввода ключей для изменения текущих входных данных.</span><span class="sxs-lookup"><span data-stu-id="bda18-135">If the current input is incomplete (for example there is a missing closing parenthesis, bracket, or quote, then the continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span>

- <span data-ttu-id="bda18-136">Процессор `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="bda18-136">Cmd: `<Enter>`</span></span>
- <span data-ttu-id="bda18-137">Emacs: `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="bda18-137">Emacs: `<Enter>`</span></span>
- <span data-ttu-id="bda18-138">Режим вставки в VI: `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="bda18-138">Vi insert mode: `<Enter>`</span></span>

### <a name="addline"></a><span data-ttu-id="bda18-139">аддлине</span><span class="sxs-lookup"><span data-stu-id="bda18-139">AddLine</span></span>

<span data-ttu-id="bda18-140">Запрос продолжения отображается на следующей строке, а PSReadLine ожидает ввода ключей для изменения текущих входных данных.</span><span class="sxs-lookup"><span data-stu-id="bda18-140">The continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span> <span data-ttu-id="bda18-141">Это полезно для ввода многострочных входных данных в виде одной команды, даже если одна строка завершается самим вводом.</span><span class="sxs-lookup"><span data-stu-id="bda18-141">This is useful to enter multi-line input as a single command even when a single line is complete input by itself.</span></span>

- <span data-ttu-id="bda18-142">Процессор `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="bda18-142">Cmd: `<Shift+Enter>`</span></span>
- <span data-ttu-id="bda18-143">Emacs: `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="bda18-143">Emacs: `<Shift+Enter>`</span></span>
- <span data-ttu-id="bda18-144">Режим вставки в VI: `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="bda18-144">Vi insert mode: `<Shift+Enter>`</span></span>
- <span data-ttu-id="bda18-145">Режим команд VI: `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="bda18-145">Vi command mode: `<Shift+Enter>`</span></span>

### <a name="backwarddeletechar"></a><span data-ttu-id="bda18-146">бакквардделетечар</span><span class="sxs-lookup"><span data-stu-id="bda18-146">BackwardDeleteChar</span></span>

<span data-ttu-id="bda18-147">Удалить символ перед курсором.</span><span class="sxs-lookup"><span data-stu-id="bda18-147">Delete the character before the cursor.</span></span>

- <span data-ttu-id="bda18-148">Cmd: `<Backspace>` , `<Ctrl+h>`</span><span class="sxs-lookup"><span data-stu-id="bda18-148">Cmd: `<Backspace>`, `<Ctrl+h>`</span></span>
- <span data-ttu-id="bda18-149">Emacs: `<Backspace>` , `<Ctrl+Backspace>` , `<Ctrl+h>`</span><span class="sxs-lookup"><span data-stu-id="bda18-149">Emacs: `<Backspace>`, `<Ctrl+Backspace>`, `<Ctrl+h>`</span></span>
- <span data-ttu-id="bda18-150">Режим вставки в VI: `<Backspace>`</span><span class="sxs-lookup"><span data-stu-id="bda18-150">Vi insert mode: `<Backspace>`</span></span>
- <span data-ttu-id="bda18-151">Режим команд VI: `<X>` , `<d,h>`</span><span class="sxs-lookup"><span data-stu-id="bda18-151">Vi command mode: `<X>`, `<d,h>`</span></span>

### <a name="backwarddeleteline"></a><span data-ttu-id="bda18-152">бакквардделетелине</span><span class="sxs-lookup"><span data-stu-id="bda18-152">BackwardDeleteLine</span></span>

<span data-ttu-id="bda18-153">Like Бакквардкилллине — удаляет текст с точки до начала строки, но не помещает удаленный текст в инструкцию KILL-Ring.</span><span class="sxs-lookup"><span data-stu-id="bda18-153">Like BackwardKillLine - deletes text from the point to the start of the line, but does not put the deleted text in the kill-ring.</span></span>

- <span data-ttu-id="bda18-154">Процессор `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="bda18-154">Cmd: `<Ctrl+Home>`</span></span>
- <span data-ttu-id="bda18-155">Режим вставки в VI: `<Ctrl+u>` , `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="bda18-155">Vi insert mode: `<Ctrl+u>`, `<Ctrl+Home>`</span></span>
- <span data-ttu-id="bda18-156">Режим команд VI: `<Ctrl+u>` , `<Ctrl+Home>` , `<d,0>`</span><span class="sxs-lookup"><span data-stu-id="bda18-156">Vi command mode: `<Ctrl+u>`, `<Ctrl+Home>`, `<d,0>`</span></span>

### <a name="backwarddeleteword"></a><span data-ttu-id="bda18-157">бакквардделетеворд</span><span class="sxs-lookup"><span data-stu-id="bda18-157">BackwardDeleteWord</span></span>

<span data-ttu-id="bda18-158">Удаляет предыдущее слово.</span><span class="sxs-lookup"><span data-stu-id="bda18-158">Deletes the previous word.</span></span>

- <span data-ttu-id="bda18-159">Режим команд VI: `<Ctrl+w>` , `<d,b>`</span><span class="sxs-lookup"><span data-stu-id="bda18-159">Vi command mode: `<Ctrl+w>`, `<d,b>`</span></span>

### <a name="backwardkillline"></a><span data-ttu-id="bda18-160">бакквардкилллине</span><span class="sxs-lookup"><span data-stu-id="bda18-160">BackwardKillLine</span></span>

<span data-ttu-id="bda18-161">Очистить входные данные от начала ввода до курсора.</span><span class="sxs-lookup"><span data-stu-id="bda18-161">Clear the input from the start of the input to the cursor.</span></span> <span data-ttu-id="bda18-162">Очистка текста помещается в буфер Kill.</span><span class="sxs-lookup"><span data-stu-id="bda18-162">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="bda18-163">Emacs: `<Ctrl+u>` , `<Ctrl+x,Backspace>`</span><span class="sxs-lookup"><span data-stu-id="bda18-163">Emacs: `<Ctrl+u>`, `<Ctrl+x,Backspace>`</span></span>

### <a name="backwardkillword"></a><span data-ttu-id="bda18-164">бакквардкиллворд</span><span class="sxs-lookup"><span data-stu-id="bda18-164">BackwardKillWord</span></span>

<span data-ttu-id="bda18-165">Очистить ввод от начала текущего слова до курсора.</span><span class="sxs-lookup"><span data-stu-id="bda18-165">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="bda18-166">Если курсор находится между словами, входные данные очищаются от начала предыдущего слова до курсора.</span><span class="sxs-lookup"><span data-stu-id="bda18-166">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="bda18-167">Очистка текста помещается в буфер Kill.</span><span class="sxs-lookup"><span data-stu-id="bda18-167">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="bda18-168">Cmd: `<Ctrl+Backspace>` , `<Ctrl+w>`</span><span class="sxs-lookup"><span data-stu-id="bda18-168">Cmd: `<Ctrl+Backspace>`, `<Ctrl+w>`</span></span>
- <span data-ttu-id="bda18-169">Emacs: `<Alt+Backspace>` , `<Escape,Backspace>`</span><span class="sxs-lookup"><span data-stu-id="bda18-169">Emacs: `<Alt+Backspace>`, `<Escape,Backspace>`</span></span>
- <span data-ttu-id="bda18-170">Режим вставки в VI: `<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="bda18-170">Vi insert mode: `<Ctrl+Backspace>`</span></span>
- <span data-ttu-id="bda18-171">Режим команд VI: `<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="bda18-171">Vi command mode: `<Ctrl+Backspace>`</span></span>

### <a name="cancelline"></a><span data-ttu-id="bda18-172">канцеллине</span><span class="sxs-lookup"><span data-stu-id="bda18-172">CancelLine</span></span>

<span data-ttu-id="bda18-173">Отмена текущих входных данных с выходом на экран, но возврат к узлу, чтобы снова выполнить оценку запроса.</span><span class="sxs-lookup"><span data-stu-id="bda18-173">Cancel the current input, leaving the input on the screen, but returns back to the host so the prompt is evaluated again.</span></span>

- <span data-ttu-id="bda18-174">Режим вставки в VI: `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="bda18-174">Vi insert mode: `<Ctrl+c>`</span></span>
- <span data-ttu-id="bda18-175">Режим команд VI: `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="bda18-175">Vi command mode: `<Ctrl+c>`</span></span>

### <a name="copy"></a><span data-ttu-id="bda18-176">Копировать</span><span class="sxs-lookup"><span data-stu-id="bda18-176">Copy</span></span>

<span data-ttu-id="bda18-177">Копировать выбранный регион в буфер обмена системы.</span><span class="sxs-lookup"><span data-stu-id="bda18-177">Copy selected region to the system clipboard.</span></span> <span data-ttu-id="bda18-178">Если регион не выбран, скопируйте всю строку.</span><span class="sxs-lookup"><span data-stu-id="bda18-178">If no region is selected, copy the whole line.</span></span>

- <span data-ttu-id="bda18-179">Процессор `<Ctrl+C>`</span><span class="sxs-lookup"><span data-stu-id="bda18-179">Cmd: `<Ctrl+C>`</span></span>

### <a name="copyorcancelline"></a><span data-ttu-id="bda18-180">копйорканцеллине</span><span class="sxs-lookup"><span data-stu-id="bda18-180">CopyOrCancelLine</span></span>

<span data-ttu-id="bda18-181">Если выбран текст, скопируйте в буфер обмена, в противном случае отмените строку.</span><span class="sxs-lookup"><span data-stu-id="bda18-181">If text is selected, copy to the clipboard, otherwise cancel the line.</span></span>

- <span data-ttu-id="bda18-182">Процессор `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="bda18-182">Cmd: `<Ctrl+c>`</span></span>
- <span data-ttu-id="bda18-183">Emacs: `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="bda18-183">Emacs: `<Ctrl+c>`</span></span>

### <a name="cut"></a><span data-ttu-id="bda18-184">Вырезать</span><span class="sxs-lookup"><span data-stu-id="bda18-184">Cut</span></span>

<span data-ttu-id="bda18-185">Удалить выбранный регион, поместив удаленный текст в системный буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="bda18-185">Delete selected region placing deleted text in the system clipboard.</span></span>

- <span data-ttu-id="bda18-186">Процессор `<Ctrl+x>`</span><span class="sxs-lookup"><span data-stu-id="bda18-186">Cmd: `<Ctrl+x>`</span></span>

### <a name="deletechar"></a><span data-ttu-id="bda18-187">делетечар</span><span class="sxs-lookup"><span data-stu-id="bda18-187">DeleteChar</span></span>

<span data-ttu-id="bda18-188">Удалите символ под курсором.</span><span class="sxs-lookup"><span data-stu-id="bda18-188">Delete the character under the cursor.</span></span>

- <span data-ttu-id="bda18-189">Процессор `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="bda18-189">Cmd: `<Delete>`</span></span>
- <span data-ttu-id="bda18-190">Emacs: `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="bda18-190">Emacs: `<Delete>`</span></span>
- <span data-ttu-id="bda18-191">Режим вставки в VI: `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="bda18-191">Vi insert mode: `<Delete>`</span></span>
- <span data-ttu-id="bda18-192">Режим команд VI: `<Delete>` , `<x>` , `<d,l>` , `<d,Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="bda18-192">Vi command mode: `<Delete>`, `<x>`, `<d,l>`, `<d,Spacebar>`</span></span>

### <a name="deletecharorexit"></a><span data-ttu-id="bda18-193">делетечарорексит</span><span class="sxs-lookup"><span data-stu-id="bda18-193">DeleteCharOrExit</span></span>

<span data-ttu-id="bda18-194">Удалите символ под курсором или, если строка пуста, завершите процесс.</span><span class="sxs-lookup"><span data-stu-id="bda18-194">Delete the character under the cursor, or if the line is empty, exit the process.</span></span>

- <span data-ttu-id="bda18-195">Emacs: `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="bda18-195">Emacs: `<Ctrl+d>`</span></span>

### <a name="deleteendofbuffer"></a><span data-ttu-id="bda18-196">делетиндофбуффер</span><span class="sxs-lookup"><span data-stu-id="bda18-196">DeleteEndOfBuffer</span></span>

<span data-ttu-id="bda18-197">Удаляет до конца многострочного буфера.</span><span class="sxs-lookup"><span data-stu-id="bda18-197">Deletes to the end of the multiline buffer.</span></span>

- <span data-ttu-id="bda18-198">Режим команд VI: `<d,G>`</span><span class="sxs-lookup"><span data-stu-id="bda18-198">Vi command mode: `<d,G>`</span></span>

### <a name="deleteendofword"></a><span data-ttu-id="bda18-199">делетиндофворд</span><span class="sxs-lookup"><span data-stu-id="bda18-199">DeleteEndOfWord</span></span>

<span data-ttu-id="bda18-200">Удалить до конца слова.</span><span class="sxs-lookup"><span data-stu-id="bda18-200">Delete to the end of the word.</span></span>

- <span data-ttu-id="bda18-201">Режим команд VI: `<d,e>`</span><span class="sxs-lookup"><span data-stu-id="bda18-201">Vi command mode: `<d,e>`</span></span>

### <a name="deleteline"></a><span data-ttu-id="bda18-202">Сбой deleteline</span><span class="sxs-lookup"><span data-stu-id="bda18-202">DeleteLine</span></span>

<span data-ttu-id="bda18-203">Удаляет текущую логическую строку многострочного буфера, включая отмену.</span><span class="sxs-lookup"><span data-stu-id="bda18-203">Deletes the current logical line of a multiline buffer, enabling undo.</span></span>

- <span data-ttu-id="bda18-204">Режим команд VI: `<d,d>` , `<d,_>`</span><span class="sxs-lookup"><span data-stu-id="bda18-204">Vi command mode: `<d,d>`, `<d,_>`</span></span>

### <a name="deletepreviouslines"></a><span data-ttu-id="bda18-205">делетепревиауслинес</span><span class="sxs-lookup"><span data-stu-id="bda18-205">DeletePreviousLines</span></span>

<span data-ttu-id="bda18-206">Удаляет предыдущие запрошенные логические строки и текущую логическую строку в многострочном буфере.</span><span class="sxs-lookup"><span data-stu-id="bda18-206">Deletes the previous requested logical lines and the current logical line in a multiline buffer.</span></span>

- <span data-ttu-id="bda18-207">Режим команд VI: `<d,k>`</span><span class="sxs-lookup"><span data-stu-id="bda18-207">Vi command mode: `<d,k>`</span></span>

### <a name="deleterelativelines"></a><span data-ttu-id="bda18-208">делетерелативелинес</span><span class="sxs-lookup"><span data-stu-id="bda18-208">DeleteRelativeLines</span></span>

<span data-ttu-id="bda18-209">Удаляет с начала буфера до текущей логической строки в многострочном буфере.</span><span class="sxs-lookup"><span data-stu-id="bda18-209">Deletes from the beginning of the buffer to the current logical line in a multiline buffer.</span></span>

<span data-ttu-id="bda18-210">Как и в большинстве команд VI, `<d,g,g>` команду можно добавить в начало с числовым аргументом, который указывает абсолютный номер строки, который вместе с текущим номером строки позволяет удалить диапазон строк.</span><span class="sxs-lookup"><span data-stu-id="bda18-210">As most Vi commands, the `<d,g,g>` command can be prepended with a numeric argument that specifies an absolute line number, which, together with the current line number, make up a range of lines to be deleted.</span></span>
<span data-ttu-id="bda18-211">Если не указано, числовой аргумент по умолчанию равен 1, что означает первую логическую строку в многострочном буфере.</span><span class="sxs-lookup"><span data-stu-id="bda18-211">If not specified, the numeric argument defaults to 1, which refers to the first logical line in a multiline buffer.</span></span>

<span data-ttu-id="bda18-212">Фактическое число строк, удаляемых из многострочного, вычисляются как разница между текущим логическим номером и заданным числовым аргументом, который, таким образом, может быть отрицательным.</span><span class="sxs-lookup"><span data-stu-id="bda18-212">The actual number of lines to be deleted from the multiline is computed as the difference between the current logical line number and the specified numeric argument, which can thus be negative.</span></span> <span data-ttu-id="bda18-213">Поэтому это _Относительная_ часть имени метода.</span><span class="sxs-lookup"><span data-stu-id="bda18-213">Hence the _relative_ part of method name.</span></span>

- <span data-ttu-id="bda18-214">Режим команд VI: `<d,g,g>`</span><span class="sxs-lookup"><span data-stu-id="bda18-214">Vi command mode: `<d,g,g>`</span></span>

### <a name="deletenextlines"></a><span data-ttu-id="bda18-215">делетенекстлинес</span><span class="sxs-lookup"><span data-stu-id="bda18-215">DeleteNextLines</span></span>

<span data-ttu-id="bda18-216">Удаляет текущую логическую строку и следующие запрошенные логические строки в многострочном буфере.</span><span class="sxs-lookup"><span data-stu-id="bda18-216">Deletes the current logical line and the next requested logical lines in a multiline buffer.</span></span>

- <span data-ttu-id="bda18-217">Режим команд VI: `<d,j>`</span><span class="sxs-lookup"><span data-stu-id="bda18-217">Vi command mode: `<d,j>`</span></span>

### <a name="deletelinetofirstchar"></a><span data-ttu-id="bda18-218">делетелинетофирстчар</span><span class="sxs-lookup"><span data-stu-id="bda18-218">DeleteLineToFirstChar</span></span>

<span data-ttu-id="bda18-219">Удаляет текст из курсора на первый символ строки, отличный от пробела.</span><span class="sxs-lookup"><span data-stu-id="bda18-219">Deletes text from the cursor to the first non-blank character of the line.</span></span>

- <span data-ttu-id="bda18-220">Режим команд VI: `<d,^>`</span><span class="sxs-lookup"><span data-stu-id="bda18-220">Vi command mode: `<d,^>`</span></span>

### <a name="deletetoend"></a><span data-ttu-id="bda18-221">делететоенд</span><span class="sxs-lookup"><span data-stu-id="bda18-221">DeleteToEnd</span></span>

<span data-ttu-id="bda18-222">Удалить до конца строки.</span><span class="sxs-lookup"><span data-stu-id="bda18-222">Delete to the end of the line.</span></span>

- <span data-ttu-id="bda18-223">Режим команд VI: `<D>` , `<d,$>`</span><span class="sxs-lookup"><span data-stu-id="bda18-223">Vi command mode: `<D>`, `<d,$>`</span></span>

### <a name="deleteword"></a><span data-ttu-id="bda18-224">DeleteWord</span><span class="sxs-lookup"><span data-stu-id="bda18-224">DeleteWord</span></span>

<span data-ttu-id="bda18-225">Удалить следующее слово.</span><span class="sxs-lookup"><span data-stu-id="bda18-225">Delete the next word.</span></span>

- <span data-ttu-id="bda18-226">Режим команд VI: `<d,w>`</span><span class="sxs-lookup"><span data-stu-id="bda18-226">Vi command mode: `<d,w>`</span></span>

### <a name="forwarddeleteline"></a><span data-ttu-id="bda18-227">форвардделетелине</span><span class="sxs-lookup"><span data-stu-id="bda18-227">ForwardDeleteLine</span></span>

<span data-ttu-id="bda18-228">Как и Форвардкилллине — удаляет текст с точки до конца строки, но не помещает удаленный текст в инструкцию KILL-Ring.</span><span class="sxs-lookup"><span data-stu-id="bda18-228">Like ForwardKillLine - deletes text from the point to the end of the line, but does not put the deleted text in the kill-ring.</span></span>

- <span data-ttu-id="bda18-229">Процессор `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="bda18-229">Cmd: `<Ctrl+End>`</span></span>
- <span data-ttu-id="bda18-230">Режим вставки в VI: `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="bda18-230">Vi insert mode: `<Ctrl+End>`</span></span>
- <span data-ttu-id="bda18-231">Режим команд VI: `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="bda18-231">Vi command mode: `<Ctrl+End>`</span></span>

### <a name="insertlineabove"></a><span data-ttu-id="bda18-232">инсертлинеабове</span><span class="sxs-lookup"><span data-stu-id="bda18-232">InsertLineAbove</span></span>

<span data-ttu-id="bda18-233">Новая пустая строка создается над текущей строкой, независимо от того, где находится курсор на текущей строке.</span><span class="sxs-lookup"><span data-stu-id="bda18-233">A new empty line is created above the current line regardless of where the cursor is on the current line.</span></span> <span data-ttu-id="bda18-234">Курсор переместится в начало новой строки.</span><span class="sxs-lookup"><span data-stu-id="bda18-234">The cursor moves to the beginning of the new line.</span></span>

- <span data-ttu-id="bda18-235">Процессор `<Ctrl+Enter>`</span><span class="sxs-lookup"><span data-stu-id="bda18-235">Cmd: `<Ctrl+Enter>`</span></span>

### <a name="insertlinebelow"></a><span data-ttu-id="bda18-236">инсертлинебелов</span><span class="sxs-lookup"><span data-stu-id="bda18-236">InsertLineBelow</span></span>

<span data-ttu-id="bda18-237">Новая пустая строка создается под текущей строкой независимо от того, где находится курсор на текущей строке.</span><span class="sxs-lookup"><span data-stu-id="bda18-237">A new empty line is created below the current line regardless of where the cursor is on the current line.</span></span> <span data-ttu-id="bda18-238">Курсор переместится в начало новой строки.</span><span class="sxs-lookup"><span data-stu-id="bda18-238">The cursor moves to the beginning of the new line.</span></span>

- <span data-ttu-id="bda18-239">Процессор `<Shift+Ctrl+Enter>`</span><span class="sxs-lookup"><span data-stu-id="bda18-239">Cmd: `<Shift+Ctrl+Enter>`</span></span>

### <a name="invertcase"></a><span data-ttu-id="bda18-240">инверткасе</span><span class="sxs-lookup"><span data-stu-id="bda18-240">InvertCase</span></span>

<span data-ttu-id="bda18-241">Инвертировать регистр текущего символа и перейти к следующему.</span><span class="sxs-lookup"><span data-stu-id="bda18-241">Invert the case of the current character and move to the next one.</span></span>

- <span data-ttu-id="bda18-242">Режим команд VI: `<~>`</span><span class="sxs-lookup"><span data-stu-id="bda18-242">Vi command mode: `<~>`</span></span>

### <a name="killline"></a><span data-ttu-id="bda18-243">килллине</span><span class="sxs-lookup"><span data-stu-id="bda18-243">KillLine</span></span>

<span data-ttu-id="bda18-244">Очистить входные данные от курсора до конца входных данных.</span><span class="sxs-lookup"><span data-stu-id="bda18-244">Clear the input from the cursor to the end of the input.</span></span> <span data-ttu-id="bda18-245">Очистка текста помещается в буфер Kill.</span><span class="sxs-lookup"><span data-stu-id="bda18-245">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="bda18-246">Emacs: `<Ctrl+k>`</span><span class="sxs-lookup"><span data-stu-id="bda18-246">Emacs: `<Ctrl+k>`</span></span>

### <a name="killregion"></a><span data-ttu-id="bda18-247">киллрегион</span><span class="sxs-lookup"><span data-stu-id="bda18-247">KillRegion</span></span>

<span data-ttu-id="bda18-248">Удалить текст между курсором и меткой.</span><span class="sxs-lookup"><span data-stu-id="bda18-248">Kill the text between the cursor and the mark.</span></span>

- <span data-ttu-id="bda18-249">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="bda18-249">Function is unbound.</span></span>

### <a name="killword"></a><span data-ttu-id="bda18-250">киллворд</span><span class="sxs-lookup"><span data-stu-id="bda18-250">KillWord</span></span>

<span data-ttu-id="bda18-251">Очистить ввод от курсора до конца текущего слова.</span><span class="sxs-lookup"><span data-stu-id="bda18-251">Clear the input from the cursor to the end of the current word.</span></span> <span data-ttu-id="bda18-252">Если курсор находится между словами, входные данные очищаются от курсора до конца следующего слова.</span><span class="sxs-lookup"><span data-stu-id="bda18-252">If the cursor is between words, the input is cleared from the cursor to the end of the next word.</span></span> <span data-ttu-id="bda18-253">Очистка текста помещается в буфер Kill.</span><span class="sxs-lookup"><span data-stu-id="bda18-253">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="bda18-254">Cmd: `<Alt+d>` , `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="bda18-254">Cmd: `<Alt+d>`, `<Ctrl+Delete>`</span></span>
- <span data-ttu-id="bda18-255">Emacs: `<Alt+d>` , `<Escape,d>`</span><span class="sxs-lookup"><span data-stu-id="bda18-255">Emacs: `<Alt+d>`, `<Escape,d>`</span></span>
- <span data-ttu-id="bda18-256">Режим вставки в VI: `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="bda18-256">Vi insert mode: `<Ctrl+Delete>`</span></span>
- <span data-ttu-id="bda18-257">Режим команд VI: `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="bda18-257">Vi command mode: `<Ctrl+Delete>`</span></span>

### <a name="paste"></a><span data-ttu-id="bda18-258">Вставить</span><span class="sxs-lookup"><span data-stu-id="bda18-258">Paste</span></span>

<span data-ttu-id="bda18-259">Вставка текста из буфера обмена системы.</span><span class="sxs-lookup"><span data-stu-id="bda18-259">Paste text from the system clipboard.</span></span>

- <span data-ttu-id="bda18-260">Cmd: `<Ctrl+v>` , `<Shift+Insert>`</span><span class="sxs-lookup"><span data-stu-id="bda18-260">Cmd: `<Ctrl+v>`, `<Shift+Insert>`</span></span>
- <span data-ttu-id="bda18-261">Режим вставки в VI: `<Ctrl+v>`</span><span class="sxs-lookup"><span data-stu-id="bda18-261">Vi insert mode: `<Ctrl+v>`</span></span>
- <span data-ttu-id="bda18-262">Режим команд VI: `<Ctrl+v>`</span><span class="sxs-lookup"><span data-stu-id="bda18-262">Vi command mode: `<Ctrl+v>`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bda18-263">При использовании функции **вставки** все содержимое буфера буфера обмена вставляется во входной буфер PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="bda18-263">When using the **Paste** function, the entire contents of the clipboard buffer is pasted into the input buffer of PSReadLine.</span></span> <span data-ttu-id="bda18-264">Затем входной буфер передается средству синтаксического анализа PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bda18-264">The input buffer is then passed to the PowerShell parser.</span></span> <span data-ttu-id="bda18-265">Вход, вставленный с помощью консольного приложения, щелкните **правой кнопкой мыши** метод вставки, скопированный во входной буфер по одному символу за раз.</span><span class="sxs-lookup"><span data-stu-id="bda18-265">Input pasted using the console application's **right-click** paste method is copied to the input buffer one character at a time.</span></span> <span data-ttu-id="bda18-266">Входной буфер передается средству синтаксического анализа при копировании символа новой строки.</span><span class="sxs-lookup"><span data-stu-id="bda18-266">The input buffer is passed to the parser when a newline character is copied.</span></span> <span data-ttu-id="bda18-267">Поэтому входные данные анализируются по одной строке за раз.</span><span class="sxs-lookup"><span data-stu-id="bda18-267">Therefore, the input is parsed one line at a time.</span></span> <span data-ttu-id="bda18-268">Различие между методами вставки приводит к различному поведению при выполнении.</span><span class="sxs-lookup"><span data-stu-id="bda18-268">The difference between paste methods results in different execution behavior.</span></span>

### <a name="pasteafter"></a><span data-ttu-id="bda18-269">пастеафтер</span><span class="sxs-lookup"><span data-stu-id="bda18-269">PasteAfter</span></span>

<span data-ttu-id="bda18-270">Вставьте буфер обмена после курсора, переместив курсор в конец вставленного текста.</span><span class="sxs-lookup"><span data-stu-id="bda18-270">Paste the clipboard after the cursor, moving the cursor to the end of the pasted text.</span></span>

- <span data-ttu-id="bda18-271">Режим команд VI: `<p>`</span><span class="sxs-lookup"><span data-stu-id="bda18-271">Vi command mode: `<p>`</span></span>

### <a name="pastebefore"></a><span data-ttu-id="bda18-272">пастебефоре</span><span class="sxs-lookup"><span data-stu-id="bda18-272">PasteBefore</span></span>

<span data-ttu-id="bda18-273">Вставьте буфер обмена перед курсором, переместив курсор в конец вставленного текста.</span><span class="sxs-lookup"><span data-stu-id="bda18-273">Paste the clipboard before the cursor, moving the cursor to the end of the pasted text.</span></span>

- <span data-ttu-id="bda18-274">Режим команд VI: `<P>`</span><span class="sxs-lookup"><span data-stu-id="bda18-274">Vi command mode: `<P>`</span></span>

### <a name="prependandaccept"></a><span data-ttu-id="bda18-275">препендандакцепт</span><span class="sxs-lookup"><span data-stu-id="bda18-275">PrependAndAccept</span></span>

<span data-ttu-id="bda18-276">Добавьте в начало "#" и примите строку.</span><span class="sxs-lookup"><span data-stu-id="bda18-276">Prepend a '#' and accept the line.</span></span>

- <span data-ttu-id="bda18-277">Режим команд VI: `<#>`</span><span class="sxs-lookup"><span data-stu-id="bda18-277">Vi command mode: `<#>`</span></span>

### <a name="redo"></a><span data-ttu-id="bda18-278">Повторить</span><span class="sxs-lookup"><span data-stu-id="bda18-278">Redo</span></span>

<span data-ttu-id="bda18-279">Отмена отмены.</span><span class="sxs-lookup"><span data-stu-id="bda18-279">Undo an undo.</span></span>

- <span data-ttu-id="bda18-280">Процессор `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="bda18-280">Cmd: `<Ctrl+y>`</span></span>
- <span data-ttu-id="bda18-281">Режим вставки в VI: `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="bda18-281">Vi insert mode: `<Ctrl+y>`</span></span>
- <span data-ttu-id="bda18-282">Режим команд VI: `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="bda18-282">Vi command mode: `<Ctrl+y>`</span></span>

### <a name="repeatlastcommand"></a><span data-ttu-id="bda18-283">репеатласткомманд</span><span class="sxs-lookup"><span data-stu-id="bda18-283">RepeatLastCommand</span></span>

<span data-ttu-id="bda18-284">Повторите Последнее изменение текста.</span><span class="sxs-lookup"><span data-stu-id="bda18-284">Repeat the last text modification.</span></span>

- <span data-ttu-id="bda18-285">Режим команд VI: `<.>`</span><span class="sxs-lookup"><span data-stu-id="bda18-285">Vi command mode: `<.>`</span></span>

### <a name="revertline"></a><span data-ttu-id="bda18-286">ревертлине</span><span class="sxs-lookup"><span data-stu-id="bda18-286">RevertLine</span></span>

<span data-ttu-id="bda18-287">Меняет все входные данные на текущие входные данные.</span><span class="sxs-lookup"><span data-stu-id="bda18-287">Reverts all of the input to the current input.</span></span>

- <span data-ttu-id="bda18-288">Процессор `<Escape>`</span><span class="sxs-lookup"><span data-stu-id="bda18-288">Cmd: `<Escape>`</span></span>
- <span data-ttu-id="bda18-289">Emacs: `<Alt+r>` , `<Escape,r>`</span><span class="sxs-lookup"><span data-stu-id="bda18-289">Emacs: `<Alt+r>`, `<Escape,r>`</span></span>

### <a name="shellbackwardkillword"></a><span data-ttu-id="bda18-290">шеллбакквардкиллворд</span><span class="sxs-lookup"><span data-stu-id="bda18-290">ShellBackwardKillWord</span></span>

<span data-ttu-id="bda18-291">Очистить ввод от начала текущего слова до курсора.</span><span class="sxs-lookup"><span data-stu-id="bda18-291">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="bda18-292">Если курсор находится между словами, входные данные очищаются от начала предыдущего слова до курсора.</span><span class="sxs-lookup"><span data-stu-id="bda18-292">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="bda18-293">Очистка текста помещается в буфер Kill.</span><span class="sxs-lookup"><span data-stu-id="bda18-293">The cleared text is placed in the kill-ring.</span></span>

<span data-ttu-id="bda18-294">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="bda18-294">Function is unbound.</span></span>

### <a name="shellkillword"></a><span data-ttu-id="bda18-295">шеллкиллворд</span><span class="sxs-lookup"><span data-stu-id="bda18-295">ShellKillWord</span></span>

<span data-ttu-id="bda18-296">Очистить ввод от курсора до конца текущего слова.</span><span class="sxs-lookup"><span data-stu-id="bda18-296">Clear the input from the cursor to the end of the current word.</span></span> <span data-ttu-id="bda18-297">Если курсор находится между словами, входные данные очищаются от курсора до конца следующего слова.</span><span class="sxs-lookup"><span data-stu-id="bda18-297">If the cursor is between words, the input is cleared from the cursor to the end of the next word.</span></span> <span data-ttu-id="bda18-298">Очистка текста помещается в буфер Kill.</span><span class="sxs-lookup"><span data-stu-id="bda18-298">The cleared text is placed in the kill-ring.</span></span>

<span data-ttu-id="bda18-299">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="bda18-299">Function is unbound.</span></span>

### <a name="swapcharacters"></a><span data-ttu-id="bda18-300">свапчарактерс</span><span class="sxs-lookup"><span data-stu-id="bda18-300">SwapCharacters</span></span>

<span data-ttu-id="bda18-301">Поменять местами текущий и тот же символ.</span><span class="sxs-lookup"><span data-stu-id="bda18-301">Swap the current character and the one before it.</span></span>

- <span data-ttu-id="bda18-302">Emacs: `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="bda18-302">Emacs: `<Ctrl+t>`</span></span>
- <span data-ttu-id="bda18-303">Режим вставки в VI: `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="bda18-303">Vi insert mode: `<Ctrl+t>`</span></span>
- <span data-ttu-id="bda18-304">Режим команд VI: `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="bda18-304">Vi command mode: `<Ctrl+t>`</span></span>

### <a name="undo"></a><span data-ttu-id="bda18-305">Отменить</span><span class="sxs-lookup"><span data-stu-id="bda18-305">Undo</span></span>

<span data-ttu-id="bda18-306">Отмена предыдущего изменения.</span><span class="sxs-lookup"><span data-stu-id="bda18-306">Undo a previous edit.</span></span>

- <span data-ttu-id="bda18-307">Процессор `<Ctrl+z>`</span><span class="sxs-lookup"><span data-stu-id="bda18-307">Cmd: `<Ctrl+z>`</span></span>
- <span data-ttu-id="bda18-308">Emacs: `<Ctrl+_>` , `<Ctrl+x,Ctrl+u>`</span><span class="sxs-lookup"><span data-stu-id="bda18-308">Emacs: `<Ctrl+_>`, `<Ctrl+x,Ctrl+u>`</span></span>
- <span data-ttu-id="bda18-309">Режим вставки в VI: `<Ctrl+z>`</span><span class="sxs-lookup"><span data-stu-id="bda18-309">Vi insert mode: `<Ctrl+z>`</span></span>
- <span data-ttu-id="bda18-310">Режим команд VI: `<Ctrl+z>` , `<u>`</span><span class="sxs-lookup"><span data-stu-id="bda18-310">Vi command mode: `<Ctrl+z>`, `<u>`</span></span>

### <a name="undoall"></a><span data-ttu-id="bda18-311">ундоалл</span><span class="sxs-lookup"><span data-stu-id="bda18-311">UndoAll</span></span>

<span data-ttu-id="bda18-312">Отмена всех предыдущих изменений для строки.</span><span class="sxs-lookup"><span data-stu-id="bda18-312">Undo all previous edits for line.</span></span>

- <span data-ttu-id="bda18-313">Режим команд VI: `<U>`</span><span class="sxs-lookup"><span data-stu-id="bda18-313">Vi command mode: `<U>`</span></span>

### <a name="unixwordrubout"></a><span data-ttu-id="bda18-314">униксвордрубаут</span><span class="sxs-lookup"><span data-stu-id="bda18-314">UnixWordRubout</span></span>

<span data-ttu-id="bda18-315">Очистить ввод от начала текущего слова до курсора.</span><span class="sxs-lookup"><span data-stu-id="bda18-315">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="bda18-316">Если курсор находится между словами, входные данные очищаются от начала предыдущего слова до курсора.</span><span class="sxs-lookup"><span data-stu-id="bda18-316">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="bda18-317">Очистка текста помещается в буфер Kill.</span><span class="sxs-lookup"><span data-stu-id="bda18-317">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="bda18-318">Emacs: `<Ctrl+w>`</span><span class="sxs-lookup"><span data-stu-id="bda18-318">Emacs: `<Ctrl+w>`</span></span>

### <a name="validateandacceptline"></a><span data-ttu-id="bda18-319">валидатеандакцептлине</span><span class="sxs-lookup"><span data-stu-id="bda18-319">ValidateAndAcceptLine</span></span>

<span data-ttu-id="bda18-320">Попытка выполнить текущий вход.</span><span class="sxs-lookup"><span data-stu-id="bda18-320">Attempt to execute the current input.</span></span> <span data-ttu-id="bda18-321">Если текущий ввод неполон (например, отсутствует закрывающая круглая скобка, квадратная скобка или кавычка, запрос продолжения отображается на следующей строке, а PSReadLine ожидает ввода ключей для изменения текущих входных данных.</span><span class="sxs-lookup"><span data-stu-id="bda18-321">If the current input is incomplete (for example there is a missing closing parenthesis, bracket, or quote, then the continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span>

- <span data-ttu-id="bda18-322">Emacs: `<Ctrl+m>`</span><span class="sxs-lookup"><span data-stu-id="bda18-322">Emacs: `<Ctrl+m>`</span></span>

### <a name="viacceptline"></a><span data-ttu-id="bda18-323">виакцептлине</span><span class="sxs-lookup"><span data-stu-id="bda18-323">ViAcceptLine</span></span>

<span data-ttu-id="bda18-324">Примите строку и переключитесь в режим вставки.</span><span class="sxs-lookup"><span data-stu-id="bda18-324">Accept the line and switch to Insert mode.</span></span>

- <span data-ttu-id="bda18-325">Режим команд VI: `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="bda18-325">Vi command mode: `<Enter>`</span></span>

### <a name="viacceptlineorexit"></a><span data-ttu-id="bda18-326">виакцептлинеорексит</span><span class="sxs-lookup"><span data-stu-id="bda18-326">ViAcceptLineOrExit</span></span>

<span data-ttu-id="bda18-327">Как и Делетечарорексит в режиме Emacs, но принимает строку вместо удаления символа.</span><span class="sxs-lookup"><span data-stu-id="bda18-327">Like DeleteCharOrExit in Emacs mode, but accepts the line instead of deleting a character.</span></span>

- <span data-ttu-id="bda18-328">Режим вставки в VI: `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="bda18-328">Vi insert mode: `<Ctrl+d>`</span></span>
- <span data-ttu-id="bda18-329">Режим команд VI: `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="bda18-329">Vi command mode: `<Ctrl+d>`</span></span>

### <a name="viappendline"></a><span data-ttu-id="bda18-330">виаппендлине</span><span class="sxs-lookup"><span data-stu-id="bda18-330">ViAppendLine</span></span>

<span data-ttu-id="bda18-331">Новая строка вставляется под текущей строкой.</span><span class="sxs-lookup"><span data-stu-id="bda18-331">A new line is inserted below the current line.</span></span>

- <span data-ttu-id="bda18-332">Режим команд VI: `<o>`</span><span class="sxs-lookup"><span data-stu-id="bda18-332">Vi command mode: `<o>`</span></span>

### <a name="vibackwarddeleteglob"></a><span data-ttu-id="bda18-333">вибакквардделетеглоб</span><span class="sxs-lookup"><span data-stu-id="bda18-333">ViBackwardDeleteGlob</span></span>

<span data-ttu-id="bda18-334">Удаляет предыдущее слово, используя только пробелы в качестве разделителя слов.</span><span class="sxs-lookup"><span data-stu-id="bda18-334">Deletes the previous word, using only white space as the word delimiter.</span></span>

- <span data-ttu-id="bda18-335">Режим команд VI: `<d,B>`</span><span class="sxs-lookup"><span data-stu-id="bda18-335">Vi command mode: `<d,B>`</span></span>

### <a name="vibackwardglob"></a><span data-ttu-id="bda18-336">вибакквардглоб</span><span class="sxs-lookup"><span data-stu-id="bda18-336">ViBackwardGlob</span></span>

<span data-ttu-id="bda18-337">Перемещает курсор назад к началу предыдущего слова, используя только пробелы в качестве разделителей.</span><span class="sxs-lookup"><span data-stu-id="bda18-337">Moves the cursor back to the beginning of the previous word, using only white space as delimiters.</span></span>

- <span data-ttu-id="bda18-338">Режим команд VI: `<B>`</span><span class="sxs-lookup"><span data-stu-id="bda18-338">Vi command mode: `<B>`</span></span>

### <a name="videletebrace"></a><span data-ttu-id="bda18-339">виделетебраце</span><span class="sxs-lookup"><span data-stu-id="bda18-339">ViDeleteBrace</span></span>

<span data-ttu-id="bda18-340">Найдите парную фигурную скобку, круглую скобку или квадратную скобку и удалите все содержимое внутри, включая фигурную скобку.</span><span class="sxs-lookup"><span data-stu-id="bda18-340">Find the matching brace, parenthesis, or square bracket and delete all contents within, including the brace.</span></span>

- <span data-ttu-id="bda18-341">Режим команд VI: `<d,%>`</span><span class="sxs-lookup"><span data-stu-id="bda18-341">Vi command mode: `<d,%>`</span></span>

### <a name="videleteendofglob"></a><span data-ttu-id="bda18-342">виделетиндофглоб</span><span class="sxs-lookup"><span data-stu-id="bda18-342">ViDeleteEndOfGlob</span></span>

<span data-ttu-id="bda18-343">Удалить до конца слова.</span><span class="sxs-lookup"><span data-stu-id="bda18-343">Delete to the end of the word.</span></span>

- <span data-ttu-id="bda18-344">Режим команд VI: `<d,E>`</span><span class="sxs-lookup"><span data-stu-id="bda18-344">Vi command mode: `<d,E>`</span></span>

### <a name="videleteglob"></a><span data-ttu-id="bda18-345">виделетеглоб</span><span class="sxs-lookup"><span data-stu-id="bda18-345">ViDeleteGlob</span></span>

<span data-ttu-id="bda18-346">Удалите следующий стандартная маска (слово, разделенное пробелами).</span><span class="sxs-lookup"><span data-stu-id="bda18-346">Delete the next glob (white space delimited word).</span></span>

- <span data-ttu-id="bda18-347">Режим команд VI: `<d,W>`</span><span class="sxs-lookup"><span data-stu-id="bda18-347">Vi command mode: `<d,W>`</span></span>

### <a name="videletetobeforechar"></a><span data-ttu-id="bda18-348">виделететобефоречар</span><span class="sxs-lookup"><span data-stu-id="bda18-348">ViDeleteToBeforeChar</span></span>

<span data-ttu-id="bda18-349">Удаляет до заданного символа.</span><span class="sxs-lookup"><span data-stu-id="bda18-349">Deletes until given character.</span></span>

- <span data-ttu-id="bda18-350">Режим команд VI: `<d,t>`</span><span class="sxs-lookup"><span data-stu-id="bda18-350">Vi command mode: `<d,t>`</span></span>

### <a name="videletetobeforecharbackward"></a><span data-ttu-id="bda18-351">виделететобефоречарбакквард</span><span class="sxs-lookup"><span data-stu-id="bda18-351">ViDeleteToBeforeCharBackward</span></span>

<span data-ttu-id="bda18-352">Удаляет до заданного символа.</span><span class="sxs-lookup"><span data-stu-id="bda18-352">Deletes until given character.</span></span>

- <span data-ttu-id="bda18-353">Режим команд VI: `<d,T>`</span><span class="sxs-lookup"><span data-stu-id="bda18-353">Vi command mode: `<d,T>`</span></span>

### <a name="videletetochar"></a><span data-ttu-id="bda18-354">виделететочар</span><span class="sxs-lookup"><span data-stu-id="bda18-354">ViDeleteToChar</span></span>

<span data-ttu-id="bda18-355">Удаляет до заданного символа.</span><span class="sxs-lookup"><span data-stu-id="bda18-355">Deletes until given character.</span></span>

- <span data-ttu-id="bda18-356">Режим команд VI: `<d,f>`</span><span class="sxs-lookup"><span data-stu-id="bda18-356">Vi command mode: `<d,f>`</span></span>

### <a name="videletetocharbackward"></a><span data-ttu-id="bda18-357">виделететочарбакквард</span><span class="sxs-lookup"><span data-stu-id="bda18-357">ViDeleteToCharBackward</span></span>

<span data-ttu-id="bda18-358">Удаляет обратную сторону до заданного символа.</span><span class="sxs-lookup"><span data-stu-id="bda18-358">Deletes backwards until given character.</span></span>

- <span data-ttu-id="bda18-359">Режим команд VI: `<d,F>`</span><span class="sxs-lookup"><span data-stu-id="bda18-359">Vi command mode: `<d,F>`</span></span>

### <a name="viinsertatbegining"></a><span data-ttu-id="bda18-360">виинсертатбегининг</span><span class="sxs-lookup"><span data-stu-id="bda18-360">ViInsertAtBegining</span></span>

<span data-ttu-id="bda18-361">Переключитесь в режим вставки и поместите курсор в начало строки.</span><span class="sxs-lookup"><span data-stu-id="bda18-361">Switch to Insert mode and position the cursor at the beginning of the line.</span></span>

- <span data-ttu-id="bda18-362">Режим команд VI: `<I>`</span><span class="sxs-lookup"><span data-stu-id="bda18-362">Vi command mode: `<I>`</span></span>

### <a name="viinsertatend"></a><span data-ttu-id="bda18-363">виинсертатенд</span><span class="sxs-lookup"><span data-stu-id="bda18-363">ViInsertAtEnd</span></span>

<span data-ttu-id="bda18-364">Переключитесь в режим вставки и поместите курсор в конец строки.</span><span class="sxs-lookup"><span data-stu-id="bda18-364">Switch to Insert mode and position the cursor at the end of the line.</span></span>

- <span data-ttu-id="bda18-365">Режим команд VI: `<A>`</span><span class="sxs-lookup"><span data-stu-id="bda18-365">Vi command mode: `<A>`</span></span>

### <a name="viinsertline"></a><span data-ttu-id="bda18-366">виинсертлине</span><span class="sxs-lookup"><span data-stu-id="bda18-366">ViInsertLine</span></span>

<span data-ttu-id="bda18-367">Новая строка вставляется над текущей строкой.</span><span class="sxs-lookup"><span data-stu-id="bda18-367">A new line is inserted above the current line.</span></span>

- <span data-ttu-id="bda18-368">Режим команд VI: `<O>`</span><span class="sxs-lookup"><span data-stu-id="bda18-368">Vi command mode: `<O>`</span></span>

### <a name="viinsertwithappend"></a><span data-ttu-id="bda18-369">виинсертвисаппенд</span><span class="sxs-lookup"><span data-stu-id="bda18-369">ViInsertWithAppend</span></span>

<span data-ttu-id="bda18-370">Добавление из текущей позицией строки.</span><span class="sxs-lookup"><span data-stu-id="bda18-370">Append from the current line position.</span></span>

- <span data-ttu-id="bda18-371">Режим команд VI: `<a>`</span><span class="sxs-lookup"><span data-stu-id="bda18-371">Vi command mode: `<a>`</span></span>

### <a name="viinsertwithdelete"></a><span data-ttu-id="bda18-372">виинсертвисделете</span><span class="sxs-lookup"><span data-stu-id="bda18-372">ViInsertWithDelete</span></span>

<span data-ttu-id="bda18-373">Удалите текущий символ и переключитесь в режим вставки.</span><span class="sxs-lookup"><span data-stu-id="bda18-373">Delete the current character and switch to Insert mode.</span></span>

- <span data-ttu-id="bda18-374">Режим команд VI: `<s>`</span><span class="sxs-lookup"><span data-stu-id="bda18-374">Vi command mode: `<s>`</span></span>

### <a name="vijoinlines"></a><span data-ttu-id="bda18-375">вижоинлинес</span><span class="sxs-lookup"><span data-stu-id="bda18-375">ViJoinLines</span></span>

<span data-ttu-id="bda18-376">Объединяет текущую строку и следующую строку.</span><span class="sxs-lookup"><span data-stu-id="bda18-376">Joins the current line and the next line.</span></span>

- <span data-ttu-id="bda18-377">Режим команд VI: `<J>`</span><span class="sxs-lookup"><span data-stu-id="bda18-377">Vi command mode: `<J>`</span></span>

### <a name="vireplaceline"></a><span data-ttu-id="bda18-378">виреплацелине</span><span class="sxs-lookup"><span data-stu-id="bda18-378">ViReplaceLine</span></span>

<span data-ttu-id="bda18-379">Очистить всю командную строку.</span><span class="sxs-lookup"><span data-stu-id="bda18-379">Erase the entire command line.</span></span>

- <span data-ttu-id="bda18-380">Режим команд VI: `<S>` , `<c,c>`</span><span class="sxs-lookup"><span data-stu-id="bda18-380">Vi command mode: `<S>`, `<c,c>`</span></span>

### <a name="vireplacetobeforechar"></a><span data-ttu-id="bda18-381">виреплацетобефоречар</span><span class="sxs-lookup"><span data-stu-id="bda18-381">ViReplaceToBeforeChar</span></span>

<span data-ttu-id="bda18-382">Заменяет заданный символ.</span><span class="sxs-lookup"><span data-stu-id="bda18-382">Replaces until given character.</span></span>

- <span data-ttu-id="bda18-383">Режим команд VI: `<c,t>`</span><span class="sxs-lookup"><span data-stu-id="bda18-383">Vi command mode: `<c,t>`</span></span>

### <a name="vireplacetobeforecharbackward"></a><span data-ttu-id="bda18-384">виреплацетобефоречарбакквард</span><span class="sxs-lookup"><span data-stu-id="bda18-384">ViReplaceToBeforeCharBackward</span></span>

<span data-ttu-id="bda18-385">Заменяет заданный символ.</span><span class="sxs-lookup"><span data-stu-id="bda18-385">Replaces until given character.</span></span>

- <span data-ttu-id="bda18-386">Режим команд VI: `<c,T>`</span><span class="sxs-lookup"><span data-stu-id="bda18-386">Vi command mode: `<c,T>`</span></span>

### <a name="vireplacetochar"></a><span data-ttu-id="bda18-387">виреплацеточар</span><span class="sxs-lookup"><span data-stu-id="bda18-387">ViReplaceToChar</span></span>

<span data-ttu-id="bda18-388">Удаляет до заданного символа.</span><span class="sxs-lookup"><span data-stu-id="bda18-388">Deletes until given character.</span></span>

- <span data-ttu-id="bda18-389">Режим команд VI: `<c,f>`</span><span class="sxs-lookup"><span data-stu-id="bda18-389">Vi command mode: `<c,f>`</span></span>

### <a name="vireplacetocharbackward"></a><span data-ttu-id="bda18-390">виреплацеточарбакквард</span><span class="sxs-lookup"><span data-stu-id="bda18-390">ViReplaceToCharBackward</span></span>

<span data-ttu-id="bda18-391">Заменяет заданный символ.</span><span class="sxs-lookup"><span data-stu-id="bda18-391">Replaces until given character.</span></span>

- <span data-ttu-id="bda18-392">Режим команд VI: `<c,F>`</span><span class="sxs-lookup"><span data-stu-id="bda18-392">Vi command mode: `<c,F>`</span></span>

### <a name="viyankbeginningofline"></a><span data-ttu-id="bda18-393">вийанкбегиннингофлине</span><span class="sxs-lookup"><span data-stu-id="bda18-393">ViYankBeginningOfLine</span></span>

<span data-ttu-id="bda18-394">Янк от начала буфера до курсора.</span><span class="sxs-lookup"><span data-stu-id="bda18-394">Yank from the beginning of the buffer to the cursor.</span></span>

- <span data-ttu-id="bda18-395">Режим команд VI: `<y,0>`</span><span class="sxs-lookup"><span data-stu-id="bda18-395">Vi command mode: `<y,0>`</span></span>

### <a name="viyankendofglob"></a><span data-ttu-id="bda18-396">вийанкендофглоб</span><span class="sxs-lookup"><span data-stu-id="bda18-396">ViYankEndOfGlob</span></span>

<span data-ttu-id="bda18-397">Янк от курсора до конца слова.</span><span class="sxs-lookup"><span data-stu-id="bda18-397">Yank from the cursor to the end of the WORD(s).</span></span>

- <span data-ttu-id="bda18-398">Режим команд VI: `<y,E>`</span><span class="sxs-lookup"><span data-stu-id="bda18-398">Vi command mode: `<y,E>`</span></span>

### <a name="viyankendofword"></a><span data-ttu-id="bda18-399">вийанкендофворд</span><span class="sxs-lookup"><span data-stu-id="bda18-399">ViYankEndOfWord</span></span>

<span data-ttu-id="bda18-400">Янк от курсора до конца слова.</span><span class="sxs-lookup"><span data-stu-id="bda18-400">Yank from the cursor to the end of the word(s).</span></span>

- <span data-ttu-id="bda18-401">Режим команд VI: `<y,e>`</span><span class="sxs-lookup"><span data-stu-id="bda18-401">Vi command mode: `<y,e>`</span></span>

### <a name="viyankleft"></a><span data-ttu-id="bda18-402">вийанклефт</span><span class="sxs-lookup"><span data-stu-id="bda18-402">ViYankLeft</span></span>

<span data-ttu-id="bda18-403">Янк символы слева от курсора.</span><span class="sxs-lookup"><span data-stu-id="bda18-403">Yank character(s) to the left of the cursor.</span></span>

- <span data-ttu-id="bda18-404">Режим команд VI: `<y,h>`</span><span class="sxs-lookup"><span data-stu-id="bda18-404">Vi command mode: `<y,h>`</span></span>

### <a name="viyankline"></a><span data-ttu-id="bda18-405">вийанклине</span><span class="sxs-lookup"><span data-stu-id="bda18-405">ViYankLine</span></span>

<span data-ttu-id="bda18-406">Янк весь буфер.</span><span class="sxs-lookup"><span data-stu-id="bda18-406">Yank the entire buffer.</span></span>

- <span data-ttu-id="bda18-407">Режим команд VI: `<y,y>`</span><span class="sxs-lookup"><span data-stu-id="bda18-407">Vi command mode: `<y,y>`</span></span>

### <a name="viyanknextglob"></a><span data-ttu-id="bda18-408">вийанкнекстглоб</span><span class="sxs-lookup"><span data-stu-id="bda18-408">ViYankNextGlob</span></span>

<span data-ttu-id="bda18-409">Янк от курсора до начала следующего слова.</span><span class="sxs-lookup"><span data-stu-id="bda18-409">Yank from cursor to the start of the next WORD(s).</span></span>

- <span data-ttu-id="bda18-410">Режим команд VI: `<y,W>`</span><span class="sxs-lookup"><span data-stu-id="bda18-410">Vi command mode: `<y,W>`</span></span>

### <a name="viyanknextword"></a><span data-ttu-id="bda18-411">вийанкнекстворд</span><span class="sxs-lookup"><span data-stu-id="bda18-411">ViYankNextWord</span></span>

<span data-ttu-id="bda18-412">Янк слова после курсора.</span><span class="sxs-lookup"><span data-stu-id="bda18-412">Yank the word(s) after the cursor.</span></span>

- <span data-ttu-id="bda18-413">Режим команд VI: `<y,w>`</span><span class="sxs-lookup"><span data-stu-id="bda18-413">Vi command mode: `<y,w>`</span></span>

### <a name="viyankpercent"></a><span data-ttu-id="bda18-414">вийанкперцент</span><span class="sxs-lookup"><span data-stu-id="bda18-414">ViYankPercent</span></span>

<span data-ttu-id="bda18-415">Янк в парную фигурную скобку.</span><span class="sxs-lookup"><span data-stu-id="bda18-415">Yank to/from matching brace.</span></span>

- <span data-ttu-id="bda18-416">Режим команд VI: `<y,%>`</span><span class="sxs-lookup"><span data-stu-id="bda18-416">Vi command mode: `<y,%>`</span></span>

### <a name="viyankpreviousglob"></a><span data-ttu-id="bda18-417">вийанкпревиаусглоб</span><span class="sxs-lookup"><span data-stu-id="bda18-417">ViYankPreviousGlob</span></span>

<span data-ttu-id="bda18-418">Янк от начала слов до курсора.</span><span class="sxs-lookup"><span data-stu-id="bda18-418">Yank from beginning of the WORD(s) to cursor.</span></span>

- <span data-ttu-id="bda18-419">Режим команд VI: `<y,B>`</span><span class="sxs-lookup"><span data-stu-id="bda18-419">Vi command mode: `<y,B>`</span></span>

### <a name="viyankpreviousword"></a><span data-ttu-id="bda18-420">вийанкпревиаусворд</span><span class="sxs-lookup"><span data-stu-id="bda18-420">ViYankPreviousWord</span></span>

<span data-ttu-id="bda18-421">Янк слова перед курсором.</span><span class="sxs-lookup"><span data-stu-id="bda18-421">Yank the word(s) before the cursor.</span></span>

- <span data-ttu-id="bda18-422">Режим команд VI: `<y,b>`</span><span class="sxs-lookup"><span data-stu-id="bda18-422">Vi command mode: `<y,b>`</span></span>

### <a name="viyankright"></a><span data-ttu-id="bda18-423">вийанкригхт</span><span class="sxs-lookup"><span data-stu-id="bda18-423">ViYankRight</span></span>

<span data-ttu-id="bda18-424">Янк символы в положении и справа от курсора.</span><span class="sxs-lookup"><span data-stu-id="bda18-424">Yank character(s) under and to the right of the cursor.</span></span>

- <span data-ttu-id="bda18-425">Режим команд VI: `<y,l>` , `<y,Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="bda18-425">Vi command mode: `<y,l>`, `<y,Spacebar>`</span></span>

### <a name="viyanktoendofline"></a><span data-ttu-id="bda18-426">вийанктоендофлине</span><span class="sxs-lookup"><span data-stu-id="bda18-426">ViYankToEndOfLine</span></span>

<span data-ttu-id="bda18-427">Янк от курсора до конца буфера.</span><span class="sxs-lookup"><span data-stu-id="bda18-427">Yank from the cursor to the end of the buffer.</span></span>

- <span data-ttu-id="bda18-428">Режим команд VI: `<y,$>`</span><span class="sxs-lookup"><span data-stu-id="bda18-428">Vi command mode: `<y,$>`</span></span>

### <a name="viyanktofirstchar"></a><span data-ttu-id="bda18-429">вийанктофирстчар</span><span class="sxs-lookup"><span data-stu-id="bda18-429">ViYankToFirstChar</span></span>

<span data-ttu-id="bda18-430">Янк от первого символа, отличного от пробела, к курсору.</span><span class="sxs-lookup"><span data-stu-id="bda18-430">Yank from the first non-whitespace character to the cursor.</span></span>

- <span data-ttu-id="bda18-431">Режим команд VI: `<y,^>`</span><span class="sxs-lookup"><span data-stu-id="bda18-431">Vi command mode: `<y,^>`</span></span>

### <a name="yank"></a><span data-ttu-id="bda18-432">янк</span><span class="sxs-lookup"><span data-stu-id="bda18-432">Yank</span></span>

<span data-ttu-id="bda18-433">Добавление последнего недавнего текста во входные данные.</span><span class="sxs-lookup"><span data-stu-id="bda18-433">Add the most recently killed text to the input.</span></span>

- <span data-ttu-id="bda18-434">Emacs: `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="bda18-434">Emacs: `<Ctrl+y>`</span></span>

### <a name="yanklastarg"></a><span data-ttu-id="bda18-435">янкластарг</span><span class="sxs-lookup"><span data-stu-id="bda18-435">YankLastArg</span></span>

<span data-ttu-id="bda18-436">Янк последний аргумент из предыдущей строки журнала.</span><span class="sxs-lookup"><span data-stu-id="bda18-436">Yank the last argument from the previous history line.</span></span> <span data-ttu-id="bda18-437">С аргументом при первом вызове он ведет себя так же, как Янкнсарг.</span><span class="sxs-lookup"><span data-stu-id="bda18-437">With an argument, the first time it is invoked, behaves just like YankNthArg.</span></span> <span data-ttu-id="bda18-438">Если вызывается несколько раз, вместо этого выполняется итерация по журналу, а аргумент устанавливает направление (отрицательно меняет направление на противоположное).</span><span class="sxs-lookup"><span data-stu-id="bda18-438">If invoked multiple times, instead it iterates through history and arg sets the direction (negative reverses the direction.)</span></span>

- <span data-ttu-id="bda18-439">Процессор `<Alt+.>`</span><span class="sxs-lookup"><span data-stu-id="bda18-439">Cmd: `<Alt+.>`</span></span>
- <span data-ttu-id="bda18-440">Emacs: `<Alt+.>` , `<Alt+_>` , `<Escape,.>` , `<Escape,_>`</span><span class="sxs-lookup"><span data-stu-id="bda18-440">Emacs: `<Alt+.>`, `<Alt+_>`, `<Escape,.>`, `<Escape,_>`</span></span>

### <a name="yankntharg"></a><span data-ttu-id="bda18-441">янкнсарг</span><span class="sxs-lookup"><span data-stu-id="bda18-441">YankNthArg</span></span>

<span data-ttu-id="bda18-442">Янк первый аргумент (после команды) из предыдущей строки журнала.</span><span class="sxs-lookup"><span data-stu-id="bda18-442">Yank the first argument (after the command) from the previous history line.</span></span>
<span data-ttu-id="bda18-443">При использовании аргумента Янк аргумент n (начиная с 0), если аргумент является отрицательным, начните с последнего аргумента.</span><span class="sxs-lookup"><span data-stu-id="bda18-443">With an argument, yank the nth argument (starting from 0), if the argument is negative, start from the last argument.</span></span>

- <span data-ttu-id="bda18-444">Emacs: `<Ctrl+Alt+y>` , `<Escape,Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="bda18-444">Emacs: `<Ctrl+Alt+y>`, `<Escape,Ctrl+y>`</span></span>

### <a name="yankpop"></a><span data-ttu-id="bda18-445">янкпоп</span><span class="sxs-lookup"><span data-stu-id="bda18-445">YankPop</span></span>

<span data-ttu-id="bda18-446">Если предыдущая операция была Янк или Янкпоп, замените ранее янкед текст следующим уничтоженным текстом из Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="bda18-446">If the previous operation was Yank or YankPop, replace the previously yanked text with the next killed text from the kill-ring.</span></span>

- <span data-ttu-id="bda18-447">Emacs: `<Alt+y>` , `<Escape,y>`</span><span class="sxs-lookup"><span data-stu-id="bda18-447">Emacs: `<Alt+y>`, `<Escape,y>`</span></span>

## <a name="cursor-movement-functions"></a><span data-ttu-id="bda18-448">Функции перемещения курсора</span><span class="sxs-lookup"><span data-stu-id="bda18-448">Cursor movement functions</span></span>

### <a name="backwardchar"></a><span data-ttu-id="bda18-449">бакквардчар</span><span class="sxs-lookup"><span data-stu-id="bda18-449">BackwardChar</span></span>

<span data-ttu-id="bda18-450">Переместить курсор на один символ влево.</span><span class="sxs-lookup"><span data-stu-id="bda18-450">Move the cursor one character to the left.</span></span> <span data-ttu-id="bda18-451">Это может переместить курсор к предыдущей строке многострочного ввода.</span><span class="sxs-lookup"><span data-stu-id="bda18-451">This may move the cursor to the previous line of multi-line input.</span></span>

- <span data-ttu-id="bda18-452">Процессор `<LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="bda18-452">Cmd: `<LeftArrow>`</span></span>
- <span data-ttu-id="bda18-453">Emacs: `<LeftArrow>` , `<Ctrl+b>`</span><span class="sxs-lookup"><span data-stu-id="bda18-453">Emacs: `<LeftArrow>`, `<Ctrl+b>`</span></span>

### <a name="backwardword"></a><span data-ttu-id="bda18-454">бакквардворд</span><span class="sxs-lookup"><span data-stu-id="bda18-454">BackwardWord</span></span>

<span data-ttu-id="bda18-455">Перемещение курсора назад к началу текущего слова или между словами, с начала предыдущего слова.</span><span class="sxs-lookup"><span data-stu-id="bda18-455">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="bda18-456">Границы слов определяются с помощью настраиваемого набора символов.</span><span class="sxs-lookup"><span data-stu-id="bda18-456">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="bda18-457">Процессор `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="bda18-457">Cmd: `<Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="bda18-458">Emacs: `<Alt+b>` , `<Escape,b>`</span><span class="sxs-lookup"><span data-stu-id="bda18-458">Emacs: `<Alt+b>`, `<Escape,b>`</span></span>
- <span data-ttu-id="bda18-459">Режим вставки в VI: `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="bda18-459">Vi insert mode: `<Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="bda18-460">Режим команд VI: `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="bda18-460">Vi command mode: `<Ctrl+LeftArrow>`</span></span>

### <a name="beginningofline"></a><span data-ttu-id="bda18-461">бегиннингофлине</span><span class="sxs-lookup"><span data-stu-id="bda18-461">BeginningOfLine</span></span>

<span data-ttu-id="bda18-462">Если входные данные имеют несколько строк, переместитесь в начало текущей строки или, если они уже находятся в начале строки, перейдите к началу входного элемента.</span><span class="sxs-lookup"><span data-stu-id="bda18-462">If the input has multiple lines, move to the start of the current line, or if already at the start of the line, move to the start of the input.</span></span> <span data-ttu-id="bda18-463">Если входные данные имеют одну строку, переходите к началу входных данных.</span><span class="sxs-lookup"><span data-stu-id="bda18-463">If the input has a single line, move to the start of the input.</span></span>

- <span data-ttu-id="bda18-464">Процессор `<Home>`</span><span class="sxs-lookup"><span data-stu-id="bda18-464">Cmd: `<Home>`</span></span>
- <span data-ttu-id="bda18-465">Emacs: `<Home>` , `<Ctrl+a>`</span><span class="sxs-lookup"><span data-stu-id="bda18-465">Emacs: `<Home>`, `<Ctrl+a>`</span></span>
- <span data-ttu-id="bda18-466">Режим вставки в VI: `<Home>`</span><span class="sxs-lookup"><span data-stu-id="bda18-466">Vi insert mode: `<Home>`</span></span>
- <span data-ttu-id="bda18-467">Режим команд VI: `<Home>`</span><span class="sxs-lookup"><span data-stu-id="bda18-467">Vi command mode: `<Home>`</span></span>

### <a name="endofline"></a><span data-ttu-id="bda18-468">ендофлине</span><span class="sxs-lookup"><span data-stu-id="bda18-468">EndOfLine</span></span>

<span data-ttu-id="bda18-469">Если входные данные имеют несколько строк, переместитесь в конец текущей строки или, если они уже находятся в конце строки, перейдите к концу входных данных.</span><span class="sxs-lookup"><span data-stu-id="bda18-469">If the input has multiple lines, move to the end of the current line, or if already at the end of the line, move to the end of the input.</span></span> <span data-ttu-id="bda18-470">Если входные данные имеют одну строку, переходите к концу входных данных.</span><span class="sxs-lookup"><span data-stu-id="bda18-470">If the input has a single line, move to the end of the input.</span></span>

- <span data-ttu-id="bda18-471">Процессор `<End>`</span><span class="sxs-lookup"><span data-stu-id="bda18-471">Cmd: `<End>`</span></span>
- <span data-ttu-id="bda18-472">Emacs: `<End>` , `<Ctrl+e>`</span><span class="sxs-lookup"><span data-stu-id="bda18-472">Emacs: `<End>`, `<Ctrl+e>`</span></span>
- <span data-ttu-id="bda18-473">Режим вставки в VI: `<End>`</span><span class="sxs-lookup"><span data-stu-id="bda18-473">Vi insert mode: `<End>`</span></span>

### <a name="forwardchar"></a><span data-ttu-id="bda18-474">форвардчар</span><span class="sxs-lookup"><span data-stu-id="bda18-474">ForwardChar</span></span>

<span data-ttu-id="bda18-475">Переместить курсор на один символ вправо.</span><span class="sxs-lookup"><span data-stu-id="bda18-475">Move the cursor one character to the right.</span></span> <span data-ttu-id="bda18-476">Это может переместить курсор на следующую строку многострочного ввода.</span><span class="sxs-lookup"><span data-stu-id="bda18-476">This may move the cursor to the next line of multi-line input.</span></span>

- <span data-ttu-id="bda18-477">Процессор `<RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="bda18-477">Cmd: `<RightArrow>`</span></span>
- <span data-ttu-id="bda18-478">Emacs: `<RightArrow>` , `<Ctrl+f>`</span><span class="sxs-lookup"><span data-stu-id="bda18-478">Emacs: `<RightArrow>`, `<Ctrl+f>`</span></span>

### <a name="forwardword"></a><span data-ttu-id="bda18-479">форвардворд</span><span class="sxs-lookup"><span data-stu-id="bda18-479">ForwardWord</span></span>

<span data-ttu-id="bda18-480">Переместить курсор вперед к концу текущего слова или между словами, до конца следующего слова.</span><span class="sxs-lookup"><span data-stu-id="bda18-480">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="bda18-481">Границы слов определяются с помощью настраиваемого набора символов.</span><span class="sxs-lookup"><span data-stu-id="bda18-481">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="bda18-482">Emacs: `<Alt+f>` , `<Escape,f>`</span><span class="sxs-lookup"><span data-stu-id="bda18-482">Emacs: `<Alt+f>`, `<Escape,f>`</span></span>

### <a name="gotobrace"></a><span data-ttu-id="bda18-483">GotoBrace</span><span class="sxs-lookup"><span data-stu-id="bda18-483">GotoBrace</span></span>

<span data-ttu-id="bda18-484">Перейдите к парной фигурной скобке, круглой скобке или квадратной скобке.</span><span class="sxs-lookup"><span data-stu-id="bda18-484">Go to the matching brace, parenthesis, or square bracket.</span></span>

- <span data-ttu-id="bda18-485">Процессор `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="bda18-485">Cmd: `<Ctrl+]>`</span></span>
- <span data-ttu-id="bda18-486">Режим вставки в VI: `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="bda18-486">Vi insert mode: `<Ctrl+]>`</span></span>
- <span data-ttu-id="bda18-487">Режим команд VI: `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="bda18-487">Vi command mode: `<Ctrl+]>`</span></span>

### <a name="gotocolumn"></a><span data-ttu-id="bda18-488">готоколумн</span><span class="sxs-lookup"><span data-stu-id="bda18-488">GotoColumn</span></span>

<span data-ttu-id="bda18-489">Переход к столбцу, указанному аргументом arg.</span><span class="sxs-lookup"><span data-stu-id="bda18-489">Move to the column indicated by arg.</span></span>

- <span data-ttu-id="bda18-490">Режим команд VI: `<|>`</span><span class="sxs-lookup"><span data-stu-id="bda18-490">Vi command mode: `<|>`</span></span>

### <a name="gotofirstnonblankofline"></a><span data-ttu-id="bda18-491">готофирстнонбланкофлине</span><span class="sxs-lookup"><span data-stu-id="bda18-491">GotoFirstNonBlankOfLine</span></span>

<span data-ttu-id="bda18-492">Переместить курсор к первому непустому символу в строке.</span><span class="sxs-lookup"><span data-stu-id="bda18-492">Move the cursor to the first non-blank character in the line.</span></span>

- <span data-ttu-id="bda18-493">Режим команд VI: `<^>` , `<_>`</span><span class="sxs-lookup"><span data-stu-id="bda18-493">Vi command mode: `<^>`, `<_>`</span></span>

### <a name="movetoendofline"></a><span data-ttu-id="bda18-494">моветоендофлине</span><span class="sxs-lookup"><span data-stu-id="bda18-494">MoveToEndOfLine</span></span>

<span data-ttu-id="bda18-495">Переместить курсор в конец входных данных.</span><span class="sxs-lookup"><span data-stu-id="bda18-495">Move the cursor to the end of the input.</span></span>

- <span data-ttu-id="bda18-496">Режим команд VI: `<End>` , `<$>`</span><span class="sxs-lookup"><span data-stu-id="bda18-496">Vi command mode: `<End>`, `<$>`</span></span>

### <a name="nextline"></a><span data-ttu-id="bda18-497">некстлине</span><span class="sxs-lookup"><span data-stu-id="bda18-497">NextLine</span></span>

<span data-ttu-id="bda18-498">Переместить курсор на следующую строку.</span><span class="sxs-lookup"><span data-stu-id="bda18-498">Move the cursor to the next line.</span></span>

- <span data-ttu-id="bda18-499">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="bda18-499">Function is unbound.</span></span>

### <a name="nextword"></a><span data-ttu-id="bda18-500">некстворд</span><span class="sxs-lookup"><span data-stu-id="bda18-500">NextWord</span></span>

<span data-ttu-id="bda18-501">Переместить курсор вперед к началу следующего слова.</span><span class="sxs-lookup"><span data-stu-id="bda18-501">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="bda18-502">Границы слов определяются с помощью настраиваемого набора символов.</span><span class="sxs-lookup"><span data-stu-id="bda18-502">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="bda18-503">Процессор `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="bda18-503">Cmd: `<Ctrl+RightArrow>`</span></span>
- <span data-ttu-id="bda18-504">Режим вставки в VI: `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="bda18-504">Vi insert mode: `<Ctrl+RightArrow>`</span></span>
- <span data-ttu-id="bda18-505">Режим команд VI: `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="bda18-505">Vi command mode: `<Ctrl+RightArrow>`</span></span>

### <a name="nextwordend"></a><span data-ttu-id="bda18-506">некстворденд</span><span class="sxs-lookup"><span data-stu-id="bda18-506">NextWordEnd</span></span>

<span data-ttu-id="bda18-507">Переместить курсор вперед к концу текущего слова или между словами, до конца следующего слова.</span><span class="sxs-lookup"><span data-stu-id="bda18-507">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="bda18-508">Границы слов определяются с помощью настраиваемого набора символов.</span><span class="sxs-lookup"><span data-stu-id="bda18-508">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="bda18-509">Режим команд VI: `<e>`</span><span class="sxs-lookup"><span data-stu-id="bda18-509">Vi command mode: `<e>`</span></span>

### <a name="previousline"></a><span data-ttu-id="bda18-510">превиауслине</span><span class="sxs-lookup"><span data-stu-id="bda18-510">PreviousLine</span></span>

<span data-ttu-id="bda18-511">Переместить курсор на предыдущую строку.</span><span class="sxs-lookup"><span data-stu-id="bda18-511">Move the cursor to the previous line.</span></span>

- <span data-ttu-id="bda18-512">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="bda18-512">Function is unbound.</span></span>

### <a name="shellbackwardword"></a><span data-ttu-id="bda18-513">шеллбакквардворд</span><span class="sxs-lookup"><span data-stu-id="bda18-513">ShellBackwardWord</span></span>

<span data-ttu-id="bda18-514">Перемещение курсора назад к началу текущего слова или между словами, с начала предыдущего слова.</span><span class="sxs-lookup"><span data-stu-id="bda18-514">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="bda18-515">Границы слов определяются токенами PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bda18-515">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="bda18-516">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="bda18-516">Function is unbound.</span></span>

### <a name="shellforwardword"></a><span data-ttu-id="bda18-517">шеллфорвардворд</span><span class="sxs-lookup"><span data-stu-id="bda18-517">ShellForwardWord</span></span>

<span data-ttu-id="bda18-518">Переместить курсор вперед к началу следующего слова.</span><span class="sxs-lookup"><span data-stu-id="bda18-518">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="bda18-519">Границы слов определяются токенами PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bda18-519">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="bda18-520">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="bda18-520">Function is unbound.</span></span>

### <a name="shellnextword"></a><span data-ttu-id="bda18-521">шеллнекстворд</span><span class="sxs-lookup"><span data-stu-id="bda18-521">ShellNextWord</span></span>

<span data-ttu-id="bda18-522">Переместить курсор вперед к концу текущего слова или между словами, до конца следующего слова.</span><span class="sxs-lookup"><span data-stu-id="bda18-522">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="bda18-523">Границы слов определяются токенами PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bda18-523">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="bda18-524">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="bda18-524">Function is unbound.</span></span>

### <a name="vibackwardchar"></a><span data-ttu-id="bda18-525">вибакквардчар</span><span class="sxs-lookup"><span data-stu-id="bda18-525">ViBackwardChar</span></span>

<span data-ttu-id="bda18-526">Переместить курсор на один символ влево в режиме редактирования VI.</span><span class="sxs-lookup"><span data-stu-id="bda18-526">Move the cursor one character to the left in the Vi edit mode.</span></span> <span data-ttu-id="bda18-527">Это может переместить курсор к предыдущей строке многострочного ввода.</span><span class="sxs-lookup"><span data-stu-id="bda18-527">This may move the cursor to the previous line of multi-line input.</span></span>

- <span data-ttu-id="bda18-528">Режим вставки в VI: `<LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="bda18-528">Vi insert mode: `<LeftArrow>`</span></span>
- <span data-ttu-id="bda18-529">Режим команд VI: `<LeftArrow>` , `<Backspace>` , `<h>`</span><span class="sxs-lookup"><span data-stu-id="bda18-529">Vi command mode: `<LeftArrow>`, `<Backspace>`, `<h>`</span></span>

### <a name="vibackwardword"></a><span data-ttu-id="bda18-530">вибакквардворд</span><span class="sxs-lookup"><span data-stu-id="bda18-530">ViBackwardWord</span></span>

<span data-ttu-id="bda18-531">Перемещение курсора назад к началу текущего слова или между словами, с начала предыдущего слова.</span><span class="sxs-lookup"><span data-stu-id="bda18-531">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="bda18-532">Границы слов определяются с помощью настраиваемого набора символов.</span><span class="sxs-lookup"><span data-stu-id="bda18-532">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="bda18-533">Режим команд VI: `<b>`</span><span class="sxs-lookup"><span data-stu-id="bda18-533">Vi command mode: `<b>`</span></span>

### <a name="viforwardchar"></a><span data-ttu-id="bda18-534">вифорвардчар</span><span class="sxs-lookup"><span data-stu-id="bda18-534">ViForwardChar</span></span>

<span data-ttu-id="bda18-535">Переместить курсор на один символ вправо в режиме редактирования VI.</span><span class="sxs-lookup"><span data-stu-id="bda18-535">Move the cursor one character to the right in the Vi edit mode.</span></span> <span data-ttu-id="bda18-536">Это может переместить курсор на следующую строку многострочного ввода.</span><span class="sxs-lookup"><span data-stu-id="bda18-536">This may move the cursor to the next line of multi-line input.</span></span>

- <span data-ttu-id="bda18-537">Режим вставки в VI: `<RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="bda18-537">Vi insert mode: `<RightArrow>`</span></span>
- <span data-ttu-id="bda18-538">Режим команд VI: `<RightArrow>` , `<Spacebar>` , `<l>`</span><span class="sxs-lookup"><span data-stu-id="bda18-538">Vi command mode: `<RightArrow>`, `<Spacebar>`, `<l>`</span></span>

### <a name="viendofglob"></a><span data-ttu-id="bda18-539">виендофглоб</span><span class="sxs-lookup"><span data-stu-id="bda18-539">ViEndOfGlob</span></span>

<span data-ttu-id="bda18-540">Перемещает курсор в конец слова, используя только пробелы в качестве разделителей.</span><span class="sxs-lookup"><span data-stu-id="bda18-540">Moves the cursor to the end of the word, using only white space as delimiters.</span></span>

- <span data-ttu-id="bda18-541">Режим команд VI: `<E>`</span><span class="sxs-lookup"><span data-stu-id="bda18-541">Vi command mode: `<E>`</span></span>

### <a name="viendofpreviousglob"></a><span data-ttu-id="bda18-542">виендофпревиаусглоб</span><span class="sxs-lookup"><span data-stu-id="bda18-542">ViEndOfPreviousGlob</span></span>

<span data-ttu-id="bda18-543">Переход к концу предыдущего слова с использованием только пробелов в качестве разделителя слов.</span><span class="sxs-lookup"><span data-stu-id="bda18-543">Moves to the end of the previous word, using only white space as a word delimiter.</span></span>

- <span data-ttu-id="bda18-544">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="bda18-544">Function is unbound.</span></span>

### <a name="vigotobrace"></a><span data-ttu-id="bda18-545">виготобраце</span><span class="sxs-lookup"><span data-stu-id="bda18-545">ViGotoBrace</span></span>

<span data-ttu-id="bda18-546">Аналогичен Готобраце, но является символом, а не основан на токене.</span><span class="sxs-lookup"><span data-stu-id="bda18-546">Similar to GotoBrace, but is character based instead of token based.</span></span>

- <span data-ttu-id="bda18-547">Режим команд VI: `<%>`</span><span class="sxs-lookup"><span data-stu-id="bda18-547">Vi command mode: `<%>`</span></span>

### <a name="vinextglob"></a><span data-ttu-id="bda18-548">винекстглоб</span><span class="sxs-lookup"><span data-stu-id="bda18-548">ViNextGlob</span></span>

<span data-ttu-id="bda18-549">Переход к следующему слову с использованием только пробелов в качестве разделителя слов.</span><span class="sxs-lookup"><span data-stu-id="bda18-549">Moves to the next word, using only white space as a word delimiter.</span></span>

- <span data-ttu-id="bda18-550">Режим команд VI: `<W>`</span><span class="sxs-lookup"><span data-stu-id="bda18-550">Vi command mode: `<W>`</span></span>

### <a name="vinextword"></a><span data-ttu-id="bda18-551">винекстворд</span><span class="sxs-lookup"><span data-stu-id="bda18-551">ViNextWord</span></span>

<span data-ttu-id="bda18-552">Переместить курсор вперед к началу следующего слова.</span><span class="sxs-lookup"><span data-stu-id="bda18-552">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="bda18-553">Границы слов определяются с помощью настраиваемого набора символов.</span><span class="sxs-lookup"><span data-stu-id="bda18-553">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="bda18-554">Режим команд VI: `<w>`</span><span class="sxs-lookup"><span data-stu-id="bda18-554">Vi command mode: `<w>`</span></span>

## <a name="history-functions"></a><span data-ttu-id="bda18-555">Функции журнала</span><span class="sxs-lookup"><span data-stu-id="bda18-555">History functions</span></span>

### <a name="beginningofhistory"></a><span data-ttu-id="bda18-556">бегиннингофхистори</span><span class="sxs-lookup"><span data-stu-id="bda18-556">BeginningOfHistory</span></span>

<span data-ttu-id="bda18-557">Перейти к первому элементу в журнале.</span><span class="sxs-lookup"><span data-stu-id="bda18-557">Move to the first item in the history.</span></span>

- <span data-ttu-id="bda18-558">Emacs: `<Alt+<>`</span><span class="sxs-lookup"><span data-stu-id="bda18-558">Emacs: `<Alt+<>`</span></span>

### <a name="clearhistory"></a><span data-ttu-id="bda18-559">клеархистори</span><span class="sxs-lookup"><span data-stu-id="bda18-559">ClearHistory</span></span>

<span data-ttu-id="bda18-560">Очищает журнал в PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="bda18-560">Clears history in PSReadLine.</span></span> <span data-ttu-id="bda18-561">Это не влияет на журнал PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bda18-561">This does not affect PowerShell history.</span></span>

- <span data-ttu-id="bda18-562">Процессор `<Alt+F7>`</span><span class="sxs-lookup"><span data-stu-id="bda18-562">Cmd: `<Alt+F7>`</span></span>

### <a name="endofhistory"></a><span data-ttu-id="bda18-563">ендофхистори</span><span class="sxs-lookup"><span data-stu-id="bda18-563">EndOfHistory</span></span>

<span data-ttu-id="bda18-564">Переход к последнему элементу (текущему входному объекту) в журнале.</span><span class="sxs-lookup"><span data-stu-id="bda18-564">Move to the last item (the current input) in the history.</span></span>

- <span data-ttu-id="bda18-565">Emacs: `<Alt+>>`</span><span class="sxs-lookup"><span data-stu-id="bda18-565">Emacs: `<Alt+>>`</span></span>

### <a name="forwardsearchhistory"></a><span data-ttu-id="bda18-566">форвардсеарчхистори</span><span class="sxs-lookup"><span data-stu-id="bda18-566">ForwardSearchHistory</span></span>

<span data-ttu-id="bda18-567">Выполните добавочный поиск по журналу.</span><span class="sxs-lookup"><span data-stu-id="bda18-567">Perform an incremental forward search through history.</span></span>

- <span data-ttu-id="bda18-568">Процессор `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="bda18-568">Cmd: `<Ctrl+s>`</span></span>
- <span data-ttu-id="bda18-569">Emacs: `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="bda18-569">Emacs: `<Ctrl+s>`</span></span>

### <a name="historysearchbackward"></a><span data-ttu-id="bda18-570">хисторисеарчбакквард</span><span class="sxs-lookup"><span data-stu-id="bda18-570">HistorySearchBackward</span></span>

<span data-ttu-id="bda18-571">Замените текущие входные данные элементом "Previous" из журнала PSReadLine, который соответствует символам между началом и входом и курсором.</span><span class="sxs-lookup"><span data-stu-id="bda18-571">Replace the current input with the 'previous' item from PSReadLine history that matches the characters between the start and the input and the cursor.</span></span>

- <span data-ttu-id="bda18-572">Процессор `<F8>`</span><span class="sxs-lookup"><span data-stu-id="bda18-572">Cmd: `<F8>`</span></span>

### <a name="historysearchforward"></a><span data-ttu-id="bda18-573">хисторисеарчфорвард</span><span class="sxs-lookup"><span data-stu-id="bda18-573">HistorySearchForward</span></span>

<span data-ttu-id="bda18-574">Замените текущие входные данные элементом "Next" из журнала PSReadLine, который соответствует символам между началом и входом и курсором.</span><span class="sxs-lookup"><span data-stu-id="bda18-574">Replace the current input with the 'next' item from PSReadLine history that matches the characters between the start and the input and the cursor.</span></span>

- <span data-ttu-id="bda18-575">Процессор `<Shift+F8>`</span><span class="sxs-lookup"><span data-stu-id="bda18-575">Cmd: `<Shift+F8>`</span></span>

### <a name="nexthistory"></a><span data-ttu-id="bda18-576">некссистори</span><span class="sxs-lookup"><span data-stu-id="bda18-576">NextHistory</span></span>

<span data-ttu-id="bda18-577">Замените текущие входные данные на элемент "Next" из журнала PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="bda18-577">Replace the current input with the 'next' item from PSReadLine history.</span></span>

- <span data-ttu-id="bda18-578">Процессор `<DownArrow>`</span><span class="sxs-lookup"><span data-stu-id="bda18-578">Cmd: `<DownArrow>`</span></span>
- <span data-ttu-id="bda18-579">Emacs: `<DownArrow>` , `<Ctrl+n>`</span><span class="sxs-lookup"><span data-stu-id="bda18-579">Emacs: `<DownArrow>`, `<Ctrl+n>`</span></span>
- <span data-ttu-id="bda18-580">Режим вставки в VI: `<DownArrow>`</span><span class="sxs-lookup"><span data-stu-id="bda18-580">Vi insert mode: `<DownArrow>`</span></span>
- <span data-ttu-id="bda18-581">Режим команд VI: `<DownArrow>` , `<j>` , `<+>`</span><span class="sxs-lookup"><span data-stu-id="bda18-581">Vi command mode: `<DownArrow>`, `<j>`, `<+>`</span></span>

### <a name="previoushistory"></a><span data-ttu-id="bda18-582">превиаушистори</span><span class="sxs-lookup"><span data-stu-id="bda18-582">PreviousHistory</span></span>

<span data-ttu-id="bda18-583">Замените текущие входные данные элементом "Previous" из журнала PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="bda18-583">Replace the current input with the 'previous' item from PSReadLine history.</span></span>

- <span data-ttu-id="bda18-584">Процессор `<UpArrow>`</span><span class="sxs-lookup"><span data-stu-id="bda18-584">Cmd: `<UpArrow>`</span></span>
- <span data-ttu-id="bda18-585">Emacs: `<UpArrow>` , `<Ctrl+p>`</span><span class="sxs-lookup"><span data-stu-id="bda18-585">Emacs: `<UpArrow>`, `<Ctrl+p>`</span></span>
- <span data-ttu-id="bda18-586">Режим вставки в VI: `<UpArrow>`</span><span class="sxs-lookup"><span data-stu-id="bda18-586">Vi insert mode: `<UpArrow>`</span></span>
- <span data-ttu-id="bda18-587">Режим команд VI: `<UpArrow>` , `<k>` , `<->`</span><span class="sxs-lookup"><span data-stu-id="bda18-587">Vi command mode: `<UpArrow>`, `<k>`, `<->`</span></span>

### <a name="reversesearchhistory"></a><span data-ttu-id="bda18-588">реверсесеарчхистори</span><span class="sxs-lookup"><span data-stu-id="bda18-588">ReverseSearchHistory</span></span>

<span data-ttu-id="bda18-589">Выполните добавочный поиск по журналу.</span><span class="sxs-lookup"><span data-stu-id="bda18-589">Perform an incremental backward search through history.</span></span>

- <span data-ttu-id="bda18-590">Процессор `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="bda18-590">Cmd: `<Ctrl+r>`</span></span>
- <span data-ttu-id="bda18-591">Emacs: `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="bda18-591">Emacs: `<Ctrl+r>`</span></span>

### <a name="visearchhistorybackward"></a><span data-ttu-id="bda18-592">висеарчхисторибакквард</span><span class="sxs-lookup"><span data-stu-id="bda18-592">ViSearchHistoryBackward</span></span>

<span data-ttu-id="bda18-593">Запрашивает строку поиска и инициирует поиск по запросу Акцептлине.</span><span class="sxs-lookup"><span data-stu-id="bda18-593">Prompts for a search string and initiates search upon AcceptLine.</span></span>

- <span data-ttu-id="bda18-594">Режим вставки в VI: `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="bda18-594">Vi insert mode: `<Ctrl+r>`</span></span>
- <span data-ttu-id="bda18-595">Режим команд VI: `</>` , `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="bda18-595">Vi command mode: `</>`, `<Ctrl+r>`</span></span>

## <a name="completion-functions"></a><span data-ttu-id="bda18-596">Функции завершения</span><span class="sxs-lookup"><span data-stu-id="bda18-596">Completion functions</span></span>

### <a name="complete"></a><span data-ttu-id="bda18-597">Завершить</span><span class="sxs-lookup"><span data-stu-id="bda18-597">Complete</span></span>

<span data-ttu-id="bda18-598">Попытка выполнить завершение в тексте, окружающем курсор.</span><span class="sxs-lookup"><span data-stu-id="bda18-598">Attempt to perform completion on the text surrounding the cursor.</span></span> <span data-ttu-id="bda18-599">Если существует несколько возможных завершений, для завершения используется самый длинный ненеоднозначный префикс.</span><span class="sxs-lookup"><span data-stu-id="bda18-599">If there are multiple possible completions, the longest unambiguous prefix is used for completion.</span></span> <span data-ttu-id="bda18-600">При попытке выполнить наибольшее неоднозначное Завершение отображается список возможных завершений.</span><span class="sxs-lookup"><span data-stu-id="bda18-600">If trying to complete the longest unambiguous completion, a list of possible completions is displayed.</span></span>

- <span data-ttu-id="bda18-601">Emacs: `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="bda18-601">Emacs: `<Tab>`</span></span>

### <a name="menucomplete"></a><span data-ttu-id="bda18-602">менукомплете</span><span class="sxs-lookup"><span data-stu-id="bda18-602">MenuComplete</span></span>

<span data-ttu-id="bda18-603">Попытка выполнить завершение в тексте, окружающем курсор.</span><span class="sxs-lookup"><span data-stu-id="bda18-603">Attempt to perform completion on the text surrounding the cursor.</span></span> <span data-ttu-id="bda18-604">Если существует несколько возможных завершений, для завершения используется самый длинный ненеоднозначный префикс.</span><span class="sxs-lookup"><span data-stu-id="bda18-604">If there are multiple possible completions, the longest unambiguous prefix is used for completion.</span></span> <span data-ttu-id="bda18-605">При попытке выполнить наибольшее неоднозначное Завершение отображается список возможных завершений.</span><span class="sxs-lookup"><span data-stu-id="bda18-605">If trying to complete the longest unambiguous completion, a list of possible completions is displayed.</span></span>

- <span data-ttu-id="bda18-606">Cmd: `<Ctrl+@>` , `<Ctrl+Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="bda18-606">Cmd: `<Ctrl+@>`, `<Ctrl+Spacebar>`</span></span>
- <span data-ttu-id="bda18-607">Emacs: `<Ctrl+Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="bda18-607">Emacs: `<Ctrl+Spacebar>`</span></span>

### <a name="possiblecompletions"></a><span data-ttu-id="bda18-608">поссиблекомплетионс</span><span class="sxs-lookup"><span data-stu-id="bda18-608">PossibleCompletions</span></span>

<span data-ttu-id="bda18-609">Отображение списка возможных завершений.</span><span class="sxs-lookup"><span data-stu-id="bda18-609">Display the list of possible completions.</span></span>

- <span data-ttu-id="bda18-610">Emacs: `<Alt+=>`</span><span class="sxs-lookup"><span data-stu-id="bda18-610">Emacs: `<Alt+=>`</span></span>
- <span data-ttu-id="bda18-611">Режим вставки в VI: `<Ctrl+Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="bda18-611">Vi insert mode: `<Ctrl+Spacebar>`</span></span>
- <span data-ttu-id="bda18-612">Режим команд VI: `<Ctrl+Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="bda18-612">Vi command mode: `<Ctrl+Spacebar>`</span></span>

### <a name="tabcompletenext"></a><span data-ttu-id="bda18-613">табкомплетенекст</span><span class="sxs-lookup"><span data-stu-id="bda18-613">TabCompleteNext</span></span>

<span data-ttu-id="bda18-614">Попытайтесь завершить текст, окружающий курсор, с помощью следующего доступного завершения.</span><span class="sxs-lookup"><span data-stu-id="bda18-614">Attempt to complete the text surrounding the cursor with the next available completion.</span></span>

- <span data-ttu-id="bda18-615">Процессор `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="bda18-615">Cmd: `<Tab>`</span></span>
- <span data-ttu-id="bda18-616">Режим команд VI: `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="bda18-616">Vi command mode: `<Tab>`</span></span>

### <a name="tabcompleteprevious"></a><span data-ttu-id="bda18-617">табкомплетепревиаус</span><span class="sxs-lookup"><span data-stu-id="bda18-617">TabCompletePrevious</span></span>

<span data-ttu-id="bda18-618">Попытайтесь завершить текст, окружающий курсор, с предыдущим доступным завершением.</span><span class="sxs-lookup"><span data-stu-id="bda18-618">Attempt to complete the text surrounding the cursor with the previous available completion.</span></span>

- <span data-ttu-id="bda18-619">Процессор `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="bda18-619">Cmd: `<Shift+Tab>`</span></span>
- <span data-ttu-id="bda18-620">Режим команд VI: `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="bda18-620">Vi command mode: `<Shift+Tab>`</span></span>

### <a name="vitabcompletenext"></a><span data-ttu-id="bda18-621">витабкомплетенекст</span><span class="sxs-lookup"><span data-stu-id="bda18-621">ViTabCompleteNext</span></span>

<span data-ttu-id="bda18-622">При необходимости завершает текущую группу редактирования и вызывает Табкомплетенекст.</span><span class="sxs-lookup"><span data-stu-id="bda18-622">Ends the current edit group, if needed, and invokes TabCompleteNext.</span></span>

- <span data-ttu-id="bda18-623">Режим вставки в VI: `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="bda18-623">Vi insert mode: `<Tab>`</span></span>

### <a name="vitabcompleteprevious"></a><span data-ttu-id="bda18-624">витабкомплетепревиаус</span><span class="sxs-lookup"><span data-stu-id="bda18-624">ViTabCompletePrevious</span></span>

<span data-ttu-id="bda18-625">При необходимости завершает текущую группу редактирования и вызывает Табкомплетепревиаус.</span><span class="sxs-lookup"><span data-stu-id="bda18-625">Ends the current edit group, if needed, and invokes TabCompletePrevious.</span></span>

- <span data-ttu-id="bda18-626">Режим вставки в VI: `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="bda18-626">Vi insert mode: `<Shift+Tab>`</span></span>

## <a name="miscellaneous-functions"></a><span data-ttu-id="bda18-627">Прочие функции</span><span class="sxs-lookup"><span data-stu-id="bda18-627">Miscellaneous functions</span></span>

### <a name="acceptnextsuggestionword"></a><span data-ttu-id="bda18-628">акцептнекстсугжестионворд</span><span class="sxs-lookup"><span data-stu-id="bda18-628">AcceptNextSuggestionWord</span></span>

<span data-ttu-id="bda18-629">Принять следующее слово встроенного или выбранного предложения.</span><span class="sxs-lookup"><span data-stu-id="bda18-629">Accept the next word of the inline or selected suggestion.</span></span>

- <span data-ttu-id="bda18-630">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="bda18-630">Function is unbound.</span></span>

### <a name="acceptsuggestion"></a><span data-ttu-id="bda18-631">акцептсугжестион</span><span class="sxs-lookup"><span data-stu-id="bda18-631">AcceptSuggestion</span></span>

<span data-ttu-id="bda18-632">Принять текущее встроенное или выбранное предложение.</span><span class="sxs-lookup"><span data-stu-id="bda18-632">Accept the current inline or selected suggestion.</span></span>

- <span data-ttu-id="bda18-633">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="bda18-633">Function is unbound.</span></span>

### <a name="capturescreen"></a><span data-ttu-id="bda18-634">каптурескрин</span><span class="sxs-lookup"><span data-stu-id="bda18-634">CaptureScreen</span></span>

<span data-ttu-id="bda18-635">Запуск интерактивной записи экрана — стрелки вверх и вниз выбор строк, ввод копирует выделенный текст в буфер обмена в виде текста и HTML.</span><span class="sxs-lookup"><span data-stu-id="bda18-635">Start interactive screen capture - up/down arrows select lines, enter copies selected text to clipboard as text and html.</span></span>

- <span data-ttu-id="bda18-636">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="bda18-636">Function is unbound.</span></span>

### <a name="clearscreen"></a><span data-ttu-id="bda18-637">клеарскрин</span><span class="sxs-lookup"><span data-stu-id="bda18-637">ClearScreen</span></span>

<span data-ttu-id="bda18-638">Очистить экран и нарисовать текущую строку в верхней части экрана.</span><span class="sxs-lookup"><span data-stu-id="bda18-638">Clear the screen and draw the current line at the top of the screen.</span></span>

- <span data-ttu-id="bda18-639">Процессор `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="bda18-639">Cmd: `<Ctrl+l>`</span></span>
- <span data-ttu-id="bda18-640">Emacs: `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="bda18-640">Emacs: `<Ctrl+l>`</span></span>
- <span data-ttu-id="bda18-641">Режим вставки в VI: `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="bda18-641">Vi insert mode: `<Ctrl+l>`</span></span>
- <span data-ttu-id="bda18-642">Режим команд VI: `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="bda18-642">Vi command mode: `<Ctrl+l>`</span></span>

### <a name="digitargument"></a><span data-ttu-id="bda18-643">дигитаргумент</span><span class="sxs-lookup"><span data-stu-id="bda18-643">DigitArgument</span></span>

<span data-ttu-id="bda18-644">Начните новый аргумент цифры для передачи другим функциям.</span><span class="sxs-lookup"><span data-stu-id="bda18-644">Start a new digit argument to pass to other functions.</span></span>

- <span data-ttu-id="bda18-645">Cmd: `<Alt+0>` , `<Alt+1>` , `<Alt+2>` , `<Alt+3>` , `<Alt+4>` , `<Alt+5>` , `<Alt+6>` , `<Alt+7>` , `<Alt+8>` , `<Alt+9>` , `<Alt+->`</span><span class="sxs-lookup"><span data-stu-id="bda18-645">Cmd: `<Alt+0>`, `<Alt+1>`, `<Alt+2>`, `<Alt+3>`, `<Alt+4>`, `<Alt+5>`, `<Alt+6>`, `<Alt+7>`, `<Alt+8>`, `<Alt+9>`, `<Alt+->`</span></span>
- <span data-ttu-id="bda18-646">Emacs: `<Alt+0>` , `<Alt+1>` , `<Alt+2>` , `<Alt+3>` , `<Alt+4>` , `<Alt+5>` , `<Alt+6>` , `<Alt+7>` , `<Alt+8>` , `<Alt+9>` , `<Alt+->`</span><span class="sxs-lookup"><span data-stu-id="bda18-646">Emacs: `<Alt+0>`, `<Alt+1>`, `<Alt+2>`, `<Alt+3>`, `<Alt+4>`, `<Alt+5>`, `<Alt+6>`, `<Alt+7>`, `<Alt+8>`, `<Alt+9>`, `<Alt+->`</span></span>
- <span data-ttu-id="bda18-647">Режим команд VI: `<0>` , `<1>` , `<2>` , `<3>` , `<4>` , `<5>` , `<6>` , `<7>` , `<8>` , `<9>`</span><span class="sxs-lookup"><span data-stu-id="bda18-647">Vi command mode: `<0>`, `<1>`, `<2>`, `<3>`, `<4>`, `<5>`, `<6>`, `<7>`, `<8>`, `<9>`</span></span>

### <a name="invokeprompt"></a><span data-ttu-id="bda18-648">инвокепромпт</span><span class="sxs-lookup"><span data-stu-id="bda18-648">InvokePrompt</span></span>

<span data-ttu-id="bda18-649">Стирает текущий запрос и вызывает функцию Prompt для повторного вывода запроса.</span><span class="sxs-lookup"><span data-stu-id="bda18-649">Erases the current prompt and calls the prompt function to redisplay the prompt.</span></span> <span data-ttu-id="bda18-650">Полезен для обработчиков пользовательских ключей, изменяющих состояние, например для изменения текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="bda18-650">Useful for custom key handlers that change state, e.g. change the current directory.</span></span>

- <span data-ttu-id="bda18-651">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="bda18-651">Function is unbound.</span></span>

### <a name="scrolldisplaydown"></a><span data-ttu-id="bda18-652">скроллдисплайдовн</span><span class="sxs-lookup"><span data-stu-id="bda18-652">ScrollDisplayDown</span></span>

<span data-ttu-id="bda18-653">Прокрутите экран вниз на один экран.</span><span class="sxs-lookup"><span data-stu-id="bda18-653">Scroll the display down one screen.</span></span>

- <span data-ttu-id="bda18-654">Процессор `<PageDown>`</span><span class="sxs-lookup"><span data-stu-id="bda18-654">Cmd: `<PageDown>`</span></span>
- <span data-ttu-id="bda18-655">Emacs: `<PageDown>`</span><span class="sxs-lookup"><span data-stu-id="bda18-655">Emacs: `<PageDown>`</span></span>

### <a name="scrolldisplaydownline"></a><span data-ttu-id="bda18-656">скроллдисплайдовнлине</span><span class="sxs-lookup"><span data-stu-id="bda18-656">ScrollDisplayDownLine</span></span>

<span data-ttu-id="bda18-657">Прокрутите экран вниз на одну строку.</span><span class="sxs-lookup"><span data-stu-id="bda18-657">Scroll the display down one line.</span></span>

- <span data-ttu-id="bda18-658">Процессор `<Ctrl+PageDown>`</span><span class="sxs-lookup"><span data-stu-id="bda18-658">Cmd: `<Ctrl+PageDown>`</span></span>
- <span data-ttu-id="bda18-659">Emacs: `<Ctrl+PageDown>`</span><span class="sxs-lookup"><span data-stu-id="bda18-659">Emacs: `<Ctrl+PageDown>`</span></span>

### <a name="scrolldisplaytocursor"></a><span data-ttu-id="bda18-660">скроллдисплайтокурсор</span><span class="sxs-lookup"><span data-stu-id="bda18-660">ScrollDisplayToCursor</span></span>

<span data-ttu-id="bda18-661">Прокрутить экран до курсора.</span><span class="sxs-lookup"><span data-stu-id="bda18-661">Scroll the display to the cursor.</span></span>

- <span data-ttu-id="bda18-662">Emacs: `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="bda18-662">Emacs: `<Ctrl+End>`</span></span>

### <a name="scrolldisplaytop"></a><span data-ttu-id="bda18-663">скроллдисплайтоп</span><span class="sxs-lookup"><span data-stu-id="bda18-663">ScrollDisplayTop</span></span>

<span data-ttu-id="bda18-664">Прокрутите экран до верха.</span><span class="sxs-lookup"><span data-stu-id="bda18-664">Scroll the display to the top.</span></span>

- <span data-ttu-id="bda18-665">Emacs: `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="bda18-665">Emacs: `<Ctrl+Home>`</span></span>

### <a name="scrolldisplayup"></a><span data-ttu-id="bda18-666">скроллдисплайуп</span><span class="sxs-lookup"><span data-stu-id="bda18-666">ScrollDisplayUp</span></span>

<span data-ttu-id="bda18-667">Прокрутите экран вверх на один экран.</span><span class="sxs-lookup"><span data-stu-id="bda18-667">Scroll the display up one screen.</span></span>

- <span data-ttu-id="bda18-668">Процессор `<PageUp>`</span><span class="sxs-lookup"><span data-stu-id="bda18-668">Cmd: `<PageUp>`</span></span>
- <span data-ttu-id="bda18-669">Emacs: `<PageUp>`</span><span class="sxs-lookup"><span data-stu-id="bda18-669">Emacs: `<PageUp>`</span></span>

### <a name="scrolldisplayupline"></a><span data-ttu-id="bda18-670">скроллдисплайуплине</span><span class="sxs-lookup"><span data-stu-id="bda18-670">ScrollDisplayUpLine</span></span>

<span data-ttu-id="bda18-671">Прокрутите экран вверх на одну строку.</span><span class="sxs-lookup"><span data-stu-id="bda18-671">Scroll the display up one line.</span></span>

- <span data-ttu-id="bda18-672">Процессор `<Ctrl+PageUp>`</span><span class="sxs-lookup"><span data-stu-id="bda18-672">Cmd: `<Ctrl+PageUp>`</span></span>
- <span data-ttu-id="bda18-673">Emacs: `<Ctrl+PageUp>`</span><span class="sxs-lookup"><span data-stu-id="bda18-673">Emacs: `<Ctrl+PageUp>`</span></span>

### <a name="selfinsert"></a><span data-ttu-id="bda18-674">селфинсерт</span><span class="sxs-lookup"><span data-stu-id="bda18-674">SelfInsert</span></span>

<span data-ttu-id="bda18-675">Вставьте ключ.</span><span class="sxs-lookup"><span data-stu-id="bda18-675">Insert the key.</span></span>

- <span data-ttu-id="bda18-676">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="bda18-676">Function is unbound.</span></span>

### <a name="showkeybindings"></a><span data-ttu-id="bda18-677">шовкэйбиндингс</span><span class="sxs-lookup"><span data-stu-id="bda18-677">ShowKeyBindings</span></span>

<span data-ttu-id="bda18-678">Отображение всех связанных ключей.</span><span class="sxs-lookup"><span data-stu-id="bda18-678">Show all bound keys.</span></span>

- <span data-ttu-id="bda18-679">Процессор `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="bda18-679">Cmd: `<Ctrl+Alt+?>`</span></span>
- <span data-ttu-id="bda18-680">Emacs: `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="bda18-680">Emacs: `<Ctrl+Alt+?>`</span></span>
- <span data-ttu-id="bda18-681">Режим вставки в VI: `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="bda18-681">Vi insert mode: `<Ctrl+Alt+?>`</span></span>

### <a name="vicommandmode"></a><span data-ttu-id="bda18-682">викоммандмоде</span><span class="sxs-lookup"><span data-stu-id="bda18-682">ViCommandMode</span></span>

<span data-ttu-id="bda18-683">Переключите текущий режим работы с Vi-Insert на VI-Command.</span><span class="sxs-lookup"><span data-stu-id="bda18-683">Switch the current operating mode from Vi-Insert to Vi-Command.</span></span>

- <span data-ttu-id="bda18-684">Режим вставки в VI: `<Escape>`</span><span class="sxs-lookup"><span data-stu-id="bda18-684">Vi insert mode: `<Escape>`</span></span>

### <a name="vidigitargumentinchord"></a><span data-ttu-id="bda18-685">видигитаргументинчорд</span><span class="sxs-lookup"><span data-stu-id="bda18-685">ViDigitArgumentInChord</span></span>

<span data-ttu-id="bda18-686">Начните новый числовой аргумент, чтобы передать его другим функциям в одной из сочетаний VI.</span><span class="sxs-lookup"><span data-stu-id="bda18-686">Start a new digit argument to pass to other functions while in one of vi's chords.</span></span>

- <span data-ttu-id="bda18-687">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="bda18-687">Function is unbound.</span></span>

### <a name="vieditvisually"></a><span data-ttu-id="bda18-688">виедитвисуалли</span><span class="sxs-lookup"><span data-stu-id="bda18-688">ViEditVisually</span></span>

<span data-ttu-id="bda18-689">Измените командную строку в текстовом редакторе, заданном $env: EDITOR или $env: VISUAL.</span><span class="sxs-lookup"><span data-stu-id="bda18-689">Edit the command line in a text editor specified by $env:EDITOR or $env:VISUAL.</span></span>

- <span data-ttu-id="bda18-690">Emacs: `<Ctrl+x,Ctrl+e>`</span><span class="sxs-lookup"><span data-stu-id="bda18-690">Emacs: `<Ctrl+x,Ctrl+e>`</span></span>
- <span data-ttu-id="bda18-691">Режим команд VI: `<v>`</span><span class="sxs-lookup"><span data-stu-id="bda18-691">Vi command mode: `<v>`</span></span>

### <a name="viexit"></a><span data-ttu-id="bda18-692">виексит</span><span class="sxs-lookup"><span data-stu-id="bda18-692">ViExit</span></span>

<span data-ttu-id="bda18-693">Завершает работу оболочки.</span><span class="sxs-lookup"><span data-stu-id="bda18-693">Exits the shell.</span></span>

- <span data-ttu-id="bda18-694">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="bda18-694">Function is unbound.</span></span>

### <a name="viinsertmode"></a><span data-ttu-id="bda18-695">виинсертмоде</span><span class="sxs-lookup"><span data-stu-id="bda18-695">ViInsertMode</span></span>

<span data-ttu-id="bda18-696">Переключитесь в режим вставки.</span><span class="sxs-lookup"><span data-stu-id="bda18-696">Switch to Insert mode.</span></span>

- <span data-ttu-id="bda18-697">Режим команд VI: `<i>`</span><span class="sxs-lookup"><span data-stu-id="bda18-697">Vi command mode: `<i>`</span></span>

### <a name="whatiskey"></a><span data-ttu-id="bda18-698">вхатискэй</span><span class="sxs-lookup"><span data-stu-id="bda18-698">WhatIsKey</span></span>

<span data-ttu-id="bda18-699">Прочитайте ключ и расскажите, к чему привязан ключ.</span><span class="sxs-lookup"><span data-stu-id="bda18-699">Read a key and tell me what the key is bound to.</span></span>

- <span data-ttu-id="bda18-700">Процессор `<Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="bda18-700">Cmd: `<Alt+?>`</span></span>
- <span data-ttu-id="bda18-701">Emacs: `<Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="bda18-701">Emacs: `<Alt+?>`</span></span>

## <a name="selection-functions"></a><span data-ttu-id="bda18-702">Функции выбора</span><span class="sxs-lookup"><span data-stu-id="bda18-702">Selection functions</span></span>

### <a name="exchangepointandmark"></a><span data-ttu-id="bda18-703">ексчанжепоинтандмарк</span><span class="sxs-lookup"><span data-stu-id="bda18-703">ExchangePointAndMark</span></span>

<span data-ttu-id="bda18-704">Курсор помещается в позицию метки, а метка перемещается в положение курсора.</span><span class="sxs-lookup"><span data-stu-id="bda18-704">The cursor is placed at the location of the mark and the mark is moved to the location of the cursor.</span></span>

- <span data-ttu-id="bda18-705">Emacs: `<Ctrl+x,Ctrl+x>`</span><span class="sxs-lookup"><span data-stu-id="bda18-705">Emacs: `<Ctrl+x,Ctrl+x>`</span></span>

### <a name="selectall"></a><span data-ttu-id="bda18-706">SelectAll</span><span class="sxs-lookup"><span data-stu-id="bda18-706">SelectAll</span></span>

<span data-ttu-id="bda18-707">Выделите всю строку.</span><span class="sxs-lookup"><span data-stu-id="bda18-707">Select the entire line.</span></span>

- <span data-ttu-id="bda18-708">Процессор `<Ctrl+a>`</span><span class="sxs-lookup"><span data-stu-id="bda18-708">Cmd: `<Ctrl+a>`</span></span>

### <a name="selectbackwardchar"></a><span data-ttu-id="bda18-709">селектбакквардчар</span><span class="sxs-lookup"><span data-stu-id="bda18-709">SelectBackwardChar</span></span>

<span data-ttu-id="bda18-710">Настройка текущего выделения для включения предыдущего символа.</span><span class="sxs-lookup"><span data-stu-id="bda18-710">Adjust the current selection to include the previous character.</span></span>

- <span data-ttu-id="bda18-711">Процессор `<Shift+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="bda18-711">Cmd: `<Shift+LeftArrow>`</span></span>
- <span data-ttu-id="bda18-712">Emacs: `<Shift+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="bda18-712">Emacs: `<Shift+LeftArrow>`</span></span>

### <a name="selectbackwardsline"></a><span data-ttu-id="bda18-713">селектбакквардслине</span><span class="sxs-lookup"><span data-stu-id="bda18-713">SelectBackwardsLine</span></span>

<span data-ttu-id="bda18-714">Изменить текущее выделение, чтобы включить его от курсора до начала строки.</span><span class="sxs-lookup"><span data-stu-id="bda18-714">Adjust the current selection to include from the cursor to the start of the line.</span></span>

- <span data-ttu-id="bda18-715">Процессор `<Shift+Home>`</span><span class="sxs-lookup"><span data-stu-id="bda18-715">Cmd: `<Shift+Home>`</span></span>
- <span data-ttu-id="bda18-716">Emacs: `<Shift+Home>`</span><span class="sxs-lookup"><span data-stu-id="bda18-716">Emacs: `<Shift+Home>`</span></span>

### <a name="selectbackwardword"></a><span data-ttu-id="bda18-717">селектбакквардворд</span><span class="sxs-lookup"><span data-stu-id="bda18-717">SelectBackwardWord</span></span>

<span data-ttu-id="bda18-718">Настройка текущего выделения для включения предыдущего слова.</span><span class="sxs-lookup"><span data-stu-id="bda18-718">Adjust the current selection to include the previous word.</span></span>

- <span data-ttu-id="bda18-719">Процессор `<Shift+Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="bda18-719">Cmd: `<Shift+Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="bda18-720">Emacs: `<Alt+B>`</span><span class="sxs-lookup"><span data-stu-id="bda18-720">Emacs: `<Alt+B>`</span></span>

### <a name="selectforwardchar"></a><span data-ttu-id="bda18-721">селектфорвардчар</span><span class="sxs-lookup"><span data-stu-id="bda18-721">SelectForwardChar</span></span>

<span data-ttu-id="bda18-722">Измените текущее выделение, чтобы включить следующий символ.</span><span class="sxs-lookup"><span data-stu-id="bda18-722">Adjust the current selection to include the next character.</span></span>

- <span data-ttu-id="bda18-723">Процессор `<Shift+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="bda18-723">Cmd: `<Shift+RightArrow>`</span></span>
- <span data-ttu-id="bda18-724">Emacs: `<Shift+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="bda18-724">Emacs: `<Shift+RightArrow>`</span></span>

### <a name="selectforwardword"></a><span data-ttu-id="bda18-725">селектфорвардворд</span><span class="sxs-lookup"><span data-stu-id="bda18-725">SelectForwardWord</span></span>

<span data-ttu-id="bda18-726">Измените текущее выделение, чтобы включить следующее слово с помощью Форвардворд.</span><span class="sxs-lookup"><span data-stu-id="bda18-726">Adjust the current selection to include the next word using ForwardWord.</span></span>

- <span data-ttu-id="bda18-727">Emacs: `<Alt+F>`</span><span class="sxs-lookup"><span data-stu-id="bda18-727">Emacs: `<Alt+F>`</span></span>

### <a name="selectline"></a><span data-ttu-id="bda18-728">селектлине</span><span class="sxs-lookup"><span data-stu-id="bda18-728">SelectLine</span></span>

<span data-ttu-id="bda18-729">Настройка текущего выделения для включения курсора в конец строки.</span><span class="sxs-lookup"><span data-stu-id="bda18-729">Adjust the current selection to include from the cursor to the end of the line.</span></span>

- <span data-ttu-id="bda18-730">Процессор `<Shift+End>`</span><span class="sxs-lookup"><span data-stu-id="bda18-730">Cmd: `<Shift+End>`</span></span>
- <span data-ttu-id="bda18-731">Emacs: `<Shift+End>`</span><span class="sxs-lookup"><span data-stu-id="bda18-731">Emacs: `<Shift+End>`</span></span>

### <a name="selectnextword"></a><span data-ttu-id="bda18-732">селектнекстворд</span><span class="sxs-lookup"><span data-stu-id="bda18-732">SelectNextWord</span></span>

<span data-ttu-id="bda18-733">Настройка текущего выделения для включения следующего слова.</span><span class="sxs-lookup"><span data-stu-id="bda18-733">Adjust the current selection to include the next word.</span></span>

- <span data-ttu-id="bda18-734">Процессор `<Shift+Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="bda18-734">Cmd: `<Shift+Ctrl+RightArrow>`</span></span>

### <a name="selectshellbackwardword"></a><span data-ttu-id="bda18-735">селектшеллбакквардворд</span><span class="sxs-lookup"><span data-stu-id="bda18-735">SelectShellBackwardWord</span></span>

<span data-ttu-id="bda18-736">Измените текущее выделение, чтобы включить предыдущее слово с помощью Шеллбакквардворд.</span><span class="sxs-lookup"><span data-stu-id="bda18-736">Adjust the current selection to include the previous word using ShellBackwardWord.</span></span>

- <span data-ttu-id="bda18-737">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="bda18-737">Function is unbound.</span></span>

### <a name="selectshellforwardword"></a><span data-ttu-id="bda18-738">селектшеллфорвардворд</span><span class="sxs-lookup"><span data-stu-id="bda18-738">SelectShellForwardWord</span></span>

<span data-ttu-id="bda18-739">Измените текущее выделение, чтобы включить следующее слово с помощью Шеллфорвардворд.</span><span class="sxs-lookup"><span data-stu-id="bda18-739">Adjust the current selection to include the next word using ShellForwardWord.</span></span>

- <span data-ttu-id="bda18-740">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="bda18-740">Function is unbound.</span></span>

### <a name="selectshellnextword"></a><span data-ttu-id="bda18-741">селектшеллнекстворд</span><span class="sxs-lookup"><span data-stu-id="bda18-741">SelectShellNextWord</span></span>

<span data-ttu-id="bda18-742">Измените текущее выделение, чтобы включить следующее слово с помощью Шеллнекстворд.</span><span class="sxs-lookup"><span data-stu-id="bda18-742">Adjust the current selection to include the next word using ShellNextWord.</span></span>

- <span data-ttu-id="bda18-743">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="bda18-743">Function is unbound.</span></span>

### <a name="setmark"></a><span data-ttu-id="bda18-744">сетмарк</span><span class="sxs-lookup"><span data-stu-id="bda18-744">SetMark</span></span>

<span data-ttu-id="bda18-745">Пометка текущего положения курсора для использования в последующей команде редактирования.</span><span class="sxs-lookup"><span data-stu-id="bda18-745">Mark the current location of the cursor for use in a subsequent editing command.</span></span>

- <span data-ttu-id="bda18-746">Emacs: `<Ctrl+@>`</span><span class="sxs-lookup"><span data-stu-id="bda18-746">Emacs: `<Ctrl+@>`</span></span>

## <a name="search-functions"></a><span data-ttu-id="bda18-747">Функции поиска</span><span class="sxs-lookup"><span data-stu-id="bda18-747">Search functions</span></span>

### <a name="charactersearch"></a><span data-ttu-id="bda18-748">чарактерсеарч</span><span class="sxs-lookup"><span data-stu-id="bda18-748">CharacterSearch</span></span>

<span data-ttu-id="bda18-749">Чтение символа и поиск вперед для следующего вхождения этого символа.</span><span class="sxs-lookup"><span data-stu-id="bda18-749">Read a character and search forward for the next occurrence of that character.</span></span>
<span data-ttu-id="bda18-750">Если указан аргумент, то для n-го вхождения выполните поиск вперед (или назад, если отрицательное).</span><span class="sxs-lookup"><span data-stu-id="bda18-750">If an argument is specified, search forward (or backward if negative) for the nth occurrence.</span></span>

- <span data-ttu-id="bda18-751">Процессор `<F3>`</span><span class="sxs-lookup"><span data-stu-id="bda18-751">Cmd: `<F3>`</span></span>
- <span data-ttu-id="bda18-752">Emacs: `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="bda18-752">Emacs: `<Ctrl+]>`</span></span>
- <span data-ttu-id="bda18-753">Режим вставки в VI: `<F3>`</span><span class="sxs-lookup"><span data-stu-id="bda18-753">Vi insert mode: `<F3>`</span></span>
- <span data-ttu-id="bda18-754">Режим команд VI: `<F3>`</span><span class="sxs-lookup"><span data-stu-id="bda18-754">Vi command mode: `<F3>`</span></span>

### <a name="charactersearchbackward"></a><span data-ttu-id="bda18-755">чарактерсеарчбакквард</span><span class="sxs-lookup"><span data-stu-id="bda18-755">CharacterSearchBackward</span></span>

<span data-ttu-id="bda18-756">Чтение символа и поиск следующего вхождения этого символа в обратном направлении.</span><span class="sxs-lookup"><span data-stu-id="bda18-756">Read a character and search backward for the next occurrence of that character.</span></span> <span data-ttu-id="bda18-757">Если аргумент указан, поиск в n-й последовательности осуществляется назад (или вперед, если отрицательное).</span><span class="sxs-lookup"><span data-stu-id="bda18-757">If an argument is specified, search backward (or forward if negative) for the nth occurrence.</span></span>

- <span data-ttu-id="bda18-758">Процессор `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="bda18-758">Cmd: `<Shift+F3>`</span></span>
- <span data-ttu-id="bda18-759">Emacs: `<Ctrl+Alt+]>`</span><span class="sxs-lookup"><span data-stu-id="bda18-759">Emacs: `<Ctrl+Alt+]>`</span></span>
- <span data-ttu-id="bda18-760">Режим вставки в VI: `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="bda18-760">Vi insert mode: `<Shift+F3>`</span></span>
- <span data-ttu-id="bda18-761">Режим команд VI: `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="bda18-761">Vi command mode: `<Shift+F3>`</span></span>

### <a name="repeatlastcharsearch"></a><span data-ttu-id="bda18-762">репеатластчарсеарч</span><span class="sxs-lookup"><span data-stu-id="bda18-762">RepeatLastCharSearch</span></span>

<span data-ttu-id="bda18-763">Повторите поиск последнего записанного символа.</span><span class="sxs-lookup"><span data-stu-id="bda18-763">Repeat the last recorded character search.</span></span>

- <span data-ttu-id="bda18-764">Режим команд VI: `<;>`</span><span class="sxs-lookup"><span data-stu-id="bda18-764">Vi command mode: `<;>`</span></span>

### <a name="repeatlastcharsearchbackwards"></a><span data-ttu-id="bda18-765">репеатластчарсеарчбакквардс</span><span class="sxs-lookup"><span data-stu-id="bda18-765">RepeatLastCharSearchBackwards</span></span>

<span data-ttu-id="bda18-766">Повторите поиск последнего записанного символа, но в обратном направлении.</span><span class="sxs-lookup"><span data-stu-id="bda18-766">Repeat the last recorded character search, but in the opposite direction.</span></span>

- <span data-ttu-id="bda18-767">Режим команд VI: `<,>`</span><span class="sxs-lookup"><span data-stu-id="bda18-767">Vi command mode: `<,>`</span></span>

### <a name="repeatsearch"></a><span data-ttu-id="bda18-768">репеатсеарч</span><span class="sxs-lookup"><span data-stu-id="bda18-768">RepeatSearch</span></span>

<span data-ttu-id="bda18-769">Повторите последний поиск в том же направлении, что и раньше.</span><span class="sxs-lookup"><span data-stu-id="bda18-769">Repeat the last search in the same direction as before.</span></span>

- <span data-ttu-id="bda18-770">Режим команд VI: `<n>`</span><span class="sxs-lookup"><span data-stu-id="bda18-770">Vi command mode: `<n>`</span></span>

### <a name="repeatsearchbackward"></a><span data-ttu-id="bda18-771">репеатсеарчбакквард</span><span class="sxs-lookup"><span data-stu-id="bda18-771">RepeatSearchBackward</span></span>

<span data-ttu-id="bda18-772">Повторите последний поиск в том же направлении, что и раньше.</span><span class="sxs-lookup"><span data-stu-id="bda18-772">Repeat the last search in the same direction as before.</span></span>

- <span data-ttu-id="bda18-773">Режим команд VI: `<N>`</span><span class="sxs-lookup"><span data-stu-id="bda18-773">Vi command mode: `<N>`</span></span>

### <a name="searchchar"></a><span data-ttu-id="bda18-774">сеарччар</span><span class="sxs-lookup"><span data-stu-id="bda18-774">SearchChar</span></span>

<span data-ttu-id="bda18-775">Прочитать следующий символ, затем найти его, перейти вперед, а затем отследить символ.</span><span class="sxs-lookup"><span data-stu-id="bda18-775">Read the next character and then find it, going forward, and then back off a character.</span></span> <span data-ttu-id="bda18-776">Это относится к функциональным возможностям.</span><span class="sxs-lookup"><span data-stu-id="bda18-776">This is for 't' functionality.</span></span>

- <span data-ttu-id="bda18-777">Режим команд VI: `<f>`</span><span class="sxs-lookup"><span data-stu-id="bda18-777">Vi command mode: `<f>`</span></span>

### <a name="searchcharbackward"></a><span data-ttu-id="bda18-778">сеарччарбакквард</span><span class="sxs-lookup"><span data-stu-id="bda18-778">SearchCharBackward</span></span>

<span data-ttu-id="bda18-779">Прочитать следующий символ, а затем найти его, вернуться назад, а затем отследить символ.</span><span class="sxs-lookup"><span data-stu-id="bda18-779">Read the next character and then find it, going backward, and then back off a character.</span></span> <span data-ttu-id="bda18-780">Это относится к функциональным возможностям.</span><span class="sxs-lookup"><span data-stu-id="bda18-780">This is for 'T' functionality.</span></span>

- <span data-ttu-id="bda18-781">Режим команд VI: `<F>`</span><span class="sxs-lookup"><span data-stu-id="bda18-781">Vi command mode: `<F>`</span></span>

### <a name="searchcharbackwardwithbackoff"></a><span data-ttu-id="bda18-782">сеарччарбакквардвисбаккофф</span><span class="sxs-lookup"><span data-stu-id="bda18-782">SearchCharBackwardWithBackoff</span></span>

<span data-ttu-id="bda18-783">Прочитать следующий символ, а затем найти его, вернуться назад, а затем отследить символ.</span><span class="sxs-lookup"><span data-stu-id="bda18-783">Read the next character and then find it, going backward, and then back off a character.</span></span> <span data-ttu-id="bda18-784">Это относится к функциональным возможностям.</span><span class="sxs-lookup"><span data-stu-id="bda18-784">This is for 'T' functionality.</span></span>

- <span data-ttu-id="bda18-785">Режим команд VI: `<T>`</span><span class="sxs-lookup"><span data-stu-id="bda18-785">Vi command mode: `<T>`</span></span>

### <a name="searchcharwithbackoff"></a><span data-ttu-id="bda18-786">сеарччарвисбаккофф</span><span class="sxs-lookup"><span data-stu-id="bda18-786">SearchCharWithBackoff</span></span>

<span data-ttu-id="bda18-787">Прочитать следующий символ, затем найти его, перейти вперед, а затем отследить символ.</span><span class="sxs-lookup"><span data-stu-id="bda18-787">Read the next character and then find it, going forward, and then back off a character.</span></span> <span data-ttu-id="bda18-788">Это относится к функциональным возможностям.</span><span class="sxs-lookup"><span data-stu-id="bda18-788">This is for 't' functionality.</span></span>

- <span data-ttu-id="bda18-789">Режим команд VI: `<t>`</span><span class="sxs-lookup"><span data-stu-id="bda18-789">Vi command mode: `<t>`</span></span>

### <a name="searchforward"></a><span data-ttu-id="bda18-790">сеарчфорвард</span><span class="sxs-lookup"><span data-stu-id="bda18-790">SearchForward</span></span>

<span data-ttu-id="bda18-791">Запрашивает строку поиска и инициирует поиск по запросу Акцептлине.</span><span class="sxs-lookup"><span data-stu-id="bda18-791">Prompts for a search string and initiates search upon AcceptLine.</span></span>

- <span data-ttu-id="bda18-792">Режим вставки в VI: `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="bda18-792">Vi insert mode: `<Ctrl+s>`</span></span>
- <span data-ttu-id="bda18-793">Режим команд VI: `<?>` , `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="bda18-793">Vi command mode: `<?>`, `<Ctrl+s>`</span></span>

## <a name="custom-key-bindings"></a><span data-ttu-id="bda18-794">Пользовательские привязки клавиш</span><span class="sxs-lookup"><span data-stu-id="bda18-794">Custom Key Bindings</span></span>

<span data-ttu-id="bda18-795">PSReadLine поддерживает пользовательские привязки клавиш с помощью командлета `Set-PSReadLineKeyHandler` .</span><span class="sxs-lookup"><span data-stu-id="bda18-795">PSReadLine supports custom key bindings using the cmdlet `Set-PSReadLineKeyHandler`.</span></span> <span data-ttu-id="bda18-796">Большинство пользовательских привязок вызывают одну из приведенных выше функций, например</span><span class="sxs-lookup"><span data-stu-id="bda18-796">Most custom key bindings call one of the above functions, for example</span></span>

```powershell
Set-PSReadLineKeyHandler -Key UpArrow -Function HistorySearchBackward
```

<span data-ttu-id="bda18-797">Можно привязать ScriptBlock к ключу.</span><span class="sxs-lookup"><span data-stu-id="bda18-797">You can bind a ScriptBlock to a key.</span></span> <span data-ttu-id="bda18-798">Блок ScriptBlock может выполнять практически все необходимые действия.</span><span class="sxs-lookup"><span data-stu-id="bda18-798">The ScriptBlock can do pretty much anything you want.</span></span> <span data-ttu-id="bda18-799">Ниже приведены некоторые полезные примеры.</span><span class="sxs-lookup"><span data-stu-id="bda18-799">Some useful examples include</span></span>

- <span data-ttu-id="bda18-800">Изменение командной строки</span><span class="sxs-lookup"><span data-stu-id="bda18-800">edit the command line</span></span>
- <span data-ttu-id="bda18-801">Открытие нового окна (например, Справка)</span><span class="sxs-lookup"><span data-stu-id="bda18-801">opening a new window (e.g. help)</span></span>
- <span data-ttu-id="bda18-802">Изменение каталогов без изменения командной строки</span><span class="sxs-lookup"><span data-stu-id="bda18-802">change directories without changing the command line</span></span>

<span data-ttu-id="bda18-803">Блок ScriptBlock получает два аргумента:</span><span class="sxs-lookup"><span data-stu-id="bda18-803">The ScriptBlock receives two arguments:</span></span>

- <span data-ttu-id="bda18-804">`$key` — Объект **[консолекэйинфо]** , который является ключом, запускающим пользовательскую привязку.</span><span class="sxs-lookup"><span data-stu-id="bda18-804">`$key` - A **[ConsoleKeyInfo]** object that is the key that triggered the custom binding.</span></span> <span data-ttu-id="bda18-805">Если один и тот же блок сценария привязан к нескольким ключам и необходимо выполнять различные действия в зависимости от ключа, можно проверить $key.</span><span class="sxs-lookup"><span data-stu-id="bda18-805">If you bind the same ScriptBlock to multiple keys and need to perform different actions depending on the key, you can check $key.</span></span> <span data-ttu-id="bda18-806">Многие пользовательские привязки игнорируют этот аргумент.</span><span class="sxs-lookup"><span data-stu-id="bda18-806">Many custom bindings ignore this argument.</span></span>

- <span data-ttu-id="bda18-807">`$arg` — Произвольный аргумент.</span><span class="sxs-lookup"><span data-stu-id="bda18-807">`$arg` - An arbitrary argument.</span></span> <span data-ttu-id="bda18-808">Чаще всего это будет целочисленный аргумент, который пользователь передает из ключевых привязок Дигитаргумент.</span><span class="sxs-lookup"><span data-stu-id="bda18-808">Most often, this would be an integer argument that the user passes from the key bindings DigitArgument.</span></span> <span data-ttu-id="bda18-809">Если привязка не принимает аргументы, целесообразно проигнорировать этот аргумент.</span><span class="sxs-lookup"><span data-stu-id="bda18-809">If your binding doesn't accept arguments, it's reasonable to ignore this argument.</span></span>

<span data-ttu-id="bda18-810">Рассмотрим пример, который добавляет в журнал командную строку, не выполняя ее.</span><span class="sxs-lookup"><span data-stu-id="bda18-810">Let's take a look at an example that adds a command line to history without executing it.</span></span> <span data-ttu-id="bda18-811">Это полезно, если вы забыли сделать что-то, но не хотите повторно вводить уже введенную командную строку.</span><span class="sxs-lookup"><span data-stu-id="bda18-811">This is useful when you realize you forgot to do something, but don't want to re-enter the command line you've already entered.</span></span>

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

<span data-ttu-id="bda18-812">В файле, `SamplePSReadLineProfile.ps1` который устанавливается в папку модуля PSReadLine, можно увидеть много других примеров.</span><span class="sxs-lookup"><span data-stu-id="bda18-812">You can see many more examples in the file `SamplePSReadLineProfile.ps1` which is installed in the PSReadLine module folder.</span></span>

<span data-ttu-id="bda18-813">Большинство ключевых привязок используют некоторые вспомогательные функции для редактирования командной строки.</span><span class="sxs-lookup"><span data-stu-id="bda18-813">Most key bindings use some helper functions for editing the command line.</span></span>
<span data-ttu-id="bda18-814">Эти API-интерфейсы описаны в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="bda18-814">Those APIs are documented in the next section.</span></span>

## <a name="custom-key-binding-support-apis"></a><span data-ttu-id="bda18-815">API поддержки пользовательского сочетания клавиш</span><span class="sxs-lookup"><span data-stu-id="bda18-815">Custom Key Binding Support APIs</span></span>

<span data-ttu-id="bda18-816">Следующие функции являются открытыми в Microsoft. PowerShell. Псконсолереадлине, но не могут быть напрямую привязаны к ключу.</span><span class="sxs-lookup"><span data-stu-id="bda18-816">The following functions are public in Microsoft.PowerShell.PSConsoleReadLine, but cannot be directly bound to a key.</span></span> <span data-ttu-id="bda18-817">Большинство из них удобно использовать в пользовательских привязках клавиш.</span><span class="sxs-lookup"><span data-stu-id="bda18-817">Most are useful in custom key bindings.</span></span>

```csharp
void AddToHistory(string command)
```

<span data-ttu-id="bda18-818">Добавьте командную строку в журнал, не выполняя ее.</span><span class="sxs-lookup"><span data-stu-id="bda18-818">Add a command line to history without executing it.</span></span>

```csharp
void ClearKillRing()
```

<span data-ttu-id="bda18-819">Снимите флажок Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="bda18-819">Clear the kill-ring.</span></span>  <span data-ttu-id="bda18-820">Это в основном используется для тестирования.</span><span class="sxs-lookup"><span data-stu-id="bda18-820">This is mostly used for testing.</span></span>

```csharp
void Delete(int start, int length)
```

<span data-ttu-id="bda18-821">Удалить символы длины из Start.</span><span class="sxs-lookup"><span data-stu-id="bda18-821">Delete length characters from start.</span></span>  <span data-ttu-id="bda18-822">Эта операция поддерживает операцию отмены и повтора.</span><span class="sxs-lookup"><span data-stu-id="bda18-822">This operation supports undo/redo.</span></span>

```csharp
void Ding()
```

<span data-ttu-id="bda18-823">Выполните действие DING, основанное на предпочтениях пользователей.</span><span class="sxs-lookup"><span data-stu-id="bda18-823">Perform the Ding action based on the users preference.</span></span>

```csharp
void GetBufferState([ref] string input, [ref] int cursor)
void GetBufferState([ref] Ast ast, [ref] Token[] tokens,
  [ref] ParseError[] parseErrors, [ref] int cursor)
```

<span data-ttu-id="bda18-824">Эти две функции извлекают полезную информацию о текущем состоянии входного буфера.</span><span class="sxs-lookup"><span data-stu-id="bda18-824">These two functions retrieve useful information about the current state of the input buffer.</span></span>  <span data-ttu-id="bda18-825">Первый из них чаще всего используется в простых случаях.</span><span class="sxs-lookup"><span data-stu-id="bda18-825">The first is more commonly used for simple cases.</span></span>  <span data-ttu-id="bda18-826">Второй используется, если привязка делает что-то более сложное с AST.</span><span class="sxs-lookup"><span data-stu-id="bda18-826">The second is used if your binding is doing something more advanced with the Ast.</span></span>

```csharp
IEnumerable[Microsoft.PowerShell.KeyHandler]
  GetKeyHandlers(bool includeBound, bool includeUnbound)

IEnumerable[Microsoft.PowerShell.KeyHandler]
  GetKeyHandlers(string[] Chord)
```

<span data-ttu-id="bda18-827">Эти две функции используются `Get-PSReadLineKeyHandler` .</span><span class="sxs-lookup"><span data-stu-id="bda18-827">These two functions are used by `Get-PSReadLineKeyHandler`.</span></span> <span data-ttu-id="bda18-828">Первый используется для получения всех привязок клавиш.</span><span class="sxs-lookup"><span data-stu-id="bda18-828">The first is used to get all key bindings.</span></span> <span data-ttu-id="bda18-829">Второй используется для получения конкретных привязок клавиш.</span><span class="sxs-lookup"><span data-stu-id="bda18-829">The second is used to get specific key bindings.</span></span>

```csharp
Microsoft.PowerShell.PSConsoleReadLineOptions GetOptions()
```

<span data-ttu-id="bda18-830">Эта функция используется Get-PSReadLineOption и, возможно, не слишком полезна в пользовательской привязке ключа.</span><span class="sxs-lookup"><span data-stu-id="bda18-830">This function is used by Get-PSReadLineOption and probably isn't too useful in a custom key binding.</span></span>

```csharp
void GetSelectionState([ref] int start, [ref] int length)
```

<span data-ttu-id="bda18-831">Если в командной строке ничего не выбрано, значение-1 будет возвращено как в начале, так и в длине.</span><span class="sxs-lookup"><span data-stu-id="bda18-831">If there is no selection on the command line, -1 will be returned in both start and length.</span></span> <span data-ttu-id="bda18-832">Если в командной строке имеется выделенный фрагмент, то начинается и длина выбора возвращается.</span><span class="sxs-lookup"><span data-stu-id="bda18-832">If there is a selection on the command line, the start and length of the selection are returned.</span></span>

```csharp
void Insert(char c)
void Insert(string s)
```

<span data-ttu-id="bda18-833">Вставка символа или строки в курсоре.</span><span class="sxs-lookup"><span data-stu-id="bda18-833">Insert a character or string at the cursor.</span></span>  <span data-ttu-id="bda18-834">Эта операция поддерживает операцию отмены и повтора.</span><span class="sxs-lookup"><span data-stu-id="bda18-834">This operation supports undo/redo.</span></span>

```csharp
string ReadLine(runspace remoteRunspace,
  System.Management.Automation.EngineIntrinsics engineIntrinsics)
```

<span data-ttu-id="bda18-835">Это Главная точка входа для PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="bda18-835">This is the main entry point to PSReadLine.</span></span> <span data-ttu-id="bda18-836">Она не поддерживает рекурсию, поэтому она не полезна в пользовательской привязке ключа.</span><span class="sxs-lookup"><span data-stu-id="bda18-836">It does not support recursion, so is not useful in a custom key binding.</span></span>

```csharp
void RemoveKeyHandler(string[] key)
```

<span data-ttu-id="bda18-837">Эта функция используется Remove-PSReadLineKeyHandler и, возможно, не слишком полезна в пользовательской привязке ключа.</span><span class="sxs-lookup"><span data-stu-id="bda18-837">This function is used by Remove-PSReadLineKeyHandler and probably isn't too useful in a custom key binding.</span></span>

```csharp
void Replace(int start, int length, string replacement)
```

<span data-ttu-id="bda18-838">Замените некоторые входные данные.</span><span class="sxs-lookup"><span data-stu-id="bda18-838">Replace some of the input.</span></span> <span data-ttu-id="bda18-839">Эта операция поддерживает операцию отмены и повтора.</span><span class="sxs-lookup"><span data-stu-id="bda18-839">This operation supports undo/redo.</span></span> <span data-ttu-id="bda18-840">Это предпочтительнее удаление с последующим вставкой, так как оно обрабатывается как одно действие для отмены.</span><span class="sxs-lookup"><span data-stu-id="bda18-840">This is preferred over Delete followed by Insert because it is treated as a single action for undo.</span></span>

```csharp
void SetCursorPosition(int cursor)
```

<span data-ttu-id="bda18-841">Переместить курсор к заданному смещению.</span><span class="sxs-lookup"><span data-stu-id="bda18-841">Move the cursor to the given offset.</span></span> <span data-ttu-id="bda18-842">Перемещение курсора не ведется для отмены.</span><span class="sxs-lookup"><span data-stu-id="bda18-842">Cursor movement is not tracked for undo.</span></span>

```csharp
void SetOptions(Microsoft.PowerShell.SetPSReadLineOption options)
```

<span data-ttu-id="bda18-843">Эта функция является вспомогательным методом, используемым командлетом Set-PSReadLineOption, но может быть полезен для пользовательской привязки ключа, которая хочет временно изменить параметр.</span><span class="sxs-lookup"><span data-stu-id="bda18-843">This function is a helper method used by the cmdlet Set-PSReadLineOption, but might be useful to a custom key binding that wants to temporarily change a setting.</span></span>

```csharp
bool TryGetArgAsInt(System.Object arg, [ref] int numericArg,
  int defaultNumericArg)
```

<span data-ttu-id="bda18-844">Этот вспомогательный метод используется для пользовательских привязок, которые учитывают Дигитаргумент.</span><span class="sxs-lookup"><span data-stu-id="bda18-844">This helper method is used for custom bindings that honor DigitArgument.</span></span> <span data-ttu-id="bda18-845">Обычный вызов выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="bda18-845">A typical call looks like</span></span>

```powershell
[int]$numericArg = 0
[Microsoft.PowerShell.PSConsoleReadLine]::TryGetArgAsInt($arg,
  [ref]$numericArg, 1)
```

## <a name="note"></a><span data-ttu-id="bda18-846">ПРИМЕЧАНИЕ</span><span class="sxs-lookup"><span data-stu-id="bda18-846">NOTE</span></span>

### <a name="powershell-compatibility"></a><span data-ttu-id="bda18-847">СОВМЕСТИМОСТЬ С POWERSHELL</span><span class="sxs-lookup"><span data-stu-id="bda18-847">POWERSHELL COMPATIBILITY</span></span>

<span data-ttu-id="bda18-848">Для PSReadLine требуется PowerShell 3,0, более поздней версии и узел консоли.</span><span class="sxs-lookup"><span data-stu-id="bda18-848">PSReadLine requires PowerShell 3.0, or newer, and the console host.</span></span> <span data-ttu-id="bda18-849">Он не работает в интегрированной среде сценариев PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bda18-849">It does not work in PowerShell ISE.</span></span> <span data-ttu-id="bda18-850">Она работает в консоли Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="bda18-850">It does work in the console of Visual Studio Code.</span></span>

### <a name="command-history"></a><span data-ttu-id="bda18-851">ЖУРНАЛ КОМАНД</span><span class="sxs-lookup"><span data-stu-id="bda18-851">COMMAND HISTORY</span></span>

<span data-ttu-id="bda18-852">PSReadLine поддерживает файл журнала, содержащий все команды и данные, введенные из командной строки.</span><span class="sxs-lookup"><span data-stu-id="bda18-852">PSReadLine maintains a history file containing all the commands and data you have entered from the command line.</span></span> <span data-ttu-id="bda18-853">Это может быть конфиденциальные данные, включая пароли.</span><span class="sxs-lookup"><span data-stu-id="bda18-853">This may contain sensitive data including passwords.</span></span> <span data-ttu-id="bda18-854">Например, при использовании `ConvertTo-SecureString` командлета пароль заносится в файл журнала в виде обычного текста.</span><span class="sxs-lookup"><span data-stu-id="bda18-854">For example, if you use the `ConvertTo-SecureString` cmdlet the password is logged in the history file as plain text.</span></span> <span data-ttu-id="bda18-855">Файлы журнала — это файл с именем `$($host.Name)_history.txt` .</span><span class="sxs-lookup"><span data-stu-id="bda18-855">The history files is a file named `$($host.Name)_history.txt`.</span></span> <span data-ttu-id="bda18-856">В системах Windows файл журнала хранится в файле `$env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine` .</span><span class="sxs-lookup"><span data-stu-id="bda18-856">On Windows systems the history file is stored at `$env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine`.</span></span> <span data-ttu-id="bda18-857">В системах, отличных от Windows, файлы журнала хранятся в `$env:XDG_DATA_HOME/powershell/PSReadLine` или `$env:HOME/.local/share/powershell/PSReadLine` .</span><span class="sxs-lookup"><span data-stu-id="bda18-857">On non-Windows systems, the history files is stored at `$env:XDG_DATA_HOME/powershell/PSReadLine` or `$env:HOME/.local/share/powershell/PSReadLine`.</span></span>

### <a name="feedback--contributing-to-psreadline"></a><span data-ttu-id="bda18-858">ОБРАТная связь & участие в PSReadLine</span><span class="sxs-lookup"><span data-stu-id="bda18-858">FEEDBACK & CONTRIBUTING TO PSReadLine</span></span>

[<span data-ttu-id="bda18-859">PSReadLine на GitHub</span><span class="sxs-lookup"><span data-stu-id="bda18-859">PSReadLine on GitHub</span></span>](https://github.com/PowerShell/PSReadLine)

<span data-ttu-id="bda18-860">Вы можете отправить запрос на вытягивание или отправить отзыв на страницу GitHub.</span><span class="sxs-lookup"><span data-stu-id="bda18-860">Feel free to submit a pull request or submit feedback on the GitHub page.</span></span>

## <a name="see-also"></a><span data-ttu-id="bda18-861">СМ. ТАКЖЕ</span><span class="sxs-lookup"><span data-stu-id="bda18-861">SEE ALSO</span></span>

<span data-ttu-id="bda18-862">На PSReadLine сильно влияют библиотеки GNU [ReadLine](https://tiswww.case.edu/php/chet/readline/rltop.html) .</span><span class="sxs-lookup"><span data-stu-id="bda18-862">PSReadLine is heavily influenced by the GNU [readline](https://tiswww.case.edu/php/chet/readline/rltop.html) library.</span></span>

