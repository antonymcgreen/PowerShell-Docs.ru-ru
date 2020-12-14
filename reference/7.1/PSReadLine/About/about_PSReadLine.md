---
description: PSReadLine предоставляет улучшенные возможности редактирования командной строки в консоли PowerShell.
keywords: powershell
Locale: en-US
ms.date: 11/16/2020
online version: https://docs.microsoft.com/powershell/module/psreadline/about/about_psreadline?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: О PSReadLine
ms.openlocfilehash: 6d52bb04118914a9ccca5d3442a9d1915c1c2818
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "94692281"
---
# <a name="psreadline"></a><span data-ttu-id="7846e-104">PSReadLine</span><span class="sxs-lookup"><span data-stu-id="7846e-104">PSReadLine</span></span>

## <a name="about_psreadline"></a><span data-ttu-id="7846e-105">about_PSReadLine</span><span class="sxs-lookup"><span data-stu-id="7846e-105">about_PSReadLine</span></span>

## <a name="short-description"></a><span data-ttu-id="7846e-106">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="7846e-106">Short Description</span></span>

<span data-ttu-id="7846e-107">PSReadLine предоставляет улучшенные возможности редактирования командной строки в консоли PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7846e-107">PSReadLine provides an improved command-line editing experience in the PowerShell console.</span></span>

## <a name="long-description"></a><span data-ttu-id="7846e-108">Полное описание</span><span class="sxs-lookup"><span data-stu-id="7846e-108">Long Description</span></span>

<span data-ttu-id="7846e-109">PSReadLine 2,1 предоставляет широкие возможности редактирования командной строки для консоли PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7846e-109">PSReadLine 2.1 provides a powerful command-line editing experience for the PowerShell console.</span></span> <span data-ttu-id="7846e-110">Консоль предоставляет следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="7846e-110">It provides:</span></span>

- <span data-ttu-id="7846e-111">Цветовое выделение синтаксиса командной строки</span><span class="sxs-lookup"><span data-stu-id="7846e-111">Syntax coloring of the command line</span></span>
- <span data-ttu-id="7846e-112">Визуальное обозначение синтаксических ошибок</span><span class="sxs-lookup"><span data-stu-id="7846e-112">A visual indication of syntax errors</span></span>
- <span data-ttu-id="7846e-113">Более эффективный многострочный интерфейс (как редактирование, так и журнал)</span><span class="sxs-lookup"><span data-stu-id="7846e-113">A better multi-line experience (both editing and history)</span></span>
- <span data-ttu-id="7846e-114">Настраиваемые сочетания клавиш</span><span class="sxs-lookup"><span data-stu-id="7846e-114">Customizable key bindings</span></span>
- <span data-ttu-id="7846e-115">Режимы работы cmd и Emacs</span><span class="sxs-lookup"><span data-stu-id="7846e-115">Cmd and Emacs modes</span></span>
- <span data-ttu-id="7846e-116">Множество параметров конфигурации</span><span class="sxs-lookup"><span data-stu-id="7846e-116">Many configuration options</span></span>
- <span data-ttu-id="7846e-117">Завершение стиля bash (необязательно в режиме cmd, по умолчанию в режиме Emacs)</span><span class="sxs-lookup"><span data-stu-id="7846e-117">Bash style completion (optional in Cmd mode, default in Emacs mode)</span></span>
- <span data-ttu-id="7846e-118">Emacs: Янк/Kill-Ring</span><span class="sxs-lookup"><span data-stu-id="7846e-118">Emacs yank/kill-ring</span></span>
- <span data-ttu-id="7846e-119">Перемещение и уничтожение токена PowerShell на основе маркеров "Word"</span><span class="sxs-lookup"><span data-stu-id="7846e-119">PowerShell token based "word" movement and kill</span></span>
- <span data-ttu-id="7846e-120">Прогнозирование IntelliSense</span><span class="sxs-lookup"><span data-stu-id="7846e-120">Predictive IntelliSense</span></span>

<span data-ttu-id="7846e-121">Для PSReadLine требуется PowerShell 3,0, более поздней версии и узел консоли.</span><span class="sxs-lookup"><span data-stu-id="7846e-121">PSReadLine requires PowerShell 3.0, or newer, and the console host.</span></span> <span data-ttu-id="7846e-122">Он не работает в интегрированной среде сценариев PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7846e-122">It does not work in PowerShell ISE.</span></span> <span data-ttu-id="7846e-123">Она работает в консоли Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="7846e-123">It does work in the console of Visual Studio Code.</span></span>

<span data-ttu-id="7846e-124">PSReadLine 2.1.0 поставляется с PowerShell 7,1 и поддерживается во всех поддерживаемых версиях PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7846e-124">PSReadLine 2.1.0 ships with PowerShell 7.1 and is supported in all supported versions of PowerShell.</span></span> <span data-ttu-id="7846e-125">Его можно установить из коллекция PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7846e-125">It is available to install from the PowerShell Gallery.</span></span>
<span data-ttu-id="7846e-126">Чтобы установить PSReadLine 2.1.0 в поддерживаемой версии PowerShell, выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="7846e-126">To install PSReadLine 2.1.0 in a supported version of PowerShell run the following command.</span></span>

```powershell
Install-Module -Name PSReadLine -RequiredVersion 2.1.0
```

> [!NOTE]
> <span data-ttu-id="7846e-127">Начиная с PowerShell 7,0, PowerShell пропускает автоматическую загрузку PSReadLine в Windows при обнаружении программы чтения с экрана.</span><span class="sxs-lookup"><span data-stu-id="7846e-127">Beginning with PowerShell 7.0, PowerShell skips auto-loading PSReadLine on Windows if a screen reader program is detected.</span></span> <span data-ttu-id="7846e-128">В настоящее время PSReadLine плохо работает с программами чтения с экрана.</span><span class="sxs-lookup"><span data-stu-id="7846e-128">Currently, PSReadLine doesn't work well with the screen readers.</span></span> <span data-ttu-id="7846e-129">Визуализация и форматирование по умолчанию для PowerShell 7,0 в Windows работают правильно.</span><span class="sxs-lookup"><span data-stu-id="7846e-129">The default rendering and formatting of PowerShell 7.0 on Windows works properly.</span></span> <span data-ttu-id="7846e-130">При необходимости модуль можно загрузить вручную.</span><span class="sxs-lookup"><span data-stu-id="7846e-130">You can manually load the module if necessary.</span></span>

## <a name="predictive-intellisense"></a><span data-ttu-id="7846e-131">Прогнозирование IntelliSense</span><span class="sxs-lookup"><span data-stu-id="7846e-131">Predictive IntelliSense</span></span>

<span data-ttu-id="7846e-132">Прогнозная IntelliSense является дополнением к концепции заполнения нажатием клавиши TAB, которая помогает пользователю успешно завершать команды.</span><span class="sxs-lookup"><span data-stu-id="7846e-132">Predictive IntelliSense is an addition to the concept of tab completion that assists the user in successfully completing commands.</span></span> <span data-ttu-id="7846e-133">Она позволяет пользователям обнаруживать, изменять и выполнять полные команды на основе прогнозов, находящихся в истории пользователя, и дополнительных подключаемых модулей для конкретных доменов.</span><span class="sxs-lookup"><span data-stu-id="7846e-133">It enables users to discover, edit, and execute full commands based on matching predictions from the user's history and additional domain specific plugins.</span></span>

### <a name="enable-predictive-intellisense"></a><span data-ttu-id="7846e-134">Включение прогнозного IntelliSense</span><span class="sxs-lookup"><span data-stu-id="7846e-134">Enable Predictive IntelliSense</span></span>

<span data-ttu-id="7846e-135">По умолчанию прогнозная технология IntelliSense отключена.</span><span class="sxs-lookup"><span data-stu-id="7846e-135">Predictive IntelliSense is disabled by default.</span></span> <span data-ttu-id="7846e-136">Чтобы включить прогнозы, просто выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="7846e-136">To enable predictions, just run the following command:</span></span>

```powershell
Set-PSReadLineOption -PredictionSource History
```

<span data-ttu-id="7846e-137">Параметр **предиктионсаурце** также может принимать подключаемые модули для конкретных требований, связанных с доменами, и пользовательскими требованиями.</span><span class="sxs-lookup"><span data-stu-id="7846e-137">The **PredictionSource** parameter can also accept plugins for domain specific and custom requirements.</span></span>

<span data-ttu-id="7846e-138">Чтобы отключить прогнозную IntelliSense, просто выполните команду:</span><span class="sxs-lookup"><span data-stu-id="7846e-138">To disable Predictive IntelliSense, just run:</span></span>

```powershell
Set-PSReadLineOption -PredictionSource None
```

<span data-ttu-id="7846e-139">В классе **[Microsoft. PowerShell. псконсолереадлине]** доступны следующие функции.</span><span class="sxs-lookup"><span data-stu-id="7846e-139">The following functions are available in the class **[Microsoft.PowerShell.PSConsoleReadLine]**.</span></span>

## <a name="basic-editing-functions"></a><span data-ttu-id="7846e-140">Базовые функции редактирования</span><span class="sxs-lookup"><span data-stu-id="7846e-140">Basic editing functions</span></span>

### <a name="abort"></a><span data-ttu-id="7846e-141">Прерывание</span><span class="sxs-lookup"><span data-stu-id="7846e-141">Abort</span></span>

<span data-ttu-id="7846e-142">Прервать текущее действие, например добавочный поиск по журналу.</span><span class="sxs-lookup"><span data-stu-id="7846e-142">Abort current action, e.g. incremental history search.</span></span>

- <span data-ttu-id="7846e-143">Emacs: `<Ctrl+g>`</span><span class="sxs-lookup"><span data-stu-id="7846e-143">Emacs: `<Ctrl+g>`</span></span>

### <a name="acceptandgetnext"></a><span data-ttu-id="7846e-144">акцептанджетнекст</span><span class="sxs-lookup"><span data-stu-id="7846e-144">AcceptAndGetNext</span></span>

<span data-ttu-id="7846e-145">Попытка выполнить текущий вход.</span><span class="sxs-lookup"><span data-stu-id="7846e-145">Attempt to execute the current input.</span></span> <span data-ttu-id="7846e-146">Если его можно выполнить (например, Акцептлине), то следует отозвать следующий элемент из журнала при следующем вызове метода ReadLine.</span><span class="sxs-lookup"><span data-stu-id="7846e-146">If it can be executed (like AcceptLine), then recall the next item from history the next time ReadLine is called.</span></span>

- <span data-ttu-id="7846e-147">Emacs: `<Ctrl+o>`</span><span class="sxs-lookup"><span data-stu-id="7846e-147">Emacs: `<Ctrl+o>`</span></span>

### <a name="acceptline"></a><span data-ttu-id="7846e-148">акцептлине</span><span class="sxs-lookup"><span data-stu-id="7846e-148">AcceptLine</span></span>

<span data-ttu-id="7846e-149">Попытка выполнить текущий вход.</span><span class="sxs-lookup"><span data-stu-id="7846e-149">Attempt to execute the current input.</span></span> <span data-ttu-id="7846e-150">Если текущий ввод неполон (например, отсутствует закрывающая круглая скобка, квадратная скобка или кавычка, запрос продолжения отображается на следующей строке, а PSReadLine ожидает ввода ключей для изменения текущих входных данных.</span><span class="sxs-lookup"><span data-stu-id="7846e-150">If the current input is incomplete (for example there is a missing closing parenthesis, bracket, or quote, then the continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span>

- <span data-ttu-id="7846e-151">Процессор `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="7846e-151">Cmd: `<Enter>`</span></span>
- <span data-ttu-id="7846e-152">Emacs: `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="7846e-152">Emacs: `<Enter>`</span></span>
- <span data-ttu-id="7846e-153">Режим вставки в VI: `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="7846e-153">Vi insert mode: `<Enter>`</span></span>

### <a name="addline"></a><span data-ttu-id="7846e-154">аддлине</span><span class="sxs-lookup"><span data-stu-id="7846e-154">AddLine</span></span>

<span data-ttu-id="7846e-155">Запрос продолжения отображается на следующей строке, а PSReadLine ожидает ввода ключей для изменения текущих входных данных.</span><span class="sxs-lookup"><span data-stu-id="7846e-155">The continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span> <span data-ttu-id="7846e-156">Это полезно для ввода многострочных входных данных в виде одной команды, даже если одна строка завершается самим вводом.</span><span class="sxs-lookup"><span data-stu-id="7846e-156">This is useful to enter multi-line input as a single command even when a single line is complete input by itself.</span></span>

- <span data-ttu-id="7846e-157">Процессор `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="7846e-157">Cmd: `<Shift+Enter>`</span></span>
- <span data-ttu-id="7846e-158">Emacs: `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="7846e-158">Emacs: `<Shift+Enter>`</span></span>
- <span data-ttu-id="7846e-159">Режим вставки в VI: `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="7846e-159">Vi insert mode: `<Shift+Enter>`</span></span>
- <span data-ttu-id="7846e-160">Режим команд VI: `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="7846e-160">Vi command mode: `<Shift+Enter>`</span></span>

### <a name="backwarddeletechar"></a><span data-ttu-id="7846e-161">бакквардделетечар</span><span class="sxs-lookup"><span data-stu-id="7846e-161">BackwardDeleteChar</span></span>

<span data-ttu-id="7846e-162">Удалить символ перед курсором.</span><span class="sxs-lookup"><span data-stu-id="7846e-162">Delete the character before the cursor.</span></span>

- <span data-ttu-id="7846e-163">Cmd: `<Backspace>` , `<Ctrl+h>`</span><span class="sxs-lookup"><span data-stu-id="7846e-163">Cmd: `<Backspace>`, `<Ctrl+h>`</span></span>
- <span data-ttu-id="7846e-164">Emacs: `<Backspace>` , `<Ctrl+Backspace>` , `<Ctrl+h>`</span><span class="sxs-lookup"><span data-stu-id="7846e-164">Emacs: `<Backspace>`, `<Ctrl+Backspace>`, `<Ctrl+h>`</span></span>
- <span data-ttu-id="7846e-165">Режим вставки в VI: `<Backspace>`</span><span class="sxs-lookup"><span data-stu-id="7846e-165">Vi insert mode: `<Backspace>`</span></span>
- <span data-ttu-id="7846e-166">Режим команд VI: `<X>` , `<d,h>`</span><span class="sxs-lookup"><span data-stu-id="7846e-166">Vi command mode: `<X>`, `<d,h>`</span></span>

### <a name="backwarddeleteline"></a><span data-ttu-id="7846e-167">бакквардделетелине</span><span class="sxs-lookup"><span data-stu-id="7846e-167">BackwardDeleteLine</span></span>

<span data-ttu-id="7846e-168">Like Бакквардкилллине — удаляет текст с точки до начала строки, но не помещает удаленный текст в инструкцию KILL-Ring.</span><span class="sxs-lookup"><span data-stu-id="7846e-168">Like BackwardKillLine - deletes text from the point to the start of the line, but does not put the deleted text in the kill-ring.</span></span>

- <span data-ttu-id="7846e-169">Процессор `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="7846e-169">Cmd: `<Ctrl+Home>`</span></span>
- <span data-ttu-id="7846e-170">Режим вставки в VI: `<Ctrl+u>` , `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="7846e-170">Vi insert mode: `<Ctrl+u>`, `<Ctrl+Home>`</span></span>
- <span data-ttu-id="7846e-171">Режим команд VI: `<Ctrl+u>` , `<Ctrl+Home>` , `<d,0>`</span><span class="sxs-lookup"><span data-stu-id="7846e-171">Vi command mode: `<Ctrl+u>`, `<Ctrl+Home>`, `<d,0>`</span></span>

### <a name="backwarddeleteword"></a><span data-ttu-id="7846e-172">бакквардделетеворд</span><span class="sxs-lookup"><span data-stu-id="7846e-172">BackwardDeleteWord</span></span>

<span data-ttu-id="7846e-173">Удаляет предыдущее слово.</span><span class="sxs-lookup"><span data-stu-id="7846e-173">Deletes the previous word.</span></span>

- <span data-ttu-id="7846e-174">Режим команд VI: `<Ctrl+w>` , `<d,b>`</span><span class="sxs-lookup"><span data-stu-id="7846e-174">Vi command mode: `<Ctrl+w>`, `<d,b>`</span></span>

### <a name="backwardkillline"></a><span data-ttu-id="7846e-175">бакквардкилллине</span><span class="sxs-lookup"><span data-stu-id="7846e-175">BackwardKillLine</span></span>

<span data-ttu-id="7846e-176">Очистить входные данные от начала ввода до курсора.</span><span class="sxs-lookup"><span data-stu-id="7846e-176">Clear the input from the start of the input to the cursor.</span></span> <span data-ttu-id="7846e-177">Очистка текста помещается в буфер Kill.</span><span class="sxs-lookup"><span data-stu-id="7846e-177">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="7846e-178">Emacs: `<Ctrl+u>` , `<Ctrl+x,Backspace>`</span><span class="sxs-lookup"><span data-stu-id="7846e-178">Emacs: `<Ctrl+u>`, `<Ctrl+x,Backspace>`</span></span>

### <a name="backwardkillword"></a><span data-ttu-id="7846e-179">бакквардкиллворд</span><span class="sxs-lookup"><span data-stu-id="7846e-179">BackwardKillWord</span></span>

<span data-ttu-id="7846e-180">Очистить ввод от начала текущего слова до курсора.</span><span class="sxs-lookup"><span data-stu-id="7846e-180">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="7846e-181">Если курсор находится между словами, входные данные очищаются от начала предыдущего слова до курсора.</span><span class="sxs-lookup"><span data-stu-id="7846e-181">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="7846e-182">Очистка текста помещается в буфер Kill.</span><span class="sxs-lookup"><span data-stu-id="7846e-182">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="7846e-183">Cmd: `<Ctrl+Backspace>` , `<Ctrl+w>`</span><span class="sxs-lookup"><span data-stu-id="7846e-183">Cmd: `<Ctrl+Backspace>`, `<Ctrl+w>`</span></span>
- <span data-ttu-id="7846e-184">Emacs: `<Alt+Backspace>` , `<Escape,Backspace>`</span><span class="sxs-lookup"><span data-stu-id="7846e-184">Emacs: `<Alt+Backspace>`, `<Escape,Backspace>`</span></span>
- <span data-ttu-id="7846e-185">Режим вставки в VI: `<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="7846e-185">Vi insert mode: `<Ctrl+Backspace>`</span></span>
- <span data-ttu-id="7846e-186">Режим команд VI: `<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="7846e-186">Vi command mode: `<Ctrl+Backspace>`</span></span>

### <a name="cancelline"></a><span data-ttu-id="7846e-187">канцеллине</span><span class="sxs-lookup"><span data-stu-id="7846e-187">CancelLine</span></span>

<span data-ttu-id="7846e-188">Отмена текущих входных данных с выходом на экран, но возврат к узлу, чтобы снова выполнить оценку запроса.</span><span class="sxs-lookup"><span data-stu-id="7846e-188">Cancel the current input, leaving the input on the screen, but returns back to the host so the prompt is evaluated again.</span></span>

- <span data-ttu-id="7846e-189">Режим вставки в VI: `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="7846e-189">Vi insert mode: `<Ctrl+c>`</span></span>
- <span data-ttu-id="7846e-190">Режим команд VI: `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="7846e-190">Vi command mode: `<Ctrl+c>`</span></span>

### <a name="copy"></a><span data-ttu-id="7846e-191">Копировать</span><span class="sxs-lookup"><span data-stu-id="7846e-191">Copy</span></span>

<span data-ttu-id="7846e-192">Копировать выбранный регион в буфер обмена системы.</span><span class="sxs-lookup"><span data-stu-id="7846e-192">Copy selected region to the system clipboard.</span></span> <span data-ttu-id="7846e-193">Если регион не выбран, скопируйте всю строку.</span><span class="sxs-lookup"><span data-stu-id="7846e-193">If no region is selected, copy the whole line.</span></span>

- <span data-ttu-id="7846e-194">Процессор `<Ctrl+C>`</span><span class="sxs-lookup"><span data-stu-id="7846e-194">Cmd: `<Ctrl+C>`</span></span>

### <a name="copyorcancelline"></a><span data-ttu-id="7846e-195">копйорканцеллине</span><span class="sxs-lookup"><span data-stu-id="7846e-195">CopyOrCancelLine</span></span>

<span data-ttu-id="7846e-196">Если выбран текст, скопируйте в буфер обмена, в противном случае отмените строку.</span><span class="sxs-lookup"><span data-stu-id="7846e-196">If text is selected, copy to the clipboard, otherwise cancel the line.</span></span>

- <span data-ttu-id="7846e-197">Процессор `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="7846e-197">Cmd: `<Ctrl+c>`</span></span>
- <span data-ttu-id="7846e-198">Emacs: `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="7846e-198">Emacs: `<Ctrl+c>`</span></span>

### <a name="cut"></a><span data-ttu-id="7846e-199">Вырезать</span><span class="sxs-lookup"><span data-stu-id="7846e-199">Cut</span></span>

<span data-ttu-id="7846e-200">Удалить выбранный регион, поместив удаленный текст в системный буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="7846e-200">Delete selected region placing deleted text in the system clipboard.</span></span>

- <span data-ttu-id="7846e-201">Процессор `<Ctrl+x>`</span><span class="sxs-lookup"><span data-stu-id="7846e-201">Cmd: `<Ctrl+x>`</span></span>

### <a name="deletechar"></a><span data-ttu-id="7846e-202">делетечар</span><span class="sxs-lookup"><span data-stu-id="7846e-202">DeleteChar</span></span>

<span data-ttu-id="7846e-203">Удалите символ под курсором.</span><span class="sxs-lookup"><span data-stu-id="7846e-203">Delete the character under the cursor.</span></span>

- <span data-ttu-id="7846e-204">Процессор `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="7846e-204">Cmd: `<Delete>`</span></span>
- <span data-ttu-id="7846e-205">Emacs: `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="7846e-205">Emacs: `<Delete>`</span></span>
- <span data-ttu-id="7846e-206">Режим вставки в VI: `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="7846e-206">Vi insert mode: `<Delete>`</span></span>
- <span data-ttu-id="7846e-207">Режим команд VI: `<Delete>` , `<x>` , `<d,l>` , `<d,Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="7846e-207">Vi command mode: `<Delete>`, `<x>`, `<d,l>`, `<d,Spacebar>`</span></span>

### <a name="deletecharorexit"></a><span data-ttu-id="7846e-208">делетечарорексит</span><span class="sxs-lookup"><span data-stu-id="7846e-208">DeleteCharOrExit</span></span>

<span data-ttu-id="7846e-209">Удалите символ под курсором или, если строка пуста, завершите процесс.</span><span class="sxs-lookup"><span data-stu-id="7846e-209">Delete the character under the cursor, or if the line is empty, exit the process.</span></span>

- <span data-ttu-id="7846e-210">Emacs: `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="7846e-210">Emacs: `<Ctrl+d>`</span></span>

### <a name="deleteendofbuffer"></a><span data-ttu-id="7846e-211">делетиндофбуффер</span><span class="sxs-lookup"><span data-stu-id="7846e-211">DeleteEndOfBuffer</span></span>

<span data-ttu-id="7846e-212">Удаляет до конца многострочного буфера.</span><span class="sxs-lookup"><span data-stu-id="7846e-212">Deletes to the end of the multiline buffer.</span></span>

- <span data-ttu-id="7846e-213">Режим команд VI: `<d,G>`</span><span class="sxs-lookup"><span data-stu-id="7846e-213">Vi command mode: `<d,G>`</span></span>

### <a name="deleteendofword"></a><span data-ttu-id="7846e-214">делетиндофворд</span><span class="sxs-lookup"><span data-stu-id="7846e-214">DeleteEndOfWord</span></span>

<span data-ttu-id="7846e-215">Удалить до конца слова.</span><span class="sxs-lookup"><span data-stu-id="7846e-215">Delete to the end of the word.</span></span>

- <span data-ttu-id="7846e-216">Режим команд VI: `<d,e>`</span><span class="sxs-lookup"><span data-stu-id="7846e-216">Vi command mode: `<d,e>`</span></span>

### <a name="deleteline"></a><span data-ttu-id="7846e-217">Сбой deleteline</span><span class="sxs-lookup"><span data-stu-id="7846e-217">DeleteLine</span></span>

<span data-ttu-id="7846e-218">Удаляет текущую логическую строку многострочного буфера, включая отмену.</span><span class="sxs-lookup"><span data-stu-id="7846e-218">Deletes the current logical line of a multiline buffer, enabling undo.</span></span>

- <span data-ttu-id="7846e-219">Режим команд VI: `<d,d>` , `<d,_>`</span><span class="sxs-lookup"><span data-stu-id="7846e-219">Vi command mode: `<d,d>`, `<d,_>`</span></span>

### <a name="deletepreviouslines"></a><span data-ttu-id="7846e-220">делетепревиауслинес</span><span class="sxs-lookup"><span data-stu-id="7846e-220">DeletePreviousLines</span></span>

<span data-ttu-id="7846e-221">Удаляет предыдущие запрошенные логические строки и текущую логическую строку в многострочном буфере.</span><span class="sxs-lookup"><span data-stu-id="7846e-221">Deletes the previous requested logical lines and the current logical line in a multiline buffer.</span></span>

- <span data-ttu-id="7846e-222">Режим команд VI: `<d,k>`</span><span class="sxs-lookup"><span data-stu-id="7846e-222">Vi command mode: `<d,k>`</span></span>

### <a name="deleterelativelines"></a><span data-ttu-id="7846e-223">делетерелативелинес</span><span class="sxs-lookup"><span data-stu-id="7846e-223">DeleteRelativeLines</span></span>

<span data-ttu-id="7846e-224">Удаляет с начала буфера до текущей логической строки в многострочном буфере.</span><span class="sxs-lookup"><span data-stu-id="7846e-224">Deletes from the beginning of the buffer to the current logical line in a multiline buffer.</span></span>

<span data-ttu-id="7846e-225">Как и в большинстве команд VI, `<d,g,g>` команду можно добавить в начало с числовым аргументом, который указывает абсолютный номер строки, который вместе с текущим номером строки позволяет удалить диапазон строк.</span><span class="sxs-lookup"><span data-stu-id="7846e-225">As most Vi commands, the `<d,g,g>` command can be prepended with a numeric argument that specifies an absolute line number, which, together with the current line number, make up a range of lines to be deleted.</span></span>
<span data-ttu-id="7846e-226">Если не указано, числовой аргумент по умолчанию равен 1, что означает первую логическую строку в многострочном буфере.</span><span class="sxs-lookup"><span data-stu-id="7846e-226">If not specified, the numeric argument defaults to 1, which refers to the first logical line in a multiline buffer.</span></span>

<span data-ttu-id="7846e-227">Фактическое число строк, удаляемых из многострочного, вычисляются как разница между текущим логическим номером и заданным числовым аргументом, который, таким образом, может быть отрицательным.</span><span class="sxs-lookup"><span data-stu-id="7846e-227">The actual number of lines to be deleted from the multiline is computed as the difference between the current logical line number and the specified numeric argument, which can thus be negative.</span></span> <span data-ttu-id="7846e-228">Поэтому это _Относительная_ часть имени метода.</span><span class="sxs-lookup"><span data-stu-id="7846e-228">Hence the _relative_ part of method name.</span></span>

- <span data-ttu-id="7846e-229">Режим команд VI: `<d,g,g>`</span><span class="sxs-lookup"><span data-stu-id="7846e-229">Vi command mode: `<d,g,g>`</span></span>

### <a name="deletenextlines"></a><span data-ttu-id="7846e-230">делетенекстлинес</span><span class="sxs-lookup"><span data-stu-id="7846e-230">DeleteNextLines</span></span>

<span data-ttu-id="7846e-231">Удаляет текущую логическую строку и следующие запрошенные логические строки в многострочном буфере.</span><span class="sxs-lookup"><span data-stu-id="7846e-231">Deletes the current logical line and the next requested logical lines in a multiline buffer.</span></span>

- <span data-ttu-id="7846e-232">Режим команд VI: `<d,j>`</span><span class="sxs-lookup"><span data-stu-id="7846e-232">Vi command mode: `<d,j>`</span></span>

### <a name="deletelinetofirstchar"></a><span data-ttu-id="7846e-233">делетелинетофирстчар</span><span class="sxs-lookup"><span data-stu-id="7846e-233">DeleteLineToFirstChar</span></span>

<span data-ttu-id="7846e-234">Удаляет текст из курсора на первый символ строки, отличный от пробела.</span><span class="sxs-lookup"><span data-stu-id="7846e-234">Deletes text from the cursor to the first non-blank character of the line.</span></span>

- <span data-ttu-id="7846e-235">Режим команд VI: `<d,^>`</span><span class="sxs-lookup"><span data-stu-id="7846e-235">Vi command mode: `<d,^>`</span></span>

### <a name="deletetoend"></a><span data-ttu-id="7846e-236">делететоенд</span><span class="sxs-lookup"><span data-stu-id="7846e-236">DeleteToEnd</span></span>

<span data-ttu-id="7846e-237">Удалить до конца строки.</span><span class="sxs-lookup"><span data-stu-id="7846e-237">Delete to the end of the line.</span></span>

- <span data-ttu-id="7846e-238">Режим команд VI: `<D>` , `<d,$>`</span><span class="sxs-lookup"><span data-stu-id="7846e-238">Vi command mode: `<D>`, `<d,$>`</span></span>

### <a name="deleteword"></a><span data-ttu-id="7846e-239">DeleteWord</span><span class="sxs-lookup"><span data-stu-id="7846e-239">DeleteWord</span></span>

<span data-ttu-id="7846e-240">Удалить следующее слово.</span><span class="sxs-lookup"><span data-stu-id="7846e-240">Delete the next word.</span></span>

- <span data-ttu-id="7846e-241">Режим команд VI: `<d,w>`</span><span class="sxs-lookup"><span data-stu-id="7846e-241">Vi command mode: `<d,w>`</span></span>

### <a name="forwarddeleteline"></a><span data-ttu-id="7846e-242">форвардделетелине</span><span class="sxs-lookup"><span data-stu-id="7846e-242">ForwardDeleteLine</span></span>

<span data-ttu-id="7846e-243">Как и Форвардкилллине — удаляет текст с точки до конца строки, но не помещает удаленный текст в инструкцию KILL-Ring.</span><span class="sxs-lookup"><span data-stu-id="7846e-243">Like ForwardKillLine - deletes text from the point to the end of the line, but does not put the deleted text in the kill-ring.</span></span>

- <span data-ttu-id="7846e-244">Процессор `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="7846e-244">Cmd: `<Ctrl+End>`</span></span>
- <span data-ttu-id="7846e-245">Режим вставки в VI: `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="7846e-245">Vi insert mode: `<Ctrl+End>`</span></span>
- <span data-ttu-id="7846e-246">Режим команд VI: `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="7846e-246">Vi command mode: `<Ctrl+End>`</span></span>

### <a name="insertlineabove"></a><span data-ttu-id="7846e-247">инсертлинеабове</span><span class="sxs-lookup"><span data-stu-id="7846e-247">InsertLineAbove</span></span>

<span data-ttu-id="7846e-248">Новая пустая строка создается над текущей строкой, независимо от того, где находится курсор на текущей строке.</span><span class="sxs-lookup"><span data-stu-id="7846e-248">A new empty line is created above the current line regardless of where the cursor is on the current line.</span></span> <span data-ttu-id="7846e-249">Курсор переместится в начало новой строки.</span><span class="sxs-lookup"><span data-stu-id="7846e-249">The cursor moves to the beginning of the new line.</span></span>

- <span data-ttu-id="7846e-250">Процессор `<Ctrl+Enter>`</span><span class="sxs-lookup"><span data-stu-id="7846e-250">Cmd: `<Ctrl+Enter>`</span></span>

### <a name="insertlinebelow"></a><span data-ttu-id="7846e-251">инсертлинебелов</span><span class="sxs-lookup"><span data-stu-id="7846e-251">InsertLineBelow</span></span>

<span data-ttu-id="7846e-252">Новая пустая строка создается под текущей строкой независимо от того, где находится курсор на текущей строке.</span><span class="sxs-lookup"><span data-stu-id="7846e-252">A new empty line is created below the current line regardless of where the cursor is on the current line.</span></span> <span data-ttu-id="7846e-253">Курсор переместится в начало новой строки.</span><span class="sxs-lookup"><span data-stu-id="7846e-253">The cursor moves to the beginning of the new line.</span></span>

- <span data-ttu-id="7846e-254">Процессор `<Shift+Ctrl+Enter>`</span><span class="sxs-lookup"><span data-stu-id="7846e-254">Cmd: `<Shift+Ctrl+Enter>`</span></span>

### <a name="invertcase"></a><span data-ttu-id="7846e-255">инверткасе</span><span class="sxs-lookup"><span data-stu-id="7846e-255">InvertCase</span></span>

<span data-ttu-id="7846e-256">Инвертировать регистр текущего символа и перейти к следующему.</span><span class="sxs-lookup"><span data-stu-id="7846e-256">Invert the case of the current character and move to the next one.</span></span>

- <span data-ttu-id="7846e-257">Режим команд VI: `<~>`</span><span class="sxs-lookup"><span data-stu-id="7846e-257">Vi command mode: `<~>`</span></span>

### <a name="killline"></a><span data-ttu-id="7846e-258">килллине</span><span class="sxs-lookup"><span data-stu-id="7846e-258">KillLine</span></span>

<span data-ttu-id="7846e-259">Очистить входные данные от курсора до конца входных данных.</span><span class="sxs-lookup"><span data-stu-id="7846e-259">Clear the input from the cursor to the end of the input.</span></span> <span data-ttu-id="7846e-260">Очистка текста помещается в буфер Kill.</span><span class="sxs-lookup"><span data-stu-id="7846e-260">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="7846e-261">Emacs: `<Ctrl+k>`</span><span class="sxs-lookup"><span data-stu-id="7846e-261">Emacs: `<Ctrl+k>`</span></span>

### <a name="killregion"></a><span data-ttu-id="7846e-262">киллрегион</span><span class="sxs-lookup"><span data-stu-id="7846e-262">KillRegion</span></span>

<span data-ttu-id="7846e-263">Удалить текст между курсором и меткой.</span><span class="sxs-lookup"><span data-stu-id="7846e-263">Kill the text between the cursor and the mark.</span></span>

- <span data-ttu-id="7846e-264">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="7846e-264">Function is unbound.</span></span>

### <a name="killword"></a><span data-ttu-id="7846e-265">киллворд</span><span class="sxs-lookup"><span data-stu-id="7846e-265">KillWord</span></span>

<span data-ttu-id="7846e-266">Очистить ввод от курсора до конца текущего слова.</span><span class="sxs-lookup"><span data-stu-id="7846e-266">Clear the input from the cursor to the end of the current word.</span></span> <span data-ttu-id="7846e-267">Если курсор находится между словами, входные данные очищаются от курсора до конца следующего слова.</span><span class="sxs-lookup"><span data-stu-id="7846e-267">If the cursor is between words, the input is cleared from the cursor to the end of the next word.</span></span> <span data-ttu-id="7846e-268">Очистка текста помещается в буфер Kill.</span><span class="sxs-lookup"><span data-stu-id="7846e-268">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="7846e-269">Cmd: `<Alt+d>` , `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="7846e-269">Cmd: `<Alt+d>`, `<Ctrl+Delete>`</span></span>
- <span data-ttu-id="7846e-270">Emacs: `<Alt+d>` , `<Escape,d>`</span><span class="sxs-lookup"><span data-stu-id="7846e-270">Emacs: `<Alt+d>`, `<Escape,d>`</span></span>
- <span data-ttu-id="7846e-271">Режим вставки в VI: `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="7846e-271">Vi insert mode: `<Ctrl+Delete>`</span></span>
- <span data-ttu-id="7846e-272">Режим команд VI: `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="7846e-272">Vi command mode: `<Ctrl+Delete>`</span></span>

### <a name="paste"></a><span data-ttu-id="7846e-273">Вставить</span><span class="sxs-lookup"><span data-stu-id="7846e-273">Paste</span></span>

<span data-ttu-id="7846e-274">Вставка текста из буфера обмена системы.</span><span class="sxs-lookup"><span data-stu-id="7846e-274">Paste text from the system clipboard.</span></span>

- <span data-ttu-id="7846e-275">Cmd: `<Ctrl+v>` , `<Shift+Insert>`</span><span class="sxs-lookup"><span data-stu-id="7846e-275">Cmd: `<Ctrl+v>`, `<Shift+Insert>`</span></span>
- <span data-ttu-id="7846e-276">Режим вставки в VI: `<Ctrl+v>`</span><span class="sxs-lookup"><span data-stu-id="7846e-276">Vi insert mode: `<Ctrl+v>`</span></span>
- <span data-ttu-id="7846e-277">Режим команд VI: `<Ctrl+v>`</span><span class="sxs-lookup"><span data-stu-id="7846e-277">Vi command mode: `<Ctrl+v>`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7846e-278">При использовании функции **вставки** все содержимое буфера буфера обмена вставляется во входной буфер PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="7846e-278">When using the **Paste** function, the entire contents of the clipboard buffer is pasted into the input buffer of PSReadLine.</span></span> <span data-ttu-id="7846e-279">Затем входной буфер передается средству синтаксического анализа PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7846e-279">The input buffer is then passed to the PowerShell parser.</span></span> <span data-ttu-id="7846e-280">Вход, вставленный с помощью консольного приложения, щелкните **правой кнопкой мыши** метод вставки, скопированный во входной буфер по одному символу за раз.</span><span class="sxs-lookup"><span data-stu-id="7846e-280">Input pasted using the console application's **right-click** paste method is copied to the input buffer one character at a time.</span></span> <span data-ttu-id="7846e-281">Входной буфер передается средству синтаксического анализа при копировании символа новой строки.</span><span class="sxs-lookup"><span data-stu-id="7846e-281">The input buffer is passed to the parser when a newline character is copied.</span></span> <span data-ttu-id="7846e-282">Поэтому входные данные анализируются по одной строке за раз.</span><span class="sxs-lookup"><span data-stu-id="7846e-282">Therefore, the input is parsed one line at a time.</span></span> <span data-ttu-id="7846e-283">Различие между методами вставки приводит к различному поведению при выполнении.</span><span class="sxs-lookup"><span data-stu-id="7846e-283">The difference between paste methods results in different execution behavior.</span></span>

### <a name="pasteafter"></a><span data-ttu-id="7846e-284">пастеафтер</span><span class="sxs-lookup"><span data-stu-id="7846e-284">PasteAfter</span></span>

<span data-ttu-id="7846e-285">Вставьте буфер обмена после курсора, переместив курсор в конец вставленного текста.</span><span class="sxs-lookup"><span data-stu-id="7846e-285">Paste the clipboard after the cursor, moving the cursor to the end of the pasted text.</span></span>

- <span data-ttu-id="7846e-286">Режим команд VI: `<p>`</span><span class="sxs-lookup"><span data-stu-id="7846e-286">Vi command mode: `<p>`</span></span>

### <a name="pastebefore"></a><span data-ttu-id="7846e-287">пастебефоре</span><span class="sxs-lookup"><span data-stu-id="7846e-287">PasteBefore</span></span>

<span data-ttu-id="7846e-288">Вставьте буфер обмена перед курсором, переместив курсор в конец вставленного текста.</span><span class="sxs-lookup"><span data-stu-id="7846e-288">Paste the clipboard before the cursor, moving the cursor to the end of the pasted text.</span></span>

- <span data-ttu-id="7846e-289">Режим команд VI: `<P>`</span><span class="sxs-lookup"><span data-stu-id="7846e-289">Vi command mode: `<P>`</span></span>

### <a name="prependandaccept"></a><span data-ttu-id="7846e-290">препендандакцепт</span><span class="sxs-lookup"><span data-stu-id="7846e-290">PrependAndAccept</span></span>

<span data-ttu-id="7846e-291">Добавьте в начало "#" и примите строку.</span><span class="sxs-lookup"><span data-stu-id="7846e-291">Prepend a '#' and accept the line.</span></span>

- <span data-ttu-id="7846e-292">Режим команд VI: `<#>`</span><span class="sxs-lookup"><span data-stu-id="7846e-292">Vi command mode: `<#>`</span></span>

### <a name="redo"></a><span data-ttu-id="7846e-293">Повторить</span><span class="sxs-lookup"><span data-stu-id="7846e-293">Redo</span></span>

<span data-ttu-id="7846e-294">Отмена отмены.</span><span class="sxs-lookup"><span data-stu-id="7846e-294">Undo an undo.</span></span>

- <span data-ttu-id="7846e-295">Процессор `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="7846e-295">Cmd: `<Ctrl+y>`</span></span>
- <span data-ttu-id="7846e-296">Режим вставки в VI: `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="7846e-296">Vi insert mode: `<Ctrl+y>`</span></span>
- <span data-ttu-id="7846e-297">Режим команд VI: `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="7846e-297">Vi command mode: `<Ctrl+y>`</span></span>

### <a name="repeatlastcommand"></a><span data-ttu-id="7846e-298">репеатласткомманд</span><span class="sxs-lookup"><span data-stu-id="7846e-298">RepeatLastCommand</span></span>

<span data-ttu-id="7846e-299">Повторите Последнее изменение текста.</span><span class="sxs-lookup"><span data-stu-id="7846e-299">Repeat the last text modification.</span></span>

- <span data-ttu-id="7846e-300">Режим команд VI: `<.>`</span><span class="sxs-lookup"><span data-stu-id="7846e-300">Vi command mode: `<.>`</span></span>

### <a name="revertline"></a><span data-ttu-id="7846e-301">ревертлине</span><span class="sxs-lookup"><span data-stu-id="7846e-301">RevertLine</span></span>

<span data-ttu-id="7846e-302">Меняет все входные данные на текущие входные данные.</span><span class="sxs-lookup"><span data-stu-id="7846e-302">Reverts all of the input to the current input.</span></span>

- <span data-ttu-id="7846e-303">Процессор `<Escape>`</span><span class="sxs-lookup"><span data-stu-id="7846e-303">Cmd: `<Escape>`</span></span>
- <span data-ttu-id="7846e-304">Emacs: `<Alt+r>` , `<Escape,r>`</span><span class="sxs-lookup"><span data-stu-id="7846e-304">Emacs: `<Alt+r>`, `<Escape,r>`</span></span>

### <a name="shellbackwardkillword"></a><span data-ttu-id="7846e-305">шеллбакквардкиллворд</span><span class="sxs-lookup"><span data-stu-id="7846e-305">ShellBackwardKillWord</span></span>

<span data-ttu-id="7846e-306">Очистить ввод от начала текущего слова до курсора.</span><span class="sxs-lookup"><span data-stu-id="7846e-306">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="7846e-307">Если курсор находится между словами, входные данные очищаются от начала предыдущего слова до курсора.</span><span class="sxs-lookup"><span data-stu-id="7846e-307">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="7846e-308">Очистка текста помещается в буфер Kill.</span><span class="sxs-lookup"><span data-stu-id="7846e-308">The cleared text is placed in the kill-ring.</span></span>

<span data-ttu-id="7846e-309">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="7846e-309">Function is unbound.</span></span>

### <a name="shellkillword"></a><span data-ttu-id="7846e-310">шеллкиллворд</span><span class="sxs-lookup"><span data-stu-id="7846e-310">ShellKillWord</span></span>

<span data-ttu-id="7846e-311">Очистить ввод от курсора до конца текущего слова.</span><span class="sxs-lookup"><span data-stu-id="7846e-311">Clear the input from the cursor to the end of the current word.</span></span> <span data-ttu-id="7846e-312">Если курсор находится между словами, входные данные очищаются от курсора до конца следующего слова.</span><span class="sxs-lookup"><span data-stu-id="7846e-312">If the cursor is between words, the input is cleared from the cursor to the end of the next word.</span></span> <span data-ttu-id="7846e-313">Очистка текста помещается в буфер Kill.</span><span class="sxs-lookup"><span data-stu-id="7846e-313">The cleared text is placed in the kill-ring.</span></span>

<span data-ttu-id="7846e-314">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="7846e-314">Function is unbound.</span></span>

### <a name="swapcharacters"></a><span data-ttu-id="7846e-315">свапчарактерс</span><span class="sxs-lookup"><span data-stu-id="7846e-315">SwapCharacters</span></span>

<span data-ttu-id="7846e-316">Поменять местами текущий и тот же символ.</span><span class="sxs-lookup"><span data-stu-id="7846e-316">Swap the current character and the one before it.</span></span>

- <span data-ttu-id="7846e-317">Emacs: `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="7846e-317">Emacs: `<Ctrl+t>`</span></span>
- <span data-ttu-id="7846e-318">Режим вставки в VI: `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="7846e-318">Vi insert mode: `<Ctrl+t>`</span></span>
- <span data-ttu-id="7846e-319">Режим команд VI: `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="7846e-319">Vi command mode: `<Ctrl+t>`</span></span>

### <a name="undo"></a><span data-ttu-id="7846e-320">Отменить</span><span class="sxs-lookup"><span data-stu-id="7846e-320">Undo</span></span>

<span data-ttu-id="7846e-321">Отмена предыдущего изменения.</span><span class="sxs-lookup"><span data-stu-id="7846e-321">Undo a previous edit.</span></span>

- <span data-ttu-id="7846e-322">Процессор `<Ctrl+z>`</span><span class="sxs-lookup"><span data-stu-id="7846e-322">Cmd: `<Ctrl+z>`</span></span>
- <span data-ttu-id="7846e-323">Emacs: `<Ctrl+_>` , `<Ctrl+x,Ctrl+u>`</span><span class="sxs-lookup"><span data-stu-id="7846e-323">Emacs: `<Ctrl+_>`, `<Ctrl+x,Ctrl+u>`</span></span>
- <span data-ttu-id="7846e-324">Режим вставки в VI: `<Ctrl+z>`</span><span class="sxs-lookup"><span data-stu-id="7846e-324">Vi insert mode: `<Ctrl+z>`</span></span>
- <span data-ttu-id="7846e-325">Режим команд VI: `<Ctrl+z>` , `<u>`</span><span class="sxs-lookup"><span data-stu-id="7846e-325">Vi command mode: `<Ctrl+z>`, `<u>`</span></span>

### <a name="undoall"></a><span data-ttu-id="7846e-326">ундоалл</span><span class="sxs-lookup"><span data-stu-id="7846e-326">UndoAll</span></span>

<span data-ttu-id="7846e-327">Отмена всех предыдущих изменений для строки.</span><span class="sxs-lookup"><span data-stu-id="7846e-327">Undo all previous edits for line.</span></span>

- <span data-ttu-id="7846e-328">Режим команд VI: `<U>`</span><span class="sxs-lookup"><span data-stu-id="7846e-328">Vi command mode: `<U>`</span></span>

### <a name="unixwordrubout"></a><span data-ttu-id="7846e-329">униксвордрубаут</span><span class="sxs-lookup"><span data-stu-id="7846e-329">UnixWordRubout</span></span>

<span data-ttu-id="7846e-330">Очистить ввод от начала текущего слова до курсора.</span><span class="sxs-lookup"><span data-stu-id="7846e-330">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="7846e-331">Если курсор находится между словами, входные данные очищаются от начала предыдущего слова до курсора.</span><span class="sxs-lookup"><span data-stu-id="7846e-331">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="7846e-332">Очистка текста помещается в буфер Kill.</span><span class="sxs-lookup"><span data-stu-id="7846e-332">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="7846e-333">Emacs: `<Ctrl+w>`</span><span class="sxs-lookup"><span data-stu-id="7846e-333">Emacs: `<Ctrl+w>`</span></span>

### <a name="validateandacceptline"></a><span data-ttu-id="7846e-334">валидатеандакцептлине</span><span class="sxs-lookup"><span data-stu-id="7846e-334">ValidateAndAcceptLine</span></span>

<span data-ttu-id="7846e-335">Попытка выполнить текущий вход.</span><span class="sxs-lookup"><span data-stu-id="7846e-335">Attempt to execute the current input.</span></span> <span data-ttu-id="7846e-336">Если текущий ввод неполон (например, отсутствует закрывающая круглая скобка, квадратная скобка или кавычка, запрос продолжения отображается на следующей строке, а PSReadLine ожидает ввода ключей для изменения текущих входных данных.</span><span class="sxs-lookup"><span data-stu-id="7846e-336">If the current input is incomplete (for example there is a missing closing parenthesis, bracket, or quote, then the continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span>

- <span data-ttu-id="7846e-337">Emacs: `<Ctrl+m>`</span><span class="sxs-lookup"><span data-stu-id="7846e-337">Emacs: `<Ctrl+m>`</span></span>

### <a name="viacceptline"></a><span data-ttu-id="7846e-338">виакцептлине</span><span class="sxs-lookup"><span data-stu-id="7846e-338">ViAcceptLine</span></span>

<span data-ttu-id="7846e-339">Примите строку и переключитесь в режим вставки.</span><span class="sxs-lookup"><span data-stu-id="7846e-339">Accept the line and switch to Insert mode.</span></span>

- <span data-ttu-id="7846e-340">Режим команд VI: `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="7846e-340">Vi command mode: `<Enter>`</span></span>

### <a name="viacceptlineorexit"></a><span data-ttu-id="7846e-341">виакцептлинеорексит</span><span class="sxs-lookup"><span data-stu-id="7846e-341">ViAcceptLineOrExit</span></span>

<span data-ttu-id="7846e-342">Как и Делетечарорексит в режиме Emacs, но принимает строку вместо удаления символа.</span><span class="sxs-lookup"><span data-stu-id="7846e-342">Like DeleteCharOrExit in Emacs mode, but accepts the line instead of deleting a character.</span></span>

- <span data-ttu-id="7846e-343">Режим вставки в VI: `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="7846e-343">Vi insert mode: `<Ctrl+d>`</span></span>
- <span data-ttu-id="7846e-344">Режим команд VI: `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="7846e-344">Vi command mode: `<Ctrl+d>`</span></span>

### <a name="viappendline"></a><span data-ttu-id="7846e-345">виаппендлине</span><span class="sxs-lookup"><span data-stu-id="7846e-345">ViAppendLine</span></span>

<span data-ttu-id="7846e-346">Новая строка вставляется под текущей строкой.</span><span class="sxs-lookup"><span data-stu-id="7846e-346">A new line is inserted below the current line.</span></span>

- <span data-ttu-id="7846e-347">Режим команд VI: `<o>`</span><span class="sxs-lookup"><span data-stu-id="7846e-347">Vi command mode: `<o>`</span></span>

### <a name="vibackwarddeleteglob"></a><span data-ttu-id="7846e-348">вибакквардделетеглоб</span><span class="sxs-lookup"><span data-stu-id="7846e-348">ViBackwardDeleteGlob</span></span>

<span data-ttu-id="7846e-349">Удаляет предыдущее слово, используя только пробелы в качестве разделителя слов.</span><span class="sxs-lookup"><span data-stu-id="7846e-349">Deletes the previous word, using only white space as the word delimiter.</span></span>

- <span data-ttu-id="7846e-350">Режим команд VI: `<d,B>`</span><span class="sxs-lookup"><span data-stu-id="7846e-350">Vi command mode: `<d,B>`</span></span>

### <a name="vibackwardglob"></a><span data-ttu-id="7846e-351">вибакквардглоб</span><span class="sxs-lookup"><span data-stu-id="7846e-351">ViBackwardGlob</span></span>

<span data-ttu-id="7846e-352">Перемещает курсор назад к началу предыдущего слова, используя только пробелы в качестве разделителей.</span><span class="sxs-lookup"><span data-stu-id="7846e-352">Moves the cursor back to the beginning of the previous word, using only white space as delimiters.</span></span>

- <span data-ttu-id="7846e-353">Режим команд VI: `<B>`</span><span class="sxs-lookup"><span data-stu-id="7846e-353">Vi command mode: `<B>`</span></span>

### <a name="videletebrace"></a><span data-ttu-id="7846e-354">виделетебраце</span><span class="sxs-lookup"><span data-stu-id="7846e-354">ViDeleteBrace</span></span>

<span data-ttu-id="7846e-355">Найдите парную фигурную скобку, круглую скобку или квадратную скобку и удалите все содержимое внутри, включая фигурную скобку.</span><span class="sxs-lookup"><span data-stu-id="7846e-355">Find the matching brace, parenthesis, or square bracket and delete all contents within, including the brace.</span></span>

- <span data-ttu-id="7846e-356">Режим команд VI: `<d,%>`</span><span class="sxs-lookup"><span data-stu-id="7846e-356">Vi command mode: `<d,%>`</span></span>

### <a name="videleteendofglob"></a><span data-ttu-id="7846e-357">виделетиндофглоб</span><span class="sxs-lookup"><span data-stu-id="7846e-357">ViDeleteEndOfGlob</span></span>

<span data-ttu-id="7846e-358">Удалить до конца слова.</span><span class="sxs-lookup"><span data-stu-id="7846e-358">Delete to the end of the word.</span></span>

- <span data-ttu-id="7846e-359">Режим команд VI: `<d,E>`</span><span class="sxs-lookup"><span data-stu-id="7846e-359">Vi command mode: `<d,E>`</span></span>

### <a name="videleteglob"></a><span data-ttu-id="7846e-360">виделетеглоб</span><span class="sxs-lookup"><span data-stu-id="7846e-360">ViDeleteGlob</span></span>

<span data-ttu-id="7846e-361">Удалите следующий стандартная маска (слово, разделенное пробелами).</span><span class="sxs-lookup"><span data-stu-id="7846e-361">Delete the next glob (white space delimited word).</span></span>

- <span data-ttu-id="7846e-362">Режим команд VI: `<d,W>`</span><span class="sxs-lookup"><span data-stu-id="7846e-362">Vi command mode: `<d,W>`</span></span>

### <a name="videletetobeforechar"></a><span data-ttu-id="7846e-363">виделететобефоречар</span><span class="sxs-lookup"><span data-stu-id="7846e-363">ViDeleteToBeforeChar</span></span>

<span data-ttu-id="7846e-364">Удаляет до заданного символа.</span><span class="sxs-lookup"><span data-stu-id="7846e-364">Deletes until given character.</span></span>

- <span data-ttu-id="7846e-365">Режим команд VI: `<d,t>`</span><span class="sxs-lookup"><span data-stu-id="7846e-365">Vi command mode: `<d,t>`</span></span>

### <a name="videletetobeforecharbackward"></a><span data-ttu-id="7846e-366">виделететобефоречарбакквард</span><span class="sxs-lookup"><span data-stu-id="7846e-366">ViDeleteToBeforeCharBackward</span></span>

<span data-ttu-id="7846e-367">Удаляет до заданного символа.</span><span class="sxs-lookup"><span data-stu-id="7846e-367">Deletes until given character.</span></span>

- <span data-ttu-id="7846e-368">Режим команд VI: `<d,T>`</span><span class="sxs-lookup"><span data-stu-id="7846e-368">Vi command mode: `<d,T>`</span></span>

### <a name="videletetochar"></a><span data-ttu-id="7846e-369">виделететочар</span><span class="sxs-lookup"><span data-stu-id="7846e-369">ViDeleteToChar</span></span>

<span data-ttu-id="7846e-370">Удаляет до заданного символа.</span><span class="sxs-lookup"><span data-stu-id="7846e-370">Deletes until given character.</span></span>

- <span data-ttu-id="7846e-371">Режим команд VI: `<d,f>`</span><span class="sxs-lookup"><span data-stu-id="7846e-371">Vi command mode: `<d,f>`</span></span>

### <a name="videletetocharbackward"></a><span data-ttu-id="7846e-372">виделететочарбакквард</span><span class="sxs-lookup"><span data-stu-id="7846e-372">ViDeleteToCharBackward</span></span>

<span data-ttu-id="7846e-373">Удаляет обратную сторону до заданного символа.</span><span class="sxs-lookup"><span data-stu-id="7846e-373">Deletes backwards until given character.</span></span>

- <span data-ttu-id="7846e-374">Режим команд VI: `<d,F>`</span><span class="sxs-lookup"><span data-stu-id="7846e-374">Vi command mode: `<d,F>`</span></span>

### <a name="viinsertatbegining"></a><span data-ttu-id="7846e-375">виинсертатбегининг</span><span class="sxs-lookup"><span data-stu-id="7846e-375">ViInsertAtBegining</span></span>

<span data-ttu-id="7846e-376">Переключитесь в режим вставки и поместите курсор в начало строки.</span><span class="sxs-lookup"><span data-stu-id="7846e-376">Switch to Insert mode and position the cursor at the beginning of the line.</span></span>

- <span data-ttu-id="7846e-377">Режим команд VI: `<I>`</span><span class="sxs-lookup"><span data-stu-id="7846e-377">Vi command mode: `<I>`</span></span>

### <a name="viinsertatend"></a><span data-ttu-id="7846e-378">виинсертатенд</span><span class="sxs-lookup"><span data-stu-id="7846e-378">ViInsertAtEnd</span></span>

<span data-ttu-id="7846e-379">Переключитесь в режим вставки и поместите курсор в конец строки.</span><span class="sxs-lookup"><span data-stu-id="7846e-379">Switch to Insert mode and position the cursor at the end of the line.</span></span>

- <span data-ttu-id="7846e-380">Режим команд VI: `<A>`</span><span class="sxs-lookup"><span data-stu-id="7846e-380">Vi command mode: `<A>`</span></span>

### <a name="viinsertline"></a><span data-ttu-id="7846e-381">виинсертлине</span><span class="sxs-lookup"><span data-stu-id="7846e-381">ViInsertLine</span></span>

<span data-ttu-id="7846e-382">Новая строка вставляется над текущей строкой.</span><span class="sxs-lookup"><span data-stu-id="7846e-382">A new line is inserted above the current line.</span></span>

- <span data-ttu-id="7846e-383">Режим команд VI: `<O>`</span><span class="sxs-lookup"><span data-stu-id="7846e-383">Vi command mode: `<O>`</span></span>

### <a name="viinsertwithappend"></a><span data-ttu-id="7846e-384">виинсертвисаппенд</span><span class="sxs-lookup"><span data-stu-id="7846e-384">ViInsertWithAppend</span></span>

<span data-ttu-id="7846e-385">Добавление из текущей позицией строки.</span><span class="sxs-lookup"><span data-stu-id="7846e-385">Append from the current line position.</span></span>

- <span data-ttu-id="7846e-386">Режим команд VI: `<a>`</span><span class="sxs-lookup"><span data-stu-id="7846e-386">Vi command mode: `<a>`</span></span>

### <a name="viinsertwithdelete"></a><span data-ttu-id="7846e-387">виинсертвисделете</span><span class="sxs-lookup"><span data-stu-id="7846e-387">ViInsertWithDelete</span></span>

<span data-ttu-id="7846e-388">Удалите текущий символ и переключитесь в режим вставки.</span><span class="sxs-lookup"><span data-stu-id="7846e-388">Delete the current character and switch to Insert mode.</span></span>

- <span data-ttu-id="7846e-389">Режим команд VI: `<s>`</span><span class="sxs-lookup"><span data-stu-id="7846e-389">Vi command mode: `<s>`</span></span>

### <a name="vijoinlines"></a><span data-ttu-id="7846e-390">вижоинлинес</span><span class="sxs-lookup"><span data-stu-id="7846e-390">ViJoinLines</span></span>

<span data-ttu-id="7846e-391">Объединяет текущую строку и следующую строку.</span><span class="sxs-lookup"><span data-stu-id="7846e-391">Joins the current line and the next line.</span></span>

- <span data-ttu-id="7846e-392">Режим команд VI: `<J>`</span><span class="sxs-lookup"><span data-stu-id="7846e-392">Vi command mode: `<J>`</span></span>

### <a name="vireplaceline"></a><span data-ttu-id="7846e-393">виреплацелине</span><span class="sxs-lookup"><span data-stu-id="7846e-393">ViReplaceLine</span></span>

<span data-ttu-id="7846e-394">Очистить всю командную строку.</span><span class="sxs-lookup"><span data-stu-id="7846e-394">Erase the entire command line.</span></span>

- <span data-ttu-id="7846e-395">Режим команд VI: `<S>` , `<c,c>`</span><span class="sxs-lookup"><span data-stu-id="7846e-395">Vi command mode: `<S>`, `<c,c>`</span></span>

### <a name="vireplacetobeforechar"></a><span data-ttu-id="7846e-396">виреплацетобефоречар</span><span class="sxs-lookup"><span data-stu-id="7846e-396">ViReplaceToBeforeChar</span></span>

<span data-ttu-id="7846e-397">Заменяет заданный символ.</span><span class="sxs-lookup"><span data-stu-id="7846e-397">Replaces until given character.</span></span>

- <span data-ttu-id="7846e-398">Режим команд VI: `<c,t>`</span><span class="sxs-lookup"><span data-stu-id="7846e-398">Vi command mode: `<c,t>`</span></span>

### <a name="vireplacetobeforecharbackward"></a><span data-ttu-id="7846e-399">виреплацетобефоречарбакквард</span><span class="sxs-lookup"><span data-stu-id="7846e-399">ViReplaceToBeforeCharBackward</span></span>

<span data-ttu-id="7846e-400">Заменяет заданный символ.</span><span class="sxs-lookup"><span data-stu-id="7846e-400">Replaces until given character.</span></span>

- <span data-ttu-id="7846e-401">Режим команд VI: `<c,T>`</span><span class="sxs-lookup"><span data-stu-id="7846e-401">Vi command mode: `<c,T>`</span></span>

### <a name="vireplacetochar"></a><span data-ttu-id="7846e-402">виреплацеточар</span><span class="sxs-lookup"><span data-stu-id="7846e-402">ViReplaceToChar</span></span>

<span data-ttu-id="7846e-403">Удаляет до заданного символа.</span><span class="sxs-lookup"><span data-stu-id="7846e-403">Deletes until given character.</span></span>

- <span data-ttu-id="7846e-404">Режим команд VI: `<c,f>`</span><span class="sxs-lookup"><span data-stu-id="7846e-404">Vi command mode: `<c,f>`</span></span>

### <a name="vireplacetocharbackward"></a><span data-ttu-id="7846e-405">виреплацеточарбакквард</span><span class="sxs-lookup"><span data-stu-id="7846e-405">ViReplaceToCharBackward</span></span>

<span data-ttu-id="7846e-406">Заменяет заданный символ.</span><span class="sxs-lookup"><span data-stu-id="7846e-406">Replaces until given character.</span></span>

- <span data-ttu-id="7846e-407">Режим команд VI: `<c,F>`</span><span class="sxs-lookup"><span data-stu-id="7846e-407">Vi command mode: `<c,F>`</span></span>

### <a name="viyankbeginningofline"></a><span data-ttu-id="7846e-408">вийанкбегиннингофлине</span><span class="sxs-lookup"><span data-stu-id="7846e-408">ViYankBeginningOfLine</span></span>

<span data-ttu-id="7846e-409">Янк от начала буфера до курсора.</span><span class="sxs-lookup"><span data-stu-id="7846e-409">Yank from the beginning of the buffer to the cursor.</span></span>

- <span data-ttu-id="7846e-410">Режим команд VI: `<y,0>`</span><span class="sxs-lookup"><span data-stu-id="7846e-410">Vi command mode: `<y,0>`</span></span>

### <a name="viyankendofglob"></a><span data-ttu-id="7846e-411">вийанкендофглоб</span><span class="sxs-lookup"><span data-stu-id="7846e-411">ViYankEndOfGlob</span></span>

<span data-ttu-id="7846e-412">Янк от курсора до конца слова.</span><span class="sxs-lookup"><span data-stu-id="7846e-412">Yank from the cursor to the end of the WORD(s).</span></span>

- <span data-ttu-id="7846e-413">Режим команд VI: `<y,E>`</span><span class="sxs-lookup"><span data-stu-id="7846e-413">Vi command mode: `<y,E>`</span></span>

### <a name="viyankendofword"></a><span data-ttu-id="7846e-414">вийанкендофворд</span><span class="sxs-lookup"><span data-stu-id="7846e-414">ViYankEndOfWord</span></span>

<span data-ttu-id="7846e-415">Янк от курсора до конца слова.</span><span class="sxs-lookup"><span data-stu-id="7846e-415">Yank from the cursor to the end of the word(s).</span></span>

- <span data-ttu-id="7846e-416">Режим команд VI: `<y,e>`</span><span class="sxs-lookup"><span data-stu-id="7846e-416">Vi command mode: `<y,e>`</span></span>

### <a name="viyankleft"></a><span data-ttu-id="7846e-417">вийанклефт</span><span class="sxs-lookup"><span data-stu-id="7846e-417">ViYankLeft</span></span>

<span data-ttu-id="7846e-418">Янк символы слева от курсора.</span><span class="sxs-lookup"><span data-stu-id="7846e-418">Yank character(s) to the left of the cursor.</span></span>

- <span data-ttu-id="7846e-419">Режим команд VI: `<y,h>`</span><span class="sxs-lookup"><span data-stu-id="7846e-419">Vi command mode: `<y,h>`</span></span>

### <a name="viyankline"></a><span data-ttu-id="7846e-420">вийанклине</span><span class="sxs-lookup"><span data-stu-id="7846e-420">ViYankLine</span></span>

<span data-ttu-id="7846e-421">Янк весь буфер.</span><span class="sxs-lookup"><span data-stu-id="7846e-421">Yank the entire buffer.</span></span>

- <span data-ttu-id="7846e-422">Режим команд VI: `<y,y>`</span><span class="sxs-lookup"><span data-stu-id="7846e-422">Vi command mode: `<y,y>`</span></span>

### <a name="viyanknextglob"></a><span data-ttu-id="7846e-423">вийанкнекстглоб</span><span class="sxs-lookup"><span data-stu-id="7846e-423">ViYankNextGlob</span></span>

<span data-ttu-id="7846e-424">Янк от курсора до начала следующего слова.</span><span class="sxs-lookup"><span data-stu-id="7846e-424">Yank from cursor to the start of the next WORD(s).</span></span>

- <span data-ttu-id="7846e-425">Режим команд VI: `<y,W>`</span><span class="sxs-lookup"><span data-stu-id="7846e-425">Vi command mode: `<y,W>`</span></span>

### <a name="viyanknextword"></a><span data-ttu-id="7846e-426">вийанкнекстворд</span><span class="sxs-lookup"><span data-stu-id="7846e-426">ViYankNextWord</span></span>

<span data-ttu-id="7846e-427">Янк слова после курсора.</span><span class="sxs-lookup"><span data-stu-id="7846e-427">Yank the word(s) after the cursor.</span></span>

- <span data-ttu-id="7846e-428">Режим команд VI: `<y,w>`</span><span class="sxs-lookup"><span data-stu-id="7846e-428">Vi command mode: `<y,w>`</span></span>

### <a name="viyankpercent"></a><span data-ttu-id="7846e-429">вийанкперцент</span><span class="sxs-lookup"><span data-stu-id="7846e-429">ViYankPercent</span></span>

<span data-ttu-id="7846e-430">Янк в парную фигурную скобку.</span><span class="sxs-lookup"><span data-stu-id="7846e-430">Yank to/from matching brace.</span></span>

- <span data-ttu-id="7846e-431">Режим команд VI: `<y,%>`</span><span class="sxs-lookup"><span data-stu-id="7846e-431">Vi command mode: `<y,%>`</span></span>

### <a name="viyankpreviousglob"></a><span data-ttu-id="7846e-432">вийанкпревиаусглоб</span><span class="sxs-lookup"><span data-stu-id="7846e-432">ViYankPreviousGlob</span></span>

<span data-ttu-id="7846e-433">Янк от начала слов до курсора.</span><span class="sxs-lookup"><span data-stu-id="7846e-433">Yank from beginning of the WORD(s) to cursor.</span></span>

- <span data-ttu-id="7846e-434">Режим команд VI: `<y,B>`</span><span class="sxs-lookup"><span data-stu-id="7846e-434">Vi command mode: `<y,B>`</span></span>

### <a name="viyankpreviousword"></a><span data-ttu-id="7846e-435">вийанкпревиаусворд</span><span class="sxs-lookup"><span data-stu-id="7846e-435">ViYankPreviousWord</span></span>

<span data-ttu-id="7846e-436">Янк слова перед курсором.</span><span class="sxs-lookup"><span data-stu-id="7846e-436">Yank the word(s) before the cursor.</span></span>

- <span data-ttu-id="7846e-437">Режим команд VI: `<y,b>`</span><span class="sxs-lookup"><span data-stu-id="7846e-437">Vi command mode: `<y,b>`</span></span>

### <a name="viyankright"></a><span data-ttu-id="7846e-438">вийанкригхт</span><span class="sxs-lookup"><span data-stu-id="7846e-438">ViYankRight</span></span>

<span data-ttu-id="7846e-439">Янк символы в положении и справа от курсора.</span><span class="sxs-lookup"><span data-stu-id="7846e-439">Yank character(s) under and to the right of the cursor.</span></span>

- <span data-ttu-id="7846e-440">Режим команд VI: `<y,l>` , `<y,Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="7846e-440">Vi command mode: `<y,l>`, `<y,Spacebar>`</span></span>

### <a name="viyanktoendofline"></a><span data-ttu-id="7846e-441">вийанктоендофлине</span><span class="sxs-lookup"><span data-stu-id="7846e-441">ViYankToEndOfLine</span></span>

<span data-ttu-id="7846e-442">Янк от курсора до конца буфера.</span><span class="sxs-lookup"><span data-stu-id="7846e-442">Yank from the cursor to the end of the buffer.</span></span>

- <span data-ttu-id="7846e-443">Режим команд VI: `<y,$>`</span><span class="sxs-lookup"><span data-stu-id="7846e-443">Vi command mode: `<y,$>`</span></span>

### <a name="viyanktofirstchar"></a><span data-ttu-id="7846e-444">вийанктофирстчар</span><span class="sxs-lookup"><span data-stu-id="7846e-444">ViYankToFirstChar</span></span>

<span data-ttu-id="7846e-445">Янк от первого символа, отличного от пробела, к курсору.</span><span class="sxs-lookup"><span data-stu-id="7846e-445">Yank from the first non-whitespace character to the cursor.</span></span>

- <span data-ttu-id="7846e-446">Режим команд VI: `<y,^>`</span><span class="sxs-lookup"><span data-stu-id="7846e-446">Vi command mode: `<y,^>`</span></span>

### <a name="yank"></a><span data-ttu-id="7846e-447">янк</span><span class="sxs-lookup"><span data-stu-id="7846e-447">Yank</span></span>

<span data-ttu-id="7846e-448">Добавление последнего недавнего текста во входные данные.</span><span class="sxs-lookup"><span data-stu-id="7846e-448">Add the most recently killed text to the input.</span></span>

- <span data-ttu-id="7846e-449">Emacs: `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="7846e-449">Emacs: `<Ctrl+y>`</span></span>

### <a name="yanklastarg"></a><span data-ttu-id="7846e-450">янкластарг</span><span class="sxs-lookup"><span data-stu-id="7846e-450">YankLastArg</span></span>

<span data-ttu-id="7846e-451">Янк последний аргумент из предыдущей строки журнала.</span><span class="sxs-lookup"><span data-stu-id="7846e-451">Yank the last argument from the previous history line.</span></span> <span data-ttu-id="7846e-452">С аргументом при первом вызове он ведет себя так же, как Янкнсарг.</span><span class="sxs-lookup"><span data-stu-id="7846e-452">With an argument, the first time it is invoked, behaves just like YankNthArg.</span></span> <span data-ttu-id="7846e-453">Если вызывается несколько раз, вместо этого выполняется итерация по журналу, а аргумент устанавливает направление (отрицательно меняет направление на противоположное).</span><span class="sxs-lookup"><span data-stu-id="7846e-453">If invoked multiple times, instead it iterates through history and arg sets the direction (negative reverses the direction.)</span></span>

- <span data-ttu-id="7846e-454">Процессор `<Alt+.>`</span><span class="sxs-lookup"><span data-stu-id="7846e-454">Cmd: `<Alt+.>`</span></span>
- <span data-ttu-id="7846e-455">Emacs: `<Alt+.>` , `<Alt+_>` , `<Escape,.>` , `<Escape,_>`</span><span class="sxs-lookup"><span data-stu-id="7846e-455">Emacs: `<Alt+.>`, `<Alt+_>`, `<Escape,.>`, `<Escape,_>`</span></span>

### <a name="yankntharg"></a><span data-ttu-id="7846e-456">янкнсарг</span><span class="sxs-lookup"><span data-stu-id="7846e-456">YankNthArg</span></span>

<span data-ttu-id="7846e-457">Янк первый аргумент (после команды) из предыдущей строки журнала.</span><span class="sxs-lookup"><span data-stu-id="7846e-457">Yank the first argument (after the command) from the previous history line.</span></span>
<span data-ttu-id="7846e-458">При использовании аргумента Янк аргумент n (начиная с 0), если аргумент является отрицательным, начните с последнего аргумента.</span><span class="sxs-lookup"><span data-stu-id="7846e-458">With an argument, yank the nth argument (starting from 0), if the argument is negative, start from the last argument.</span></span>

- <span data-ttu-id="7846e-459">Emacs: `<Ctrl+Alt+y>` , `<Escape,Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="7846e-459">Emacs: `<Ctrl+Alt+y>`, `<Escape,Ctrl+y>`</span></span>

### <a name="yankpop"></a><span data-ttu-id="7846e-460">янкпоп</span><span class="sxs-lookup"><span data-stu-id="7846e-460">YankPop</span></span>

<span data-ttu-id="7846e-461">Если предыдущая операция была Янк или Янкпоп, замените ранее янкед текст следующим уничтоженным текстом из Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="7846e-461">If the previous operation was Yank or YankPop, replace the previously yanked text with the next killed text from the kill-ring.</span></span>

- <span data-ttu-id="7846e-462">Emacs: `<Alt+y>` , `<Escape,y>`</span><span class="sxs-lookup"><span data-stu-id="7846e-462">Emacs: `<Alt+y>`, `<Escape,y>`</span></span>

## <a name="cursor-movement-functions"></a><span data-ttu-id="7846e-463">Функции перемещения курсора</span><span class="sxs-lookup"><span data-stu-id="7846e-463">Cursor movement functions</span></span>

### <a name="backwardchar"></a><span data-ttu-id="7846e-464">бакквардчар</span><span class="sxs-lookup"><span data-stu-id="7846e-464">BackwardChar</span></span>

<span data-ttu-id="7846e-465">Переместить курсор на один символ влево.</span><span class="sxs-lookup"><span data-stu-id="7846e-465">Move the cursor one character to the left.</span></span> <span data-ttu-id="7846e-466">Это может переместить курсор к предыдущей строке многострочного ввода.</span><span class="sxs-lookup"><span data-stu-id="7846e-466">This may move the cursor to the previous line of multi-line input.</span></span>

- <span data-ttu-id="7846e-467">Процессор `<LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="7846e-467">Cmd: `<LeftArrow>`</span></span>
- <span data-ttu-id="7846e-468">Emacs: `<LeftArrow>` , `<Ctrl+b>`</span><span class="sxs-lookup"><span data-stu-id="7846e-468">Emacs: `<LeftArrow>`, `<Ctrl+b>`</span></span>

### <a name="backwardword"></a><span data-ttu-id="7846e-469">бакквардворд</span><span class="sxs-lookup"><span data-stu-id="7846e-469">BackwardWord</span></span>

<span data-ttu-id="7846e-470">Перемещение курсора назад к началу текущего слова или между словами, с начала предыдущего слова.</span><span class="sxs-lookup"><span data-stu-id="7846e-470">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="7846e-471">Границы слов определяются с помощью настраиваемого набора символов.</span><span class="sxs-lookup"><span data-stu-id="7846e-471">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="7846e-472">Процессор `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="7846e-472">Cmd: `<Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="7846e-473">Emacs: `<Alt+b>` , `<Escape,b>`</span><span class="sxs-lookup"><span data-stu-id="7846e-473">Emacs: `<Alt+b>`, `<Escape,b>`</span></span>
- <span data-ttu-id="7846e-474">Режим вставки в VI: `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="7846e-474">Vi insert mode: `<Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="7846e-475">Режим команд VI: `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="7846e-475">Vi command mode: `<Ctrl+LeftArrow>`</span></span>

### <a name="beginningofline"></a><span data-ttu-id="7846e-476">бегиннингофлине</span><span class="sxs-lookup"><span data-stu-id="7846e-476">BeginningOfLine</span></span>

<span data-ttu-id="7846e-477">Если входные данные имеют несколько строк, переместитесь в начало текущей строки или, если они уже находятся в начале строки, перейдите к началу входного элемента.</span><span class="sxs-lookup"><span data-stu-id="7846e-477">If the input has multiple lines, move to the start of the current line, or if already at the start of the line, move to the start of the input.</span></span> <span data-ttu-id="7846e-478">Если входные данные имеют одну строку, переходите к началу входных данных.</span><span class="sxs-lookup"><span data-stu-id="7846e-478">If the input has a single line, move to the start of the input.</span></span>

- <span data-ttu-id="7846e-479">Процессор `<Home>`</span><span class="sxs-lookup"><span data-stu-id="7846e-479">Cmd: `<Home>`</span></span>
- <span data-ttu-id="7846e-480">Emacs: `<Home>` , `<Ctrl+a>`</span><span class="sxs-lookup"><span data-stu-id="7846e-480">Emacs: `<Home>`, `<Ctrl+a>`</span></span>
- <span data-ttu-id="7846e-481">Режим вставки в VI: `<Home>`</span><span class="sxs-lookup"><span data-stu-id="7846e-481">Vi insert mode: `<Home>`</span></span>
- <span data-ttu-id="7846e-482">Режим команд VI: `<Home>`</span><span class="sxs-lookup"><span data-stu-id="7846e-482">Vi command mode: `<Home>`</span></span>

### <a name="endofline"></a><span data-ttu-id="7846e-483">ендофлине</span><span class="sxs-lookup"><span data-stu-id="7846e-483">EndOfLine</span></span>

<span data-ttu-id="7846e-484">Если входные данные имеют несколько строк, переместитесь в конец текущей строки или, если они уже находятся в конце строки, перейдите к концу входных данных.</span><span class="sxs-lookup"><span data-stu-id="7846e-484">If the input has multiple lines, move to the end of the current line, or if already at the end of the line, move to the end of the input.</span></span> <span data-ttu-id="7846e-485">Если входные данные имеют одну строку, переходите к концу входных данных.</span><span class="sxs-lookup"><span data-stu-id="7846e-485">If the input has a single line, move to the end of the input.</span></span>

- <span data-ttu-id="7846e-486">Процессор `<End>`</span><span class="sxs-lookup"><span data-stu-id="7846e-486">Cmd: `<End>`</span></span>
- <span data-ttu-id="7846e-487">Emacs: `<End>` , `<Ctrl+e>`</span><span class="sxs-lookup"><span data-stu-id="7846e-487">Emacs: `<End>`, `<Ctrl+e>`</span></span>
- <span data-ttu-id="7846e-488">Режим вставки в VI: `<End>`</span><span class="sxs-lookup"><span data-stu-id="7846e-488">Vi insert mode: `<End>`</span></span>

### <a name="forwardchar"></a><span data-ttu-id="7846e-489">форвардчар</span><span class="sxs-lookup"><span data-stu-id="7846e-489">ForwardChar</span></span>

<span data-ttu-id="7846e-490">Переместить курсор на один символ вправо.</span><span class="sxs-lookup"><span data-stu-id="7846e-490">Move the cursor one character to the right.</span></span> <span data-ttu-id="7846e-491">Это может переместить курсор на следующую строку многострочного ввода.</span><span class="sxs-lookup"><span data-stu-id="7846e-491">This may move the cursor to the next line of multi-line input.</span></span>

- <span data-ttu-id="7846e-492">Процессор `<RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="7846e-492">Cmd: `<RightArrow>`</span></span>
- <span data-ttu-id="7846e-493">Emacs: `<RightArrow>` , `<Ctrl+f>`</span><span class="sxs-lookup"><span data-stu-id="7846e-493">Emacs: `<RightArrow>`, `<Ctrl+f>`</span></span>

### <a name="forwardword"></a><span data-ttu-id="7846e-494">форвардворд</span><span class="sxs-lookup"><span data-stu-id="7846e-494">ForwardWord</span></span>

<span data-ttu-id="7846e-495">Переместить курсор вперед к концу текущего слова или между словами, до конца следующего слова.</span><span class="sxs-lookup"><span data-stu-id="7846e-495">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="7846e-496">Границы слов определяются с помощью настраиваемого набора символов.</span><span class="sxs-lookup"><span data-stu-id="7846e-496">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="7846e-497">Emacs: `<Alt+f>` , `<Escape,f>`</span><span class="sxs-lookup"><span data-stu-id="7846e-497">Emacs: `<Alt+f>`, `<Escape,f>`</span></span>

### <a name="gotobrace"></a><span data-ttu-id="7846e-498">GotoBrace</span><span class="sxs-lookup"><span data-stu-id="7846e-498">GotoBrace</span></span>

<span data-ttu-id="7846e-499">Перейдите к парной фигурной скобке, круглой скобке или квадратной скобке.</span><span class="sxs-lookup"><span data-stu-id="7846e-499">Go to the matching brace, parenthesis, or square bracket.</span></span>

- <span data-ttu-id="7846e-500">Процессор `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="7846e-500">Cmd: `<Ctrl+]>`</span></span>
- <span data-ttu-id="7846e-501">Режим вставки в VI: `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="7846e-501">Vi insert mode: `<Ctrl+]>`</span></span>
- <span data-ttu-id="7846e-502">Режим команд VI: `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="7846e-502">Vi command mode: `<Ctrl+]>`</span></span>

### <a name="gotocolumn"></a><span data-ttu-id="7846e-503">готоколумн</span><span class="sxs-lookup"><span data-stu-id="7846e-503">GotoColumn</span></span>

<span data-ttu-id="7846e-504">Переход к столбцу, указанному аргументом arg.</span><span class="sxs-lookup"><span data-stu-id="7846e-504">Move to the column indicated by arg.</span></span>

- <span data-ttu-id="7846e-505">Режим команд VI: `<|>`</span><span class="sxs-lookup"><span data-stu-id="7846e-505">Vi command mode: `<|>`</span></span>

### <a name="gotofirstnonblankofline"></a><span data-ttu-id="7846e-506">готофирстнонбланкофлине</span><span class="sxs-lookup"><span data-stu-id="7846e-506">GotoFirstNonBlankOfLine</span></span>

<span data-ttu-id="7846e-507">Переместить курсор к первому непустому символу в строке.</span><span class="sxs-lookup"><span data-stu-id="7846e-507">Move the cursor to the first non-blank character in the line.</span></span>

- <span data-ttu-id="7846e-508">Режим команд VI: `<^>` , `<_>`</span><span class="sxs-lookup"><span data-stu-id="7846e-508">Vi command mode: `<^>`, `<_>`</span></span>

### <a name="movetoendofline"></a><span data-ttu-id="7846e-509">моветоендофлине</span><span class="sxs-lookup"><span data-stu-id="7846e-509">MoveToEndOfLine</span></span>

<span data-ttu-id="7846e-510">Переместить курсор в конец входных данных.</span><span class="sxs-lookup"><span data-stu-id="7846e-510">Move the cursor to the end of the input.</span></span>

- <span data-ttu-id="7846e-511">Режим команд VI: `<End>` , `<$>`</span><span class="sxs-lookup"><span data-stu-id="7846e-511">Vi command mode: `<End>`, `<$>`</span></span>

### <a name="nextline"></a><span data-ttu-id="7846e-512">некстлине</span><span class="sxs-lookup"><span data-stu-id="7846e-512">NextLine</span></span>

<span data-ttu-id="7846e-513">Переместить курсор на следующую строку.</span><span class="sxs-lookup"><span data-stu-id="7846e-513">Move the cursor to the next line.</span></span>

- <span data-ttu-id="7846e-514">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="7846e-514">Function is unbound.</span></span>

### <a name="nextword"></a><span data-ttu-id="7846e-515">некстворд</span><span class="sxs-lookup"><span data-stu-id="7846e-515">NextWord</span></span>

<span data-ttu-id="7846e-516">Переместить курсор вперед к началу следующего слова.</span><span class="sxs-lookup"><span data-stu-id="7846e-516">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="7846e-517">Границы слов определяются с помощью настраиваемого набора символов.</span><span class="sxs-lookup"><span data-stu-id="7846e-517">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="7846e-518">Процессор `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="7846e-518">Cmd: `<Ctrl+RightArrow>`</span></span>
- <span data-ttu-id="7846e-519">Режим вставки в VI: `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="7846e-519">Vi insert mode: `<Ctrl+RightArrow>`</span></span>
- <span data-ttu-id="7846e-520">Режим команд VI: `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="7846e-520">Vi command mode: `<Ctrl+RightArrow>`</span></span>

### <a name="nextwordend"></a><span data-ttu-id="7846e-521">некстворденд</span><span class="sxs-lookup"><span data-stu-id="7846e-521">NextWordEnd</span></span>

<span data-ttu-id="7846e-522">Переместить курсор вперед к концу текущего слова или между словами, до конца следующего слова.</span><span class="sxs-lookup"><span data-stu-id="7846e-522">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="7846e-523">Границы слов определяются с помощью настраиваемого набора символов.</span><span class="sxs-lookup"><span data-stu-id="7846e-523">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="7846e-524">Режим команд VI: `<e>`</span><span class="sxs-lookup"><span data-stu-id="7846e-524">Vi command mode: `<e>`</span></span>

### <a name="previousline"></a><span data-ttu-id="7846e-525">превиауслине</span><span class="sxs-lookup"><span data-stu-id="7846e-525">PreviousLine</span></span>

<span data-ttu-id="7846e-526">Переместить курсор на предыдущую строку.</span><span class="sxs-lookup"><span data-stu-id="7846e-526">Move the cursor to the previous line.</span></span>

- <span data-ttu-id="7846e-527">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="7846e-527">Function is unbound.</span></span>

### <a name="shellbackwardword"></a><span data-ttu-id="7846e-528">шеллбакквардворд</span><span class="sxs-lookup"><span data-stu-id="7846e-528">ShellBackwardWord</span></span>

<span data-ttu-id="7846e-529">Перемещение курсора назад к началу текущего слова или между словами, с начала предыдущего слова.</span><span class="sxs-lookup"><span data-stu-id="7846e-529">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="7846e-530">Границы слов определяются токенами PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7846e-530">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="7846e-531">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="7846e-531">Function is unbound.</span></span>

### <a name="shellforwardword"></a><span data-ttu-id="7846e-532">шеллфорвардворд</span><span class="sxs-lookup"><span data-stu-id="7846e-532">ShellForwardWord</span></span>

<span data-ttu-id="7846e-533">Переместить курсор вперед к началу следующего слова.</span><span class="sxs-lookup"><span data-stu-id="7846e-533">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="7846e-534">Границы слов определяются токенами PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7846e-534">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="7846e-535">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="7846e-535">Function is unbound.</span></span>

### <a name="shellnextword"></a><span data-ttu-id="7846e-536">шеллнекстворд</span><span class="sxs-lookup"><span data-stu-id="7846e-536">ShellNextWord</span></span>

<span data-ttu-id="7846e-537">Переместить курсор вперед к концу текущего слова или между словами, до конца следующего слова.</span><span class="sxs-lookup"><span data-stu-id="7846e-537">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="7846e-538">Границы слов определяются токенами PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7846e-538">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="7846e-539">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="7846e-539">Function is unbound.</span></span>

### <a name="vibackwardchar"></a><span data-ttu-id="7846e-540">вибакквардчар</span><span class="sxs-lookup"><span data-stu-id="7846e-540">ViBackwardChar</span></span>

<span data-ttu-id="7846e-541">Переместить курсор на один символ влево в режиме редактирования VI.</span><span class="sxs-lookup"><span data-stu-id="7846e-541">Move the cursor one character to the left in the Vi edit mode.</span></span> <span data-ttu-id="7846e-542">Это может переместить курсор к предыдущей строке многострочного ввода.</span><span class="sxs-lookup"><span data-stu-id="7846e-542">This may move the cursor to the previous line of multi-line input.</span></span>

- <span data-ttu-id="7846e-543">Режим вставки в VI: `<LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="7846e-543">Vi insert mode: `<LeftArrow>`</span></span>
- <span data-ttu-id="7846e-544">Режим команд VI: `<LeftArrow>` , `<Backspace>` , `<h>`</span><span class="sxs-lookup"><span data-stu-id="7846e-544">Vi command mode: `<LeftArrow>`, `<Backspace>`, `<h>`</span></span>

### <a name="vibackwardword"></a><span data-ttu-id="7846e-545">вибакквардворд</span><span class="sxs-lookup"><span data-stu-id="7846e-545">ViBackwardWord</span></span>

<span data-ttu-id="7846e-546">Перемещение курсора назад к началу текущего слова или между словами, с начала предыдущего слова.</span><span class="sxs-lookup"><span data-stu-id="7846e-546">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="7846e-547">Границы слов определяются с помощью настраиваемого набора символов.</span><span class="sxs-lookup"><span data-stu-id="7846e-547">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="7846e-548">Режим команд VI: `<b>`</span><span class="sxs-lookup"><span data-stu-id="7846e-548">Vi command mode: `<b>`</span></span>

### <a name="viforwardchar"></a><span data-ttu-id="7846e-549">вифорвардчар</span><span class="sxs-lookup"><span data-stu-id="7846e-549">ViForwardChar</span></span>

<span data-ttu-id="7846e-550">Переместить курсор на один символ вправо в режиме редактирования VI.</span><span class="sxs-lookup"><span data-stu-id="7846e-550">Move the cursor one character to the right in the Vi edit mode.</span></span> <span data-ttu-id="7846e-551">Это может переместить курсор на следующую строку многострочного ввода.</span><span class="sxs-lookup"><span data-stu-id="7846e-551">This may move the cursor to the next line of multi-line input.</span></span>

- <span data-ttu-id="7846e-552">Режим вставки в VI: `<RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="7846e-552">Vi insert mode: `<RightArrow>`</span></span>
- <span data-ttu-id="7846e-553">Режим команд VI: `<RightArrow>` , `<Spacebar>` , `<l>`</span><span class="sxs-lookup"><span data-stu-id="7846e-553">Vi command mode: `<RightArrow>`, `<Spacebar>`, `<l>`</span></span>

### <a name="viendofglob"></a><span data-ttu-id="7846e-554">виендофглоб</span><span class="sxs-lookup"><span data-stu-id="7846e-554">ViEndOfGlob</span></span>

<span data-ttu-id="7846e-555">Перемещает курсор в конец слова, используя только пробелы в качестве разделителей.</span><span class="sxs-lookup"><span data-stu-id="7846e-555">Moves the cursor to the end of the word, using only white space as delimiters.</span></span>

- <span data-ttu-id="7846e-556">Режим команд VI: `<E>`</span><span class="sxs-lookup"><span data-stu-id="7846e-556">Vi command mode: `<E>`</span></span>

### <a name="viendofpreviousglob"></a><span data-ttu-id="7846e-557">виендофпревиаусглоб</span><span class="sxs-lookup"><span data-stu-id="7846e-557">ViEndOfPreviousGlob</span></span>

<span data-ttu-id="7846e-558">Переход к концу предыдущего слова с использованием только пробелов в качестве разделителя слов.</span><span class="sxs-lookup"><span data-stu-id="7846e-558">Moves to the end of the previous word, using only white space as a word delimiter.</span></span>

- <span data-ttu-id="7846e-559">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="7846e-559">Function is unbound.</span></span>

### <a name="vigotobrace"></a><span data-ttu-id="7846e-560">виготобраце</span><span class="sxs-lookup"><span data-stu-id="7846e-560">ViGotoBrace</span></span>

<span data-ttu-id="7846e-561">Аналогичен Готобраце, но является символом, а не основан на токене.</span><span class="sxs-lookup"><span data-stu-id="7846e-561">Similar to GotoBrace, but is character based instead of token based.</span></span>

- <span data-ttu-id="7846e-562">Режим команд VI: `<%>`</span><span class="sxs-lookup"><span data-stu-id="7846e-562">Vi command mode: `<%>`</span></span>

### <a name="vinextglob"></a><span data-ttu-id="7846e-563">винекстглоб</span><span class="sxs-lookup"><span data-stu-id="7846e-563">ViNextGlob</span></span>

<span data-ttu-id="7846e-564">Переход к следующему слову с использованием только пробелов в качестве разделителя слов.</span><span class="sxs-lookup"><span data-stu-id="7846e-564">Moves to the next word, using only white space as a word delimiter.</span></span>

- <span data-ttu-id="7846e-565">Режим команд VI: `<W>`</span><span class="sxs-lookup"><span data-stu-id="7846e-565">Vi command mode: `<W>`</span></span>

### <a name="vinextword"></a><span data-ttu-id="7846e-566">винекстворд</span><span class="sxs-lookup"><span data-stu-id="7846e-566">ViNextWord</span></span>

<span data-ttu-id="7846e-567">Переместить курсор вперед к началу следующего слова.</span><span class="sxs-lookup"><span data-stu-id="7846e-567">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="7846e-568">Границы слов определяются с помощью настраиваемого набора символов.</span><span class="sxs-lookup"><span data-stu-id="7846e-568">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="7846e-569">Режим команд VI: `<w>`</span><span class="sxs-lookup"><span data-stu-id="7846e-569">Vi command mode: `<w>`</span></span>

## <a name="history-functions"></a><span data-ttu-id="7846e-570">Функции журнала</span><span class="sxs-lookup"><span data-stu-id="7846e-570">History functions</span></span>

### <a name="beginningofhistory"></a><span data-ttu-id="7846e-571">бегиннингофхистори</span><span class="sxs-lookup"><span data-stu-id="7846e-571">BeginningOfHistory</span></span>

<span data-ttu-id="7846e-572">Перейти к первому элементу в журнале.</span><span class="sxs-lookup"><span data-stu-id="7846e-572">Move to the first item in the history.</span></span>

- <span data-ttu-id="7846e-573">Emacs: `<Alt+<>`</span><span class="sxs-lookup"><span data-stu-id="7846e-573">Emacs: `<Alt+<>`</span></span>

### <a name="clearhistory"></a><span data-ttu-id="7846e-574">клеархистори</span><span class="sxs-lookup"><span data-stu-id="7846e-574">ClearHistory</span></span>

<span data-ttu-id="7846e-575">Очищает журнал в PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="7846e-575">Clears history in PSReadLine.</span></span> <span data-ttu-id="7846e-576">Это не влияет на журнал PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7846e-576">This does not affect PowerShell history.</span></span>

- <span data-ttu-id="7846e-577">Процессор `<Alt+F7>`</span><span class="sxs-lookup"><span data-stu-id="7846e-577">Cmd: `<Alt+F7>`</span></span>

### <a name="endofhistory"></a><span data-ttu-id="7846e-578">ендофхистори</span><span class="sxs-lookup"><span data-stu-id="7846e-578">EndOfHistory</span></span>

<span data-ttu-id="7846e-579">Переход к последнему элементу (текущему входному объекту) в журнале.</span><span class="sxs-lookup"><span data-stu-id="7846e-579">Move to the last item (the current input) in the history.</span></span>

- <span data-ttu-id="7846e-580">Emacs: `<Alt+>>`</span><span class="sxs-lookup"><span data-stu-id="7846e-580">Emacs: `<Alt+>>`</span></span>

### <a name="forwardsearchhistory"></a><span data-ttu-id="7846e-581">форвардсеарчхистори</span><span class="sxs-lookup"><span data-stu-id="7846e-581">ForwardSearchHistory</span></span>

<span data-ttu-id="7846e-582">Выполните добавочный поиск по журналу.</span><span class="sxs-lookup"><span data-stu-id="7846e-582">Perform an incremental forward search through history.</span></span>

- <span data-ttu-id="7846e-583">Процессор `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="7846e-583">Cmd: `<Ctrl+s>`</span></span>
- <span data-ttu-id="7846e-584">Emacs: `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="7846e-584">Emacs: `<Ctrl+s>`</span></span>

### <a name="historysearchbackward"></a><span data-ttu-id="7846e-585">хисторисеарчбакквард</span><span class="sxs-lookup"><span data-stu-id="7846e-585">HistorySearchBackward</span></span>

<span data-ttu-id="7846e-586">Замените текущие входные данные элементом "Previous" из журнала PSReadLine, который соответствует символам между началом и входом и курсором.</span><span class="sxs-lookup"><span data-stu-id="7846e-586">Replace the current input with the 'previous' item from PSReadLine history that matches the characters between the start and the input and the cursor.</span></span>

- <span data-ttu-id="7846e-587">Процессор `<F8>`</span><span class="sxs-lookup"><span data-stu-id="7846e-587">Cmd: `<F8>`</span></span>

### <a name="historysearchforward"></a><span data-ttu-id="7846e-588">хисторисеарчфорвард</span><span class="sxs-lookup"><span data-stu-id="7846e-588">HistorySearchForward</span></span>

<span data-ttu-id="7846e-589">Замените текущие входные данные элементом "Next" из журнала PSReadLine, который соответствует символам между началом и входом и курсором.</span><span class="sxs-lookup"><span data-stu-id="7846e-589">Replace the current input with the 'next' item from PSReadLine history that matches the characters between the start and the input and the cursor.</span></span>

- <span data-ttu-id="7846e-590">Процессор `<Shift+F8>`</span><span class="sxs-lookup"><span data-stu-id="7846e-590">Cmd: `<Shift+F8>`</span></span>

### <a name="nexthistory"></a><span data-ttu-id="7846e-591">некссистори</span><span class="sxs-lookup"><span data-stu-id="7846e-591">NextHistory</span></span>

<span data-ttu-id="7846e-592">Замените текущие входные данные на элемент "Next" из журнала PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="7846e-592">Replace the current input with the 'next' item from PSReadLine history.</span></span>

- <span data-ttu-id="7846e-593">Процессор `<DownArrow>`</span><span class="sxs-lookup"><span data-stu-id="7846e-593">Cmd: `<DownArrow>`</span></span>
- <span data-ttu-id="7846e-594">Emacs: `<DownArrow>` , `<Ctrl+n>`</span><span class="sxs-lookup"><span data-stu-id="7846e-594">Emacs: `<DownArrow>`, `<Ctrl+n>`</span></span>
- <span data-ttu-id="7846e-595">Режим вставки в VI: `<DownArrow>`</span><span class="sxs-lookup"><span data-stu-id="7846e-595">Vi insert mode: `<DownArrow>`</span></span>
- <span data-ttu-id="7846e-596">Режим команд VI: `<DownArrow>` , `<j>` , `<+>`</span><span class="sxs-lookup"><span data-stu-id="7846e-596">Vi command mode: `<DownArrow>`, `<j>`, `<+>`</span></span>

### <a name="previoushistory"></a><span data-ttu-id="7846e-597">превиаушистори</span><span class="sxs-lookup"><span data-stu-id="7846e-597">PreviousHistory</span></span>

<span data-ttu-id="7846e-598">Замените текущие входные данные элементом "Previous" из журнала PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="7846e-598">Replace the current input with the 'previous' item from PSReadLine history.</span></span>

- <span data-ttu-id="7846e-599">Процессор `<UpArrow>`</span><span class="sxs-lookup"><span data-stu-id="7846e-599">Cmd: `<UpArrow>`</span></span>
- <span data-ttu-id="7846e-600">Emacs: `<UpArrow>` , `<Ctrl+p>`</span><span class="sxs-lookup"><span data-stu-id="7846e-600">Emacs: `<UpArrow>`, `<Ctrl+p>`</span></span>
- <span data-ttu-id="7846e-601">Режим вставки в VI: `<UpArrow>`</span><span class="sxs-lookup"><span data-stu-id="7846e-601">Vi insert mode: `<UpArrow>`</span></span>
- <span data-ttu-id="7846e-602">Режим команд VI: `<UpArrow>` , `<k>` , `<->`</span><span class="sxs-lookup"><span data-stu-id="7846e-602">Vi command mode: `<UpArrow>`, `<k>`, `<->`</span></span>

### <a name="reversesearchhistory"></a><span data-ttu-id="7846e-603">реверсесеарчхистори</span><span class="sxs-lookup"><span data-stu-id="7846e-603">ReverseSearchHistory</span></span>

<span data-ttu-id="7846e-604">Выполните добавочный поиск по журналу.</span><span class="sxs-lookup"><span data-stu-id="7846e-604">Perform an incremental backward search through history.</span></span>

- <span data-ttu-id="7846e-605">Процессор `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="7846e-605">Cmd: `<Ctrl+r>`</span></span>
- <span data-ttu-id="7846e-606">Emacs: `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="7846e-606">Emacs: `<Ctrl+r>`</span></span>

### <a name="visearchhistorybackward"></a><span data-ttu-id="7846e-607">висеарчхисторибакквард</span><span class="sxs-lookup"><span data-stu-id="7846e-607">ViSearchHistoryBackward</span></span>

<span data-ttu-id="7846e-608">Запрашивает строку поиска и инициирует поиск по запросу Акцептлине.</span><span class="sxs-lookup"><span data-stu-id="7846e-608">Prompts for a search string and initiates search upon AcceptLine.</span></span>

- <span data-ttu-id="7846e-609">Режим вставки в VI: `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="7846e-609">Vi insert mode: `<Ctrl+r>`</span></span>
- <span data-ttu-id="7846e-610">Режим команд VI: `</>` , `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="7846e-610">Vi command mode: `</>`, `<Ctrl+r>`</span></span>

## <a name="completion-functions"></a><span data-ttu-id="7846e-611">Функции завершения</span><span class="sxs-lookup"><span data-stu-id="7846e-611">Completion functions</span></span>

### <a name="complete"></a><span data-ttu-id="7846e-612">Завершить</span><span class="sxs-lookup"><span data-stu-id="7846e-612">Complete</span></span>

<span data-ttu-id="7846e-613">Попытка выполнить завершение в тексте, окружающем курсор.</span><span class="sxs-lookup"><span data-stu-id="7846e-613">Attempt to perform completion on the text surrounding the cursor.</span></span> <span data-ttu-id="7846e-614">Если существует несколько возможных завершений, для завершения используется самый длинный ненеоднозначный префикс.</span><span class="sxs-lookup"><span data-stu-id="7846e-614">If there are multiple possible completions, the longest unambiguous prefix is used for completion.</span></span> <span data-ttu-id="7846e-615">При попытке выполнить наибольшее неоднозначное Завершение отображается список возможных завершений.</span><span class="sxs-lookup"><span data-stu-id="7846e-615">If trying to complete the longest unambiguous completion, a list of possible completions is displayed.</span></span>

- <span data-ttu-id="7846e-616">Emacs: `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="7846e-616">Emacs: `<Tab>`</span></span>

### <a name="menucomplete"></a><span data-ttu-id="7846e-617">менукомплете</span><span class="sxs-lookup"><span data-stu-id="7846e-617">MenuComplete</span></span>

<span data-ttu-id="7846e-618">Попытка выполнить завершение в тексте, окружающем курсор.</span><span class="sxs-lookup"><span data-stu-id="7846e-618">Attempt to perform completion on the text surrounding the cursor.</span></span> <span data-ttu-id="7846e-619">Если существует несколько возможных завершений, для завершения используется самый длинный ненеоднозначный префикс.</span><span class="sxs-lookup"><span data-stu-id="7846e-619">If there are multiple possible completions, the longest unambiguous prefix is used for completion.</span></span> <span data-ttu-id="7846e-620">При попытке выполнить наибольшее неоднозначное Завершение отображается список возможных завершений.</span><span class="sxs-lookup"><span data-stu-id="7846e-620">If trying to complete the longest unambiguous completion, a list of possible completions is displayed.</span></span>

- <span data-ttu-id="7846e-621">Cmd: `<Ctrl+@>` , `<Ctrl+Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="7846e-621">Cmd: `<Ctrl+@>`, `<Ctrl+Spacebar>`</span></span>
- <span data-ttu-id="7846e-622">Emacs: `<Ctrl+Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="7846e-622">Emacs: `<Ctrl+Spacebar>`</span></span>

### <a name="possiblecompletions"></a><span data-ttu-id="7846e-623">поссиблекомплетионс</span><span class="sxs-lookup"><span data-stu-id="7846e-623">PossibleCompletions</span></span>

<span data-ttu-id="7846e-624">Отображение списка возможных завершений.</span><span class="sxs-lookup"><span data-stu-id="7846e-624">Display the list of possible completions.</span></span>

- <span data-ttu-id="7846e-625">Emacs: `<Alt+=>`</span><span class="sxs-lookup"><span data-stu-id="7846e-625">Emacs: `<Alt+=>`</span></span>
- <span data-ttu-id="7846e-626">Режим вставки в VI: `<Ctrl+Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="7846e-626">Vi insert mode: `<Ctrl+Spacebar>`</span></span>
- <span data-ttu-id="7846e-627">Режим команд VI: `<Ctrl+Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="7846e-627">Vi command mode: `<Ctrl+Spacebar>`</span></span>

### <a name="tabcompletenext"></a><span data-ttu-id="7846e-628">табкомплетенекст</span><span class="sxs-lookup"><span data-stu-id="7846e-628">TabCompleteNext</span></span>

<span data-ttu-id="7846e-629">Попытайтесь завершить текст, окружающий курсор, с помощью следующего доступного завершения.</span><span class="sxs-lookup"><span data-stu-id="7846e-629">Attempt to complete the text surrounding the cursor with the next available completion.</span></span>

- <span data-ttu-id="7846e-630">Процессор `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="7846e-630">Cmd: `<Tab>`</span></span>
- <span data-ttu-id="7846e-631">Режим команд VI: `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="7846e-631">Vi command mode: `<Tab>`</span></span>

### <a name="tabcompleteprevious"></a><span data-ttu-id="7846e-632">табкомплетепревиаус</span><span class="sxs-lookup"><span data-stu-id="7846e-632">TabCompletePrevious</span></span>

<span data-ttu-id="7846e-633">Попытайтесь завершить текст, окружающий курсор, с предыдущим доступным завершением.</span><span class="sxs-lookup"><span data-stu-id="7846e-633">Attempt to complete the text surrounding the cursor with the previous available completion.</span></span>

- <span data-ttu-id="7846e-634">Процессор `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="7846e-634">Cmd: `<Shift+Tab>`</span></span>
- <span data-ttu-id="7846e-635">Режим команд VI: `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="7846e-635">Vi command mode: `<Shift+Tab>`</span></span>

### <a name="vitabcompletenext"></a><span data-ttu-id="7846e-636">витабкомплетенекст</span><span class="sxs-lookup"><span data-stu-id="7846e-636">ViTabCompleteNext</span></span>

<span data-ttu-id="7846e-637">При необходимости завершает текущую группу редактирования и вызывает Табкомплетенекст.</span><span class="sxs-lookup"><span data-stu-id="7846e-637">Ends the current edit group, if needed, and invokes TabCompleteNext.</span></span>

- <span data-ttu-id="7846e-638">Режим вставки в VI: `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="7846e-638">Vi insert mode: `<Tab>`</span></span>

### <a name="vitabcompleteprevious"></a><span data-ttu-id="7846e-639">витабкомплетепревиаус</span><span class="sxs-lookup"><span data-stu-id="7846e-639">ViTabCompletePrevious</span></span>

<span data-ttu-id="7846e-640">При необходимости завершает текущую группу редактирования и вызывает Табкомплетепревиаус.</span><span class="sxs-lookup"><span data-stu-id="7846e-640">Ends the current edit group, if needed, and invokes TabCompletePrevious.</span></span>

- <span data-ttu-id="7846e-641">Режим вставки в VI: `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="7846e-641">Vi insert mode: `<Shift+Tab>`</span></span>

## <a name="miscellaneous-functions"></a><span data-ttu-id="7846e-642">Прочие функции</span><span class="sxs-lookup"><span data-stu-id="7846e-642">Miscellaneous functions</span></span>

### <a name="acceptnextsuggestionword"></a><span data-ttu-id="7846e-643">акцептнекстсугжестионворд</span><span class="sxs-lookup"><span data-stu-id="7846e-643">AcceptNextSuggestionWord</span></span>

<span data-ttu-id="7846e-644">Принять следующее слово встроенного или выбранного предложения.</span><span class="sxs-lookup"><span data-stu-id="7846e-644">Accept the next word of the inline or selected suggestion.</span></span>

- <span data-ttu-id="7846e-645">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="7846e-645">Function is unbound.</span></span>

### <a name="acceptsuggestion"></a><span data-ttu-id="7846e-646">акцептсугжестион</span><span class="sxs-lookup"><span data-stu-id="7846e-646">AcceptSuggestion</span></span>

<span data-ttu-id="7846e-647">Принять текущее встроенное или выбранное предложение.</span><span class="sxs-lookup"><span data-stu-id="7846e-647">Accept the current inline or selected suggestion.</span></span>

- <span data-ttu-id="7846e-648">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="7846e-648">Function is unbound.</span></span>

### <a name="capturescreen"></a><span data-ttu-id="7846e-649">каптурескрин</span><span class="sxs-lookup"><span data-stu-id="7846e-649">CaptureScreen</span></span>

<span data-ttu-id="7846e-650">Запуск интерактивной записи экрана — стрелки вверх и вниз выбор строк, ввод копирует выделенный текст в буфер обмена в виде текста и HTML.</span><span class="sxs-lookup"><span data-stu-id="7846e-650">Start interactive screen capture - up/down arrows select lines, enter copies selected text to clipboard as text and html.</span></span>

- <span data-ttu-id="7846e-651">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="7846e-651">Function is unbound.</span></span>

### <a name="clearscreen"></a><span data-ttu-id="7846e-652">клеарскрин</span><span class="sxs-lookup"><span data-stu-id="7846e-652">ClearScreen</span></span>

<span data-ttu-id="7846e-653">Очистить экран и нарисовать текущую строку в верхней части экрана.</span><span class="sxs-lookup"><span data-stu-id="7846e-653">Clear the screen and draw the current line at the top of the screen.</span></span>

- <span data-ttu-id="7846e-654">Процессор `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="7846e-654">Cmd: `<Ctrl+l>`</span></span>
- <span data-ttu-id="7846e-655">Emacs: `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="7846e-655">Emacs: `<Ctrl+l>`</span></span>
- <span data-ttu-id="7846e-656">Режим вставки в VI: `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="7846e-656">Vi insert mode: `<Ctrl+l>`</span></span>
- <span data-ttu-id="7846e-657">Режим команд VI: `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="7846e-657">Vi command mode: `<Ctrl+l>`</span></span>

### <a name="digitargument"></a><span data-ttu-id="7846e-658">дигитаргумент</span><span class="sxs-lookup"><span data-stu-id="7846e-658">DigitArgument</span></span>

<span data-ttu-id="7846e-659">Начните новый аргумент цифры для передачи другим функциям.</span><span class="sxs-lookup"><span data-stu-id="7846e-659">Start a new digit argument to pass to other functions.</span></span>

- <span data-ttu-id="7846e-660">Cmd: `<Alt+0>` , `<Alt+1>` , `<Alt+2>` , `<Alt+3>` , `<Alt+4>` , `<Alt+5>` , `<Alt+6>` , `<Alt+7>` , `<Alt+8>` , `<Alt+9>` , `<Alt+->`</span><span class="sxs-lookup"><span data-stu-id="7846e-660">Cmd: `<Alt+0>`, `<Alt+1>`, `<Alt+2>`, `<Alt+3>`, `<Alt+4>`, `<Alt+5>`, `<Alt+6>`, `<Alt+7>`, `<Alt+8>`, `<Alt+9>`, `<Alt+->`</span></span>
- <span data-ttu-id="7846e-661">Emacs: `<Alt+0>` , `<Alt+1>` , `<Alt+2>` , `<Alt+3>` , `<Alt+4>` , `<Alt+5>` , `<Alt+6>` , `<Alt+7>` , `<Alt+8>` , `<Alt+9>` , `<Alt+->`</span><span class="sxs-lookup"><span data-stu-id="7846e-661">Emacs: `<Alt+0>`, `<Alt+1>`, `<Alt+2>`, `<Alt+3>`, `<Alt+4>`, `<Alt+5>`, `<Alt+6>`, `<Alt+7>`, `<Alt+8>`, `<Alt+9>`, `<Alt+->`</span></span>
- <span data-ttu-id="7846e-662">Режим команд VI: `<0>` , `<1>` , `<2>` , `<3>` , `<4>` , `<5>` , `<6>` , `<7>` , `<8>` , `<9>`</span><span class="sxs-lookup"><span data-stu-id="7846e-662">Vi command mode: `<0>`, `<1>`, `<2>`, `<3>`, `<4>`, `<5>`, `<6>`, `<7>`, `<8>`, `<9>`</span></span>

### <a name="invokeprompt"></a><span data-ttu-id="7846e-663">инвокепромпт</span><span class="sxs-lookup"><span data-stu-id="7846e-663">InvokePrompt</span></span>

<span data-ttu-id="7846e-664">Стирает текущий запрос и вызывает функцию Prompt для повторного вывода запроса.</span><span class="sxs-lookup"><span data-stu-id="7846e-664">Erases the current prompt and calls the prompt function to redisplay the prompt.</span></span> <span data-ttu-id="7846e-665">Полезен для обработчиков пользовательских ключей, изменяющих состояние, например для изменения текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="7846e-665">Useful for custom key handlers that change state, e.g. change the current directory.</span></span>

- <span data-ttu-id="7846e-666">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="7846e-666">Function is unbound.</span></span>

### <a name="scrolldisplaydown"></a><span data-ttu-id="7846e-667">скроллдисплайдовн</span><span class="sxs-lookup"><span data-stu-id="7846e-667">ScrollDisplayDown</span></span>

<span data-ttu-id="7846e-668">Прокрутите экран вниз на один экран.</span><span class="sxs-lookup"><span data-stu-id="7846e-668">Scroll the display down one screen.</span></span>

- <span data-ttu-id="7846e-669">Процессор `<PageDown>`</span><span class="sxs-lookup"><span data-stu-id="7846e-669">Cmd: `<PageDown>`</span></span>
- <span data-ttu-id="7846e-670">Emacs: `<PageDown>`</span><span class="sxs-lookup"><span data-stu-id="7846e-670">Emacs: `<PageDown>`</span></span>

### <a name="scrolldisplaydownline"></a><span data-ttu-id="7846e-671">скроллдисплайдовнлине</span><span class="sxs-lookup"><span data-stu-id="7846e-671">ScrollDisplayDownLine</span></span>

<span data-ttu-id="7846e-672">Прокрутите экран вниз на одну строку.</span><span class="sxs-lookup"><span data-stu-id="7846e-672">Scroll the display down one line.</span></span>

- <span data-ttu-id="7846e-673">Процессор `<Ctrl+PageDown>`</span><span class="sxs-lookup"><span data-stu-id="7846e-673">Cmd: `<Ctrl+PageDown>`</span></span>
- <span data-ttu-id="7846e-674">Emacs: `<Ctrl+PageDown>`</span><span class="sxs-lookup"><span data-stu-id="7846e-674">Emacs: `<Ctrl+PageDown>`</span></span>

### <a name="scrolldisplaytocursor"></a><span data-ttu-id="7846e-675">скроллдисплайтокурсор</span><span class="sxs-lookup"><span data-stu-id="7846e-675">ScrollDisplayToCursor</span></span>

<span data-ttu-id="7846e-676">Прокрутить экран до курсора.</span><span class="sxs-lookup"><span data-stu-id="7846e-676">Scroll the display to the cursor.</span></span>

- <span data-ttu-id="7846e-677">Emacs: `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="7846e-677">Emacs: `<Ctrl+End>`</span></span>

### <a name="scrolldisplaytop"></a><span data-ttu-id="7846e-678">скроллдисплайтоп</span><span class="sxs-lookup"><span data-stu-id="7846e-678">ScrollDisplayTop</span></span>

<span data-ttu-id="7846e-679">Прокрутите экран до верха.</span><span class="sxs-lookup"><span data-stu-id="7846e-679">Scroll the display to the top.</span></span>

- <span data-ttu-id="7846e-680">Emacs: `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="7846e-680">Emacs: `<Ctrl+Home>`</span></span>

### <a name="scrolldisplayup"></a><span data-ttu-id="7846e-681">скроллдисплайуп</span><span class="sxs-lookup"><span data-stu-id="7846e-681">ScrollDisplayUp</span></span>

<span data-ttu-id="7846e-682">Прокрутите экран вверх на один экран.</span><span class="sxs-lookup"><span data-stu-id="7846e-682">Scroll the display up one screen.</span></span>

- <span data-ttu-id="7846e-683">Процессор `<PageUp>`</span><span class="sxs-lookup"><span data-stu-id="7846e-683">Cmd: `<PageUp>`</span></span>
- <span data-ttu-id="7846e-684">Emacs: `<PageUp>`</span><span class="sxs-lookup"><span data-stu-id="7846e-684">Emacs: `<PageUp>`</span></span>

### <a name="scrolldisplayupline"></a><span data-ttu-id="7846e-685">скроллдисплайуплине</span><span class="sxs-lookup"><span data-stu-id="7846e-685">ScrollDisplayUpLine</span></span>

<span data-ttu-id="7846e-686">Прокрутите экран вверх на одну строку.</span><span class="sxs-lookup"><span data-stu-id="7846e-686">Scroll the display up one line.</span></span>

- <span data-ttu-id="7846e-687">Процессор `<Ctrl+PageUp>`</span><span class="sxs-lookup"><span data-stu-id="7846e-687">Cmd: `<Ctrl+PageUp>`</span></span>
- <span data-ttu-id="7846e-688">Emacs: `<Ctrl+PageUp>`</span><span class="sxs-lookup"><span data-stu-id="7846e-688">Emacs: `<Ctrl+PageUp>`</span></span>

### <a name="selfinsert"></a><span data-ttu-id="7846e-689">селфинсерт</span><span class="sxs-lookup"><span data-stu-id="7846e-689">SelfInsert</span></span>

<span data-ttu-id="7846e-690">Вставьте ключ.</span><span class="sxs-lookup"><span data-stu-id="7846e-690">Insert the key.</span></span>

- <span data-ttu-id="7846e-691">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="7846e-691">Function is unbound.</span></span>

### <a name="showkeybindings"></a><span data-ttu-id="7846e-692">шовкэйбиндингс</span><span class="sxs-lookup"><span data-stu-id="7846e-692">ShowKeyBindings</span></span>

<span data-ttu-id="7846e-693">Отображение всех связанных ключей.</span><span class="sxs-lookup"><span data-stu-id="7846e-693">Show all bound keys.</span></span>

- <span data-ttu-id="7846e-694">Процессор `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="7846e-694">Cmd: `<Ctrl+Alt+?>`</span></span>
- <span data-ttu-id="7846e-695">Emacs: `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="7846e-695">Emacs: `<Ctrl+Alt+?>`</span></span>
- <span data-ttu-id="7846e-696">Режим вставки в VI: `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="7846e-696">Vi insert mode: `<Ctrl+Alt+?>`</span></span>

### <a name="vicommandmode"></a><span data-ttu-id="7846e-697">викоммандмоде</span><span class="sxs-lookup"><span data-stu-id="7846e-697">ViCommandMode</span></span>

<span data-ttu-id="7846e-698">Переключите текущий режим работы с Vi-Insert на VI-Command.</span><span class="sxs-lookup"><span data-stu-id="7846e-698">Switch the current operating mode from Vi-Insert to Vi-Command.</span></span>

- <span data-ttu-id="7846e-699">Режим вставки в VI: `<Escape>`</span><span class="sxs-lookup"><span data-stu-id="7846e-699">Vi insert mode: `<Escape>`</span></span>

### <a name="vidigitargumentinchord"></a><span data-ttu-id="7846e-700">видигитаргументинчорд</span><span class="sxs-lookup"><span data-stu-id="7846e-700">ViDigitArgumentInChord</span></span>

<span data-ttu-id="7846e-701">Начните новый числовой аргумент, чтобы передать его другим функциям в одной из сочетаний VI.</span><span class="sxs-lookup"><span data-stu-id="7846e-701">Start a new digit argument to pass to other functions while in one of vi's chords.</span></span>

- <span data-ttu-id="7846e-702">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="7846e-702">Function is unbound.</span></span>

### <a name="vieditvisually"></a><span data-ttu-id="7846e-703">виедитвисуалли</span><span class="sxs-lookup"><span data-stu-id="7846e-703">ViEditVisually</span></span>

<span data-ttu-id="7846e-704">Измените командную строку в текстовом редакторе, заданном $env: EDITOR или $env: VISUAL.</span><span class="sxs-lookup"><span data-stu-id="7846e-704">Edit the command line in a text editor specified by $env:EDITOR or $env:VISUAL.</span></span>

- <span data-ttu-id="7846e-705">Emacs: `<Ctrl+x,Ctrl+e>`</span><span class="sxs-lookup"><span data-stu-id="7846e-705">Emacs: `<Ctrl+x,Ctrl+e>`</span></span>
- <span data-ttu-id="7846e-706">Режим команд VI: `<v>`</span><span class="sxs-lookup"><span data-stu-id="7846e-706">Vi command mode: `<v>`</span></span>

### <a name="viexit"></a><span data-ttu-id="7846e-707">виексит</span><span class="sxs-lookup"><span data-stu-id="7846e-707">ViExit</span></span>

<span data-ttu-id="7846e-708">Завершает работу оболочки.</span><span class="sxs-lookup"><span data-stu-id="7846e-708">Exits the shell.</span></span>

- <span data-ttu-id="7846e-709">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="7846e-709">Function is unbound.</span></span>

### <a name="viinsertmode"></a><span data-ttu-id="7846e-710">виинсертмоде</span><span class="sxs-lookup"><span data-stu-id="7846e-710">ViInsertMode</span></span>

<span data-ttu-id="7846e-711">Переключитесь в режим вставки.</span><span class="sxs-lookup"><span data-stu-id="7846e-711">Switch to Insert mode.</span></span>

- <span data-ttu-id="7846e-712">Режим команд VI: `<i>`</span><span class="sxs-lookup"><span data-stu-id="7846e-712">Vi command mode: `<i>`</span></span>

### <a name="whatiskey"></a><span data-ttu-id="7846e-713">вхатискэй</span><span class="sxs-lookup"><span data-stu-id="7846e-713">WhatIsKey</span></span>

<span data-ttu-id="7846e-714">Прочитайте ключ и расскажите, к чему привязан ключ.</span><span class="sxs-lookup"><span data-stu-id="7846e-714">Read a key and tell me what the key is bound to.</span></span>

- <span data-ttu-id="7846e-715">Процессор `<Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="7846e-715">Cmd: `<Alt+?>`</span></span>
- <span data-ttu-id="7846e-716">Emacs: `<Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="7846e-716">Emacs: `<Alt+?>`</span></span>

## <a name="selection-functions"></a><span data-ttu-id="7846e-717">Функции выбора</span><span class="sxs-lookup"><span data-stu-id="7846e-717">Selection functions</span></span>

### <a name="exchangepointandmark"></a><span data-ttu-id="7846e-718">ексчанжепоинтандмарк</span><span class="sxs-lookup"><span data-stu-id="7846e-718">ExchangePointAndMark</span></span>

<span data-ttu-id="7846e-719">Курсор помещается в позицию метки, а метка перемещается в положение курсора.</span><span class="sxs-lookup"><span data-stu-id="7846e-719">The cursor is placed at the location of the mark and the mark is moved to the location of the cursor.</span></span>

- <span data-ttu-id="7846e-720">Emacs: `<Ctrl+x,Ctrl+x>`</span><span class="sxs-lookup"><span data-stu-id="7846e-720">Emacs: `<Ctrl+x,Ctrl+x>`</span></span>

### <a name="selectall"></a><span data-ttu-id="7846e-721">SelectAll</span><span class="sxs-lookup"><span data-stu-id="7846e-721">SelectAll</span></span>

<span data-ttu-id="7846e-722">Выделите всю строку.</span><span class="sxs-lookup"><span data-stu-id="7846e-722">Select the entire line.</span></span>

- <span data-ttu-id="7846e-723">Процессор `<Ctrl+a>`</span><span class="sxs-lookup"><span data-stu-id="7846e-723">Cmd: `<Ctrl+a>`</span></span>

### <a name="selectbackwardchar"></a><span data-ttu-id="7846e-724">селектбакквардчар</span><span class="sxs-lookup"><span data-stu-id="7846e-724">SelectBackwardChar</span></span>

<span data-ttu-id="7846e-725">Настройка текущего выделения для включения предыдущего символа.</span><span class="sxs-lookup"><span data-stu-id="7846e-725">Adjust the current selection to include the previous character.</span></span>

- <span data-ttu-id="7846e-726">Процессор `<Shift+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="7846e-726">Cmd: `<Shift+LeftArrow>`</span></span>
- <span data-ttu-id="7846e-727">Emacs: `<Shift+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="7846e-727">Emacs: `<Shift+LeftArrow>`</span></span>

### <a name="selectbackwardsline"></a><span data-ttu-id="7846e-728">селектбакквардслине</span><span class="sxs-lookup"><span data-stu-id="7846e-728">SelectBackwardsLine</span></span>

<span data-ttu-id="7846e-729">Изменить текущее выделение, чтобы включить его от курсора до начала строки.</span><span class="sxs-lookup"><span data-stu-id="7846e-729">Adjust the current selection to include from the cursor to the start of the line.</span></span>

- <span data-ttu-id="7846e-730">Процессор `<Shift+Home>`</span><span class="sxs-lookup"><span data-stu-id="7846e-730">Cmd: `<Shift+Home>`</span></span>
- <span data-ttu-id="7846e-731">Emacs: `<Shift+Home>`</span><span class="sxs-lookup"><span data-stu-id="7846e-731">Emacs: `<Shift+Home>`</span></span>

### <a name="selectbackwardword"></a><span data-ttu-id="7846e-732">селектбакквардворд</span><span class="sxs-lookup"><span data-stu-id="7846e-732">SelectBackwardWord</span></span>

<span data-ttu-id="7846e-733">Настройка текущего выделения для включения предыдущего слова.</span><span class="sxs-lookup"><span data-stu-id="7846e-733">Adjust the current selection to include the previous word.</span></span>

- <span data-ttu-id="7846e-734">Процессор `<Shift+Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="7846e-734">Cmd: `<Shift+Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="7846e-735">Emacs: `<Alt+B>`</span><span class="sxs-lookup"><span data-stu-id="7846e-735">Emacs: `<Alt+B>`</span></span>

### <a name="selectforwardchar"></a><span data-ttu-id="7846e-736">селектфорвардчар</span><span class="sxs-lookup"><span data-stu-id="7846e-736">SelectForwardChar</span></span>

<span data-ttu-id="7846e-737">Измените текущее выделение, чтобы включить следующий символ.</span><span class="sxs-lookup"><span data-stu-id="7846e-737">Adjust the current selection to include the next character.</span></span>

- <span data-ttu-id="7846e-738">Процессор `<Shift+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="7846e-738">Cmd: `<Shift+RightArrow>`</span></span>
- <span data-ttu-id="7846e-739">Emacs: `<Shift+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="7846e-739">Emacs: `<Shift+RightArrow>`</span></span>

### <a name="selectforwardword"></a><span data-ttu-id="7846e-740">селектфорвардворд</span><span class="sxs-lookup"><span data-stu-id="7846e-740">SelectForwardWord</span></span>

<span data-ttu-id="7846e-741">Измените текущее выделение, чтобы включить следующее слово с помощью Форвардворд.</span><span class="sxs-lookup"><span data-stu-id="7846e-741">Adjust the current selection to include the next word using ForwardWord.</span></span>

- <span data-ttu-id="7846e-742">Emacs: `<Alt+F>`</span><span class="sxs-lookup"><span data-stu-id="7846e-742">Emacs: `<Alt+F>`</span></span>

### <a name="selectline"></a><span data-ttu-id="7846e-743">селектлине</span><span class="sxs-lookup"><span data-stu-id="7846e-743">SelectLine</span></span>

<span data-ttu-id="7846e-744">Настройка текущего выделения для включения курсора в конец строки.</span><span class="sxs-lookup"><span data-stu-id="7846e-744">Adjust the current selection to include from the cursor to the end of the line.</span></span>

- <span data-ttu-id="7846e-745">Процессор `<Shift+End>`</span><span class="sxs-lookup"><span data-stu-id="7846e-745">Cmd: `<Shift+End>`</span></span>
- <span data-ttu-id="7846e-746">Emacs: `<Shift+End>`</span><span class="sxs-lookup"><span data-stu-id="7846e-746">Emacs: `<Shift+End>`</span></span>

### <a name="selectnextword"></a><span data-ttu-id="7846e-747">селектнекстворд</span><span class="sxs-lookup"><span data-stu-id="7846e-747">SelectNextWord</span></span>

<span data-ttu-id="7846e-748">Настройка текущего выделения для включения следующего слова.</span><span class="sxs-lookup"><span data-stu-id="7846e-748">Adjust the current selection to include the next word.</span></span>

- <span data-ttu-id="7846e-749">Процессор `<Shift+Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="7846e-749">Cmd: `<Shift+Ctrl+RightArrow>`</span></span>

### <a name="selectshellbackwardword"></a><span data-ttu-id="7846e-750">селектшеллбакквардворд</span><span class="sxs-lookup"><span data-stu-id="7846e-750">SelectShellBackwardWord</span></span>

<span data-ttu-id="7846e-751">Измените текущее выделение, чтобы включить предыдущее слово с помощью Шеллбакквардворд.</span><span class="sxs-lookup"><span data-stu-id="7846e-751">Adjust the current selection to include the previous word using ShellBackwardWord.</span></span>

- <span data-ttu-id="7846e-752">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="7846e-752">Function is unbound.</span></span>

### <a name="selectshellforwardword"></a><span data-ttu-id="7846e-753">селектшеллфорвардворд</span><span class="sxs-lookup"><span data-stu-id="7846e-753">SelectShellForwardWord</span></span>

<span data-ttu-id="7846e-754">Измените текущее выделение, чтобы включить следующее слово с помощью Шеллфорвардворд.</span><span class="sxs-lookup"><span data-stu-id="7846e-754">Adjust the current selection to include the next word using ShellForwardWord.</span></span>

- <span data-ttu-id="7846e-755">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="7846e-755">Function is unbound.</span></span>

### <a name="selectshellnextword"></a><span data-ttu-id="7846e-756">селектшеллнекстворд</span><span class="sxs-lookup"><span data-stu-id="7846e-756">SelectShellNextWord</span></span>

<span data-ttu-id="7846e-757">Измените текущее выделение, чтобы включить следующее слово с помощью Шеллнекстворд.</span><span class="sxs-lookup"><span data-stu-id="7846e-757">Adjust the current selection to include the next word using ShellNextWord.</span></span>

- <span data-ttu-id="7846e-758">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="7846e-758">Function is unbound.</span></span>

### <a name="setmark"></a><span data-ttu-id="7846e-759">сетмарк</span><span class="sxs-lookup"><span data-stu-id="7846e-759">SetMark</span></span>

<span data-ttu-id="7846e-760">Пометка текущего положения курсора для использования в последующей команде редактирования.</span><span class="sxs-lookup"><span data-stu-id="7846e-760">Mark the current location of the cursor for use in a subsequent editing command.</span></span>

- <span data-ttu-id="7846e-761">Emacs: `<Ctrl+@>`</span><span class="sxs-lookup"><span data-stu-id="7846e-761">Emacs: `<Ctrl+@>`</span></span>

## <a name="predictive-intellisense-functions"></a><span data-ttu-id="7846e-762">Функции прогнозной IntelliSense</span><span class="sxs-lookup"><span data-stu-id="7846e-762">Predictive IntelliSense functions</span></span>

> [!NOTE]
> <span data-ttu-id="7846e-763">Для использования этих функций необходимо включить прогнозную технологию IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="7846e-763">Predictive IntelliSense needs to be enabled to use these functions.</span></span>

### <a name="acceptnextwordsuggestion"></a><span data-ttu-id="7846e-764">акцептнекствордсугжестион</span><span class="sxs-lookup"><span data-stu-id="7846e-764">AcceptNextWordSuggestion</span></span>

<span data-ttu-id="7846e-765">Принимает следующее слово встроенного предложения из прогнозной IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="7846e-765">Accepts the next word of the inline suggestion from Predictive IntelliSense.</span></span>
<span data-ttu-id="7846e-766">Эту функцию можно привязать с помощью <kbd>клавиши CTRL</kbd> + <kbd>F</kbd> , выполнив следующую команду.</span><span class="sxs-lookup"><span data-stu-id="7846e-766">This function can be bound with <kbd>Ctrl</kbd>+<kbd>F</kbd> by running the following command.</span></span>

```powershell
Set-PSReadLineKeyHandler -Chord "Ctrl+f" -Function ForwardWord
```

### <a name="acceptsuggestion"></a><span data-ttu-id="7846e-767">акцептсугжестион</span><span class="sxs-lookup"><span data-stu-id="7846e-767">AcceptSuggestion</span></span>

<span data-ttu-id="7846e-768">Принимает текущее встроенное предложение от прогнозной IntelliSense, нажимая клавишу <kbd>RightArrow</kbd> , когда курсор находится в конце текущей строки.</span><span class="sxs-lookup"><span data-stu-id="7846e-768">Accepts the current inline suggestion from Predictive IntelliSense by pressing <kbd>RightArrow</kbd> when the cursor is at the end of the current line.</span></span>

## <a name="search-functions"></a><span data-ttu-id="7846e-769">Функции поиска</span><span class="sxs-lookup"><span data-stu-id="7846e-769">Search functions</span></span>

### <a name="charactersearch"></a><span data-ttu-id="7846e-770">чарактерсеарч</span><span class="sxs-lookup"><span data-stu-id="7846e-770">CharacterSearch</span></span>

<span data-ttu-id="7846e-771">Чтение символа и поиск вперед для следующего вхождения этого символа.</span><span class="sxs-lookup"><span data-stu-id="7846e-771">Read a character and search forward for the next occurrence of that character.</span></span>
<span data-ttu-id="7846e-772">Если указан аргумент, то для n-го вхождения выполните поиск вперед (или назад, если отрицательное).</span><span class="sxs-lookup"><span data-stu-id="7846e-772">If an argument is specified, search forward (or backward if negative) for the nth occurrence.</span></span>

- <span data-ttu-id="7846e-773">Процессор `<F3>`</span><span class="sxs-lookup"><span data-stu-id="7846e-773">Cmd: `<F3>`</span></span>
- <span data-ttu-id="7846e-774">Emacs: `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="7846e-774">Emacs: `<Ctrl+]>`</span></span>
- <span data-ttu-id="7846e-775">Режим вставки в VI: `<F3>`</span><span class="sxs-lookup"><span data-stu-id="7846e-775">Vi insert mode: `<F3>`</span></span>
- <span data-ttu-id="7846e-776">Режим команд VI: `<F3>`</span><span class="sxs-lookup"><span data-stu-id="7846e-776">Vi command mode: `<F3>`</span></span>

### <a name="charactersearchbackward"></a><span data-ttu-id="7846e-777">чарактерсеарчбакквард</span><span class="sxs-lookup"><span data-stu-id="7846e-777">CharacterSearchBackward</span></span>

<span data-ttu-id="7846e-778">Чтение символа и поиск следующего вхождения этого символа в обратном направлении.</span><span class="sxs-lookup"><span data-stu-id="7846e-778">Read a character and search backward for the next occurrence of that character.</span></span> <span data-ttu-id="7846e-779">Если аргумент указан, поиск в n-й последовательности осуществляется назад (или вперед, если отрицательное).</span><span class="sxs-lookup"><span data-stu-id="7846e-779">If an argument is specified, search backward (or forward if negative) for the nth occurrence.</span></span>

- <span data-ttu-id="7846e-780">Процессор `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="7846e-780">Cmd: `<Shift+F3>`</span></span>
- <span data-ttu-id="7846e-781">Emacs: `<Ctrl+Alt+]>`</span><span class="sxs-lookup"><span data-stu-id="7846e-781">Emacs: `<Ctrl+Alt+]>`</span></span>
- <span data-ttu-id="7846e-782">Режим вставки в VI: `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="7846e-782">Vi insert mode: `<Shift+F3>`</span></span>
- <span data-ttu-id="7846e-783">Режим команд VI: `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="7846e-783">Vi command mode: `<Shift+F3>`</span></span>

### <a name="repeatlastcharsearch"></a><span data-ttu-id="7846e-784">репеатластчарсеарч</span><span class="sxs-lookup"><span data-stu-id="7846e-784">RepeatLastCharSearch</span></span>

<span data-ttu-id="7846e-785">Повторите поиск последнего записанного символа.</span><span class="sxs-lookup"><span data-stu-id="7846e-785">Repeat the last recorded character search.</span></span>

- <span data-ttu-id="7846e-786">Режим команд VI: `<;>`</span><span class="sxs-lookup"><span data-stu-id="7846e-786">Vi command mode: `<;>`</span></span>

### <a name="repeatlastcharsearchbackwards"></a><span data-ttu-id="7846e-787">репеатластчарсеарчбакквардс</span><span class="sxs-lookup"><span data-stu-id="7846e-787">RepeatLastCharSearchBackwards</span></span>

<span data-ttu-id="7846e-788">Повторите поиск последнего записанного символа, но в обратном направлении.</span><span class="sxs-lookup"><span data-stu-id="7846e-788">Repeat the last recorded character search, but in the opposite direction.</span></span>

- <span data-ttu-id="7846e-789">Режим команд VI: `<,>`</span><span class="sxs-lookup"><span data-stu-id="7846e-789">Vi command mode: `<,>`</span></span>

### <a name="repeatsearch"></a><span data-ttu-id="7846e-790">репеатсеарч</span><span class="sxs-lookup"><span data-stu-id="7846e-790">RepeatSearch</span></span>

<span data-ttu-id="7846e-791">Повторите последний поиск в том же направлении, что и раньше.</span><span class="sxs-lookup"><span data-stu-id="7846e-791">Repeat the last search in the same direction as before.</span></span>

- <span data-ttu-id="7846e-792">Режим команд VI: `<n>`</span><span class="sxs-lookup"><span data-stu-id="7846e-792">Vi command mode: `<n>`</span></span>

### <a name="repeatsearchbackward"></a><span data-ttu-id="7846e-793">репеатсеарчбакквард</span><span class="sxs-lookup"><span data-stu-id="7846e-793">RepeatSearchBackward</span></span>

<span data-ttu-id="7846e-794">Повторите последний поиск в том же направлении, что и раньше.</span><span class="sxs-lookup"><span data-stu-id="7846e-794">Repeat the last search in the same direction as before.</span></span>

- <span data-ttu-id="7846e-795">Режим команд VI: `<N>`</span><span class="sxs-lookup"><span data-stu-id="7846e-795">Vi command mode: `<N>`</span></span>

### <a name="searchchar"></a><span data-ttu-id="7846e-796">сеарччар</span><span class="sxs-lookup"><span data-stu-id="7846e-796">SearchChar</span></span>

<span data-ttu-id="7846e-797">Прочитать следующий символ, затем найти его, перейти вперед, а затем отследить символ.</span><span class="sxs-lookup"><span data-stu-id="7846e-797">Read the next character and then find it, going forward, and then back off a character.</span></span> <span data-ttu-id="7846e-798">Это относится к функциональным возможностям.</span><span class="sxs-lookup"><span data-stu-id="7846e-798">This is for 't' functionality.</span></span>

- <span data-ttu-id="7846e-799">Режим команд VI: `<f>`</span><span class="sxs-lookup"><span data-stu-id="7846e-799">Vi command mode: `<f>`</span></span>

### <a name="searchcharbackward"></a><span data-ttu-id="7846e-800">сеарччарбакквард</span><span class="sxs-lookup"><span data-stu-id="7846e-800">SearchCharBackward</span></span>

<span data-ttu-id="7846e-801">Прочитать следующий символ, а затем найти его, вернуться назад, а затем отследить символ.</span><span class="sxs-lookup"><span data-stu-id="7846e-801">Read the next character and then find it, going backward, and then back off a character.</span></span> <span data-ttu-id="7846e-802">Это относится к функциональным возможностям.</span><span class="sxs-lookup"><span data-stu-id="7846e-802">This is for 'T' functionality.</span></span>

- <span data-ttu-id="7846e-803">Режим команд VI: `<F>`</span><span class="sxs-lookup"><span data-stu-id="7846e-803">Vi command mode: `<F>`</span></span>

### <a name="searchcharbackwardwithbackoff"></a><span data-ttu-id="7846e-804">сеарччарбакквардвисбаккофф</span><span class="sxs-lookup"><span data-stu-id="7846e-804">SearchCharBackwardWithBackoff</span></span>

<span data-ttu-id="7846e-805">Прочитать следующий символ, а затем найти его, вернуться назад, а затем отследить символ.</span><span class="sxs-lookup"><span data-stu-id="7846e-805">Read the next character and then find it, going backward, and then back off a character.</span></span> <span data-ttu-id="7846e-806">Это относится к функциональным возможностям.</span><span class="sxs-lookup"><span data-stu-id="7846e-806">This is for 'T' functionality.</span></span>

- <span data-ttu-id="7846e-807">Режим команд VI: `<T>`</span><span class="sxs-lookup"><span data-stu-id="7846e-807">Vi command mode: `<T>`</span></span>

### <a name="searchcharwithbackoff"></a><span data-ttu-id="7846e-808">сеарччарвисбаккофф</span><span class="sxs-lookup"><span data-stu-id="7846e-808">SearchCharWithBackoff</span></span>

<span data-ttu-id="7846e-809">Прочитать следующий символ, затем найти его, перейти вперед, а затем отследить символ.</span><span class="sxs-lookup"><span data-stu-id="7846e-809">Read the next character and then find it, going forward, and then back off a character.</span></span> <span data-ttu-id="7846e-810">Это относится к функциональным возможностям.</span><span class="sxs-lookup"><span data-stu-id="7846e-810">This is for 't' functionality.</span></span>

- <span data-ttu-id="7846e-811">Режим команд VI: `<t>`</span><span class="sxs-lookup"><span data-stu-id="7846e-811">Vi command mode: `<t>`</span></span>

### <a name="searchforward"></a><span data-ttu-id="7846e-812">сеарчфорвард</span><span class="sxs-lookup"><span data-stu-id="7846e-812">SearchForward</span></span>

<span data-ttu-id="7846e-813">Запрашивает строку поиска и инициирует поиск по запросу Акцептлине.</span><span class="sxs-lookup"><span data-stu-id="7846e-813">Prompts for a search string and initiates search upon AcceptLine.</span></span>

- <span data-ttu-id="7846e-814">Режим вставки в VI: `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="7846e-814">Vi insert mode: `<Ctrl+s>`</span></span>
- <span data-ttu-id="7846e-815">Режим команд VI: `<?>` , `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="7846e-815">Vi command mode: `<?>`, `<Ctrl+s>`</span></span>

## <a name="custom-key-bindings"></a><span data-ttu-id="7846e-816">Пользовательские привязки клавиш</span><span class="sxs-lookup"><span data-stu-id="7846e-816">Custom Key Bindings</span></span>

<span data-ttu-id="7846e-817">PSReadLine поддерживает пользовательские привязки клавиш с помощью командлета `Set-PSReadLineKeyHandler` .</span><span class="sxs-lookup"><span data-stu-id="7846e-817">PSReadLine supports custom key bindings using the cmdlet `Set-PSReadLineKeyHandler`.</span></span> <span data-ttu-id="7846e-818">Большинство пользовательских привязок вызывают одну из приведенных выше функций, например</span><span class="sxs-lookup"><span data-stu-id="7846e-818">Most custom key bindings call one of the above functions, for example</span></span>

```powershell
Set-PSReadLineKeyHandler -Key UpArrow -Function HistorySearchBackward
```

<span data-ttu-id="7846e-819">Можно привязать ScriptBlock к ключу.</span><span class="sxs-lookup"><span data-stu-id="7846e-819">You can bind a ScriptBlock to a key.</span></span> <span data-ttu-id="7846e-820">Блок ScriptBlock может выполнять практически все необходимые действия.</span><span class="sxs-lookup"><span data-stu-id="7846e-820">The ScriptBlock can do pretty much anything you want.</span></span> <span data-ttu-id="7846e-821">Ниже приведены некоторые полезные примеры.</span><span class="sxs-lookup"><span data-stu-id="7846e-821">Some useful examples include</span></span>

- <span data-ttu-id="7846e-822">Изменение командной строки</span><span class="sxs-lookup"><span data-stu-id="7846e-822">edit the command line</span></span>
- <span data-ttu-id="7846e-823">Открытие нового окна (например, Справка)</span><span class="sxs-lookup"><span data-stu-id="7846e-823">opening a new window (e.g. help)</span></span>
- <span data-ttu-id="7846e-824">Изменение каталогов без изменения командной строки</span><span class="sxs-lookup"><span data-stu-id="7846e-824">change directories without changing the command line</span></span>

<span data-ttu-id="7846e-825">Блок ScriptBlock получает два аргумента:</span><span class="sxs-lookup"><span data-stu-id="7846e-825">The ScriptBlock receives two arguments:</span></span>

- <span data-ttu-id="7846e-826">`$key` — Объект **[консолекэйинфо]** , который является ключом, запускающим пользовательскую привязку.</span><span class="sxs-lookup"><span data-stu-id="7846e-826">`$key` - A **[ConsoleKeyInfo]** object that is the key that triggered the custom binding.</span></span> <span data-ttu-id="7846e-827">Если один и тот же блок сценария привязан к нескольким ключам и необходимо выполнять различные действия в зависимости от ключа, можно проверить $key.</span><span class="sxs-lookup"><span data-stu-id="7846e-827">If you bind the same ScriptBlock to multiple keys and need to perform different actions depending on the key, you can check $key.</span></span> <span data-ttu-id="7846e-828">Многие пользовательские привязки игнорируют этот аргумент.</span><span class="sxs-lookup"><span data-stu-id="7846e-828">Many custom bindings ignore this argument.</span></span>

- <span data-ttu-id="7846e-829">`$arg` — Произвольный аргумент.</span><span class="sxs-lookup"><span data-stu-id="7846e-829">`$arg` - An arbitrary argument.</span></span> <span data-ttu-id="7846e-830">Чаще всего это будет целочисленный аргумент, который пользователь передает из ключевых привязок Дигитаргумент.</span><span class="sxs-lookup"><span data-stu-id="7846e-830">Most often, this would be an integer argument that the user passes from the key bindings DigitArgument.</span></span> <span data-ttu-id="7846e-831">Если привязка не принимает аргументы, целесообразно проигнорировать этот аргумент.</span><span class="sxs-lookup"><span data-stu-id="7846e-831">If your binding doesn't accept arguments, it's reasonable to ignore this argument.</span></span>

<span data-ttu-id="7846e-832">Рассмотрим пример, который добавляет в журнал командную строку, не выполняя ее.</span><span class="sxs-lookup"><span data-stu-id="7846e-832">Let's take a look at an example that adds a command line to history without executing it.</span></span> <span data-ttu-id="7846e-833">Это полезно, если вы забыли сделать что-то, но не хотите повторно вводить уже введенную командную строку.</span><span class="sxs-lookup"><span data-stu-id="7846e-833">This is useful when you realize you forgot to do something, but don't want to re-enter the command line you've already entered.</span></span>

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

<span data-ttu-id="7846e-834">В файле, `SamplePSReadLineProfile.ps1` который устанавливается в папку модуля PSReadLine, можно увидеть много других примеров.</span><span class="sxs-lookup"><span data-stu-id="7846e-834">You can see many more examples in the file `SamplePSReadLineProfile.ps1` which is installed in the PSReadLine module folder.</span></span>

<span data-ttu-id="7846e-835">Большинство ключевых привязок используют некоторые вспомогательные функции для редактирования командной строки.</span><span class="sxs-lookup"><span data-stu-id="7846e-835">Most key bindings use some helper functions for editing the command line.</span></span>
<span data-ttu-id="7846e-836">Эти API-интерфейсы описаны в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="7846e-836">Those APIs are documented in the next section.</span></span>

## <a name="custom-key-binding-support-apis"></a><span data-ttu-id="7846e-837">API поддержки пользовательского сочетания клавиш</span><span class="sxs-lookup"><span data-stu-id="7846e-837">Custom Key Binding Support APIs</span></span>

<span data-ttu-id="7846e-838">Следующие функции являются открытыми в Microsoft. PowerShell. Псконсолереадлине, но не могут быть напрямую привязаны к ключу.</span><span class="sxs-lookup"><span data-stu-id="7846e-838">The following functions are public in Microsoft.PowerShell.PSConsoleReadLine, but cannot be directly bound to a key.</span></span> <span data-ttu-id="7846e-839">Большинство из них удобно использовать в пользовательских привязках клавиш.</span><span class="sxs-lookup"><span data-stu-id="7846e-839">Most are useful in custom key bindings.</span></span>

```csharp
void AddToHistory(string command)
```

<span data-ttu-id="7846e-840">Добавьте командную строку в журнал, не выполняя ее.</span><span class="sxs-lookup"><span data-stu-id="7846e-840">Add a command line to history without executing it.</span></span>

```csharp
void ClearKillRing()
```

<span data-ttu-id="7846e-841">Снимите флажок Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="7846e-841">Clear the kill-ring.</span></span>  <span data-ttu-id="7846e-842">Это в основном используется для тестирования.</span><span class="sxs-lookup"><span data-stu-id="7846e-842">This is mostly used for testing.</span></span>

```csharp
void Delete(int start, int length)
```

<span data-ttu-id="7846e-843">Удалить символы длины из Start.</span><span class="sxs-lookup"><span data-stu-id="7846e-843">Delete length characters from start.</span></span>  <span data-ttu-id="7846e-844">Эта операция поддерживает операцию отмены и повтора.</span><span class="sxs-lookup"><span data-stu-id="7846e-844">This operation supports undo/redo.</span></span>

```csharp
void Ding()
```

<span data-ttu-id="7846e-845">Выполните действие DING, основанное на предпочтениях пользователей.</span><span class="sxs-lookup"><span data-stu-id="7846e-845">Perform the Ding action based on the users preference.</span></span>

```csharp
void GetBufferState([ref] string input, [ref] int cursor)
void GetBufferState([ref] Ast ast, [ref] Token[] tokens,
  [ref] ParseError[] parseErrors, [ref] int cursor)
```

<span data-ttu-id="7846e-846">Эти две функции извлекают полезную информацию о текущем состоянии входного буфера.</span><span class="sxs-lookup"><span data-stu-id="7846e-846">These two functions retrieve useful information about the current state of the input buffer.</span></span>  <span data-ttu-id="7846e-847">Первый из них чаще всего используется в простых случаях.</span><span class="sxs-lookup"><span data-stu-id="7846e-847">The first is more commonly used for simple cases.</span></span>  <span data-ttu-id="7846e-848">Второй используется, если привязка делает что-то более сложное с AST.</span><span class="sxs-lookup"><span data-stu-id="7846e-848">The second is used if your binding is doing something more advanced with the Ast.</span></span>

```csharp
IEnumerable[Microsoft.PowerShell.KeyHandler]
  GetKeyHandlers(bool includeBound, bool includeUnbound)

IEnumerable[Microsoft.PowerShell.KeyHandler]
  GetKeyHandlers(string[] Chord)
```

<span data-ttu-id="7846e-849">Эти две функции используются `Get-PSReadLineKeyHandler` .</span><span class="sxs-lookup"><span data-stu-id="7846e-849">These two functions are used by `Get-PSReadLineKeyHandler`.</span></span> <span data-ttu-id="7846e-850">Первый используется для получения всех привязок клавиш.</span><span class="sxs-lookup"><span data-stu-id="7846e-850">The first is used to get all key bindings.</span></span> <span data-ttu-id="7846e-851">Второй используется для получения конкретных привязок клавиш.</span><span class="sxs-lookup"><span data-stu-id="7846e-851">The second is used to get specific key bindings.</span></span>

```csharp
Microsoft.PowerShell.PSConsoleReadLineOptions GetOptions()
```

<span data-ttu-id="7846e-852">Эта функция используется Get-PSReadLineOption и, возможно, не слишком полезна в пользовательской привязке ключа.</span><span class="sxs-lookup"><span data-stu-id="7846e-852">This function is used by Get-PSReadLineOption and probably isn't too useful in a custom key binding.</span></span>

```csharp
void GetSelectionState([ref] int start, [ref] int length)
```

<span data-ttu-id="7846e-853">Если в командной строке ничего не выбрано, значение-1 будет возвращено как в начале, так и в длине.</span><span class="sxs-lookup"><span data-stu-id="7846e-853">If there is no selection on the command line, -1 will be returned in both start and length.</span></span> <span data-ttu-id="7846e-854">Если в командной строке имеется выделенный фрагмент, то начинается и длина выбора возвращается.</span><span class="sxs-lookup"><span data-stu-id="7846e-854">If there is a selection on the command line, the start and length of the selection are returned.</span></span>

```csharp
void Insert(char c)
void Insert(string s)
```

<span data-ttu-id="7846e-855">Вставка символа или строки в курсоре.</span><span class="sxs-lookup"><span data-stu-id="7846e-855">Insert a character or string at the cursor.</span></span>  <span data-ttu-id="7846e-856">Эта операция поддерживает операцию отмены и повтора.</span><span class="sxs-lookup"><span data-stu-id="7846e-856">This operation supports undo/redo.</span></span>

```csharp
string ReadLine(runspace remoteRunspace,
  System.Management.Automation.EngineIntrinsics engineIntrinsics)
```

<span data-ttu-id="7846e-857">Это Главная точка входа для PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="7846e-857">This is the main entry point to PSReadLine.</span></span> <span data-ttu-id="7846e-858">Она не поддерживает рекурсию, поэтому она не полезна в пользовательской привязке ключа.</span><span class="sxs-lookup"><span data-stu-id="7846e-858">It does not support recursion, so is not useful in a custom key binding.</span></span>

```csharp
void RemoveKeyHandler(string[] key)
```

<span data-ttu-id="7846e-859">Эта функция используется Remove-PSReadLineKeyHandler и, возможно, не слишком полезна в пользовательской привязке ключа.</span><span class="sxs-lookup"><span data-stu-id="7846e-859">This function is used by Remove-PSReadLineKeyHandler and probably isn't too useful in a custom key binding.</span></span>

```csharp
void Replace(int start, int length, string replacement)
```

<span data-ttu-id="7846e-860">Замените некоторые входные данные.</span><span class="sxs-lookup"><span data-stu-id="7846e-860">Replace some of the input.</span></span> <span data-ttu-id="7846e-861">Эта операция поддерживает операцию отмены и повтора.</span><span class="sxs-lookup"><span data-stu-id="7846e-861">This operation supports undo/redo.</span></span> <span data-ttu-id="7846e-862">Это предпочтительнее удаление с последующим вставкой, так как оно обрабатывается как одно действие для отмены.</span><span class="sxs-lookup"><span data-stu-id="7846e-862">This is preferred over Delete followed by Insert because it is treated as a single action for undo.</span></span>

```csharp
void SetCursorPosition(int cursor)
```

<span data-ttu-id="7846e-863">Переместить курсор к заданному смещению.</span><span class="sxs-lookup"><span data-stu-id="7846e-863">Move the cursor to the given offset.</span></span> <span data-ttu-id="7846e-864">Перемещение курсора не ведется для отмены.</span><span class="sxs-lookup"><span data-stu-id="7846e-864">Cursor movement is not tracked for undo.</span></span>

```csharp
void SetOptions(Microsoft.PowerShell.SetPSReadLineOption options)
```

<span data-ttu-id="7846e-865">Эта функция является вспомогательным методом, используемым командлетом Set-PSReadLineOption, но может быть полезен для пользовательской привязки ключа, которая хочет временно изменить параметр.</span><span class="sxs-lookup"><span data-stu-id="7846e-865">This function is a helper method used by the cmdlet Set-PSReadLineOption, but might be useful to a custom key binding that wants to temporarily change a setting.</span></span>

```csharp
bool TryGetArgAsInt(System.Object arg, [ref] int numericArg,
  int defaultNumericArg)
```

<span data-ttu-id="7846e-866">Этот вспомогательный метод используется для пользовательских привязок, которые учитывают Дигитаргумент.</span><span class="sxs-lookup"><span data-stu-id="7846e-866">This helper method is used for custom bindings that honor DigitArgument.</span></span> <span data-ttu-id="7846e-867">Обычный вызов выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="7846e-867">A typical call looks like</span></span>

```powershell
[int]$numericArg = 0
[Microsoft.PowerShell.PSConsoleReadLine]::TryGetArgAsInt($arg,
  [ref]$numericArg, 1)
```

## <a name="note"></a><span data-ttu-id="7846e-868">Примечание</span><span class="sxs-lookup"><span data-stu-id="7846e-868">Note</span></span>

### <a name="command-history"></a><span data-ttu-id="7846e-869">Журнал команд</span><span class="sxs-lookup"><span data-stu-id="7846e-869">Command History</span></span>

<span data-ttu-id="7846e-870">PSReadLine поддерживает файл журнала, содержащий все команды и данные, введенные из командной строки.</span><span class="sxs-lookup"><span data-stu-id="7846e-870">PSReadLine maintains a history file containing all the commands and data you have entered from the command line.</span></span> <span data-ttu-id="7846e-871">Это может быть конфиденциальные данные, включая пароли.</span><span class="sxs-lookup"><span data-stu-id="7846e-871">This may contain sensitive data including passwords.</span></span> <span data-ttu-id="7846e-872">Например, при использовании `ConvertTo-SecureString` командлета пароль заносится в файл журнала в виде обычного текста.</span><span class="sxs-lookup"><span data-stu-id="7846e-872">For example, if you use the `ConvertTo-SecureString` cmdlet the password is logged in the history file as plain text.</span></span> <span data-ttu-id="7846e-873">Файлы журнала — это файл с именем `$($host.Name)_history.txt` .</span><span class="sxs-lookup"><span data-stu-id="7846e-873">The history files is a file named `$($host.Name)_history.txt`.</span></span> <span data-ttu-id="7846e-874">В системах Windows файл журнала хранится в файле `$env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine` .</span><span class="sxs-lookup"><span data-stu-id="7846e-874">On Windows systems the history file is stored at `$env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine`.</span></span> <span data-ttu-id="7846e-875">В системах, отличных от Windows, файлы журнала хранятся в `$env:XDG_DATA_HOME/powershell/PSReadLine` или `$env:HOME/.local/share/powershell/PSReadLine` .</span><span class="sxs-lookup"><span data-stu-id="7846e-875">On non-Windows systems, the history files is stored at `$env:XDG_DATA_HOME/powershell/PSReadLine` or `$env:HOME/.local/share/powershell/PSReadLine`.</span></span>

### <a name="feedback--contributing-to-psreadline"></a><span data-ttu-id="7846e-876">Обратная связь & участие в PSReadLine</span><span class="sxs-lookup"><span data-stu-id="7846e-876">Feedback & Contributing To PSReadLine</span></span>

[<span data-ttu-id="7846e-877">PSReadLine на GitHub</span><span class="sxs-lookup"><span data-stu-id="7846e-877">PSReadLine on GitHub</span></span>](https://github.com/PowerShell/PSReadLine)

<span data-ttu-id="7846e-878">Вы можете отправить запрос на вытягивание или отправить отзыв на страницу GitHub.</span><span class="sxs-lookup"><span data-stu-id="7846e-878">Feel free to submit a pull request or submit feedback on the GitHub page.</span></span>

## <a name="see-also"></a><span data-ttu-id="7846e-879">См. также:</span><span class="sxs-lookup"><span data-stu-id="7846e-879">See Also</span></span>

<span data-ttu-id="7846e-880">На PSReadLine сильно влияют библиотеки GNU [ReadLine](https://tiswww.case.edu/php/chet/readline/rltop.html) .</span><span class="sxs-lookup"><span data-stu-id="7846e-880">PSReadLine is heavily influenced by the GNU [readline](https://tiswww.case.edu/php/chet/readline/rltop.html) library.</span></span>
