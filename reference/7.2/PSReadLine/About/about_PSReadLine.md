---
description: PSReadLine предоставляет улучшенные возможности редактирования командной строки в консоли PowerShell.
Locale: en-US
ms.date: 11/23/2020
online version: https://docs.microsoft.com/powershell/module/psreadline/about/about_psreadline?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: О PSReadLine
ms.openlocfilehash: b0c5950b2af6a866d0ffcfdd6ce7ad92a1763778
ms.sourcegitcommit: 77f6225ab0c8ea9faa1fe46b2ea15c178ec170e3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100500218"
---
# <a name="psreadline"></a><span data-ttu-id="f55fd-103">PSReadLine</span><span class="sxs-lookup"><span data-stu-id="f55fd-103">PSReadLine</span></span>

## <a name="about_psreadline"></a><span data-ttu-id="f55fd-104">about_PSReadLine</span><span class="sxs-lookup"><span data-stu-id="f55fd-104">about_PSReadLine</span></span>

## <a name="short-description"></a><span data-ttu-id="f55fd-105">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="f55fd-105">Short Description</span></span>

<span data-ttu-id="f55fd-106">PSReadLine предоставляет улучшенные возможности редактирования командной строки в консоли PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f55fd-106">PSReadLine provides an improved command-line editing experience in the PowerShell console.</span></span>

## <a name="long-description"></a><span data-ttu-id="f55fd-107">Полное описание</span><span class="sxs-lookup"><span data-stu-id="f55fd-107">Long Description</span></span>

<span data-ttu-id="f55fd-108">PSReadLine 2,2 предоставляет широкие возможности редактирования командной строки для консоли PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f55fd-108">PSReadLine 2.2 provides a powerful command-line editing experience for the PowerShell console.</span></span> <span data-ttu-id="f55fd-109">Консоль предоставляет следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="f55fd-109">It provides:</span></span>

- <span data-ttu-id="f55fd-110">Цветовое выделение синтаксиса командной строки</span><span class="sxs-lookup"><span data-stu-id="f55fd-110">Syntax coloring of the command line</span></span>
- <span data-ttu-id="f55fd-111">Визуальное обозначение синтаксических ошибок</span><span class="sxs-lookup"><span data-stu-id="f55fd-111">A visual indication of syntax errors</span></span>
- <span data-ttu-id="f55fd-112">Более эффективный многострочный интерфейс (как редактирование, так и журнал)</span><span class="sxs-lookup"><span data-stu-id="f55fd-112">A better multi-line experience (both editing and history)</span></span>
- <span data-ttu-id="f55fd-113">Настраиваемые сочетания клавиш</span><span class="sxs-lookup"><span data-stu-id="f55fd-113">Customizable key bindings</span></span>
- <span data-ttu-id="f55fd-114">Режимы работы cmd и Emacs</span><span class="sxs-lookup"><span data-stu-id="f55fd-114">Cmd and Emacs modes</span></span>
- <span data-ttu-id="f55fd-115">Множество параметров конфигурации</span><span class="sxs-lookup"><span data-stu-id="f55fd-115">Many configuration options</span></span>
- <span data-ttu-id="f55fd-116">Завершение стиля bash (необязательно в режиме cmd, по умолчанию в режиме Emacs)</span><span class="sxs-lookup"><span data-stu-id="f55fd-116">Bash style completion (optional in Cmd mode, default in Emacs mode)</span></span>
- <span data-ttu-id="f55fd-117">Emacs: Янк/Kill-Ring</span><span class="sxs-lookup"><span data-stu-id="f55fd-117">Emacs yank/kill-ring</span></span>
- <span data-ttu-id="f55fd-118">Перемещение и уничтожение токена PowerShell на основе маркеров "Word"</span><span class="sxs-lookup"><span data-stu-id="f55fd-118">PowerShell token based "word" movement and kill</span></span>
- <span data-ttu-id="f55fd-119">Прогнозирование IntelliSense</span><span class="sxs-lookup"><span data-stu-id="f55fd-119">Predictive IntelliSense</span></span>

<span data-ttu-id="f55fd-120">PSReadLine 2.2.0 добавил две новые функции прогнозной IntelliSense:</span><span class="sxs-lookup"><span data-stu-id="f55fd-120">PSReadLine 2.2.0 added two new predictive IntelliSense features:</span></span>

- <span data-ttu-id="f55fd-121">Добавлен параметр **предиктионвиевстиле** , позволяющий выбрать новый объект `ListView` .</span><span class="sxs-lookup"><span data-stu-id="f55fd-121">Added the **PredictionViewStyle** parameter to allow for the selection of the new `ListView`.</span></span>
- <span data-ttu-id="f55fd-122">Подключение PSReadLine к `CommandPrediction` API-интерфейсам, появившимся в PS 7,1, чтобы разрешить пользователю импортировать модуль прогнозирования, который может отображать предложения из пользовательского источника.</span><span class="sxs-lookup"><span data-stu-id="f55fd-122">Connected PSReadLine to the `CommandPrediction` APIs introduced in PS 7.1 to allow a user can import a predictor module that can render the suggestions from a custom source.</span></span>

<span data-ttu-id="f55fd-123">Для PSReadLine требуется PowerShell 3,0 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="f55fd-123">PSReadLine requires PowerShell 3.0, or newer.</span></span> <span data-ttu-id="f55fd-124">PSReadLine работает с узлом консоли по умолчанию, Visual Studio Code и окном терминала.</span><span class="sxs-lookup"><span data-stu-id="f55fd-124">PSReadLine works with default console host, Visual Studio Code, and Window Terminal.</span></span> <span data-ttu-id="f55fd-125">Он не работает в интегрированной среде сценариев PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f55fd-125">It does not work in PowerShell ISE.</span></span>

<span data-ttu-id="f55fd-126">PSReadLine 2.2.0 поставляется с PowerShell 7,2 и поддерживается во всех поддерживаемых версиях PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f55fd-126">PSReadLine 2.2.0 ships with PowerShell 7.2 and is supported in all supported versions of PowerShell.</span></span> <span data-ttu-id="f55fd-127">Его можно установить из коллекция PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f55fd-127">It is available to install from the PowerShell Gallery.</span></span>
<span data-ttu-id="f55fd-128">Чтобы установить PSReadLine 2.2.0 в поддерживаемой версии PowerShell, выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="f55fd-128">To install PSReadLine 2.2.0 in a supported version of PowerShell run the following command.</span></span>

```powershell
Install-Module -Name PSReadLine -AllowPrerelease
```

> [!NOTE]
> <span data-ttu-id="f55fd-129">Начиная с PowerShell 7,0, PowerShell пропускает автоматическую загрузку PSReadLine в Windows при обнаружении программы чтения с экрана.</span><span class="sxs-lookup"><span data-stu-id="f55fd-129">Beginning with PowerShell 7.0, PowerShell skips auto-loading PSReadLine on Windows if a screen reader program is detected.</span></span> <span data-ttu-id="f55fd-130">В настоящее время PSReadLine плохо работает с программами чтения с экрана.</span><span class="sxs-lookup"><span data-stu-id="f55fd-130">Currently, PSReadLine doesn't work well with the screen readers.</span></span> <span data-ttu-id="f55fd-131">Визуализация и форматирование по умолчанию для PowerShell 7,0 в Windows работают правильно.</span><span class="sxs-lookup"><span data-stu-id="f55fd-131">The default rendering and formatting of PowerShell 7.0 on Windows works properly.</span></span> <span data-ttu-id="f55fd-132">При необходимости модуль можно загрузить вручную.</span><span class="sxs-lookup"><span data-stu-id="f55fd-132">You can manually load the module if necessary.</span></span>

## <a name="predictive-intellisense"></a><span data-ttu-id="f55fd-133">Прогнозирование IntelliSense</span><span class="sxs-lookup"><span data-stu-id="f55fd-133">Predictive IntelliSense</span></span>

<span data-ttu-id="f55fd-134">Прогнозная IntelliSense является дополнением к концепции заполнения нажатием клавиши TAB, которая помогает пользователю успешно завершать команды.</span><span class="sxs-lookup"><span data-stu-id="f55fd-134">Predictive IntelliSense is an addition to the concept of tab completion that assists the user in successfully completing commands.</span></span> <span data-ttu-id="f55fd-135">Она позволяет пользователям обнаруживать, изменять и выполнять полные команды на основе прогнозов, находящихся в истории пользователя, и дополнительных подключаемых модулей для конкретных доменов.</span><span class="sxs-lookup"><span data-stu-id="f55fd-135">It enables users to discover, edit, and execute full commands based on matching predictions from the user's history and additional domain specific plugins.</span></span>

### <a name="enable-predictive-intellisense"></a><span data-ttu-id="f55fd-136">Включение прогнозного IntelliSense</span><span class="sxs-lookup"><span data-stu-id="f55fd-136">Enable Predictive IntelliSense</span></span>

<span data-ttu-id="f55fd-137">По умолчанию прогнозная технология IntelliSense отключена.</span><span class="sxs-lookup"><span data-stu-id="f55fd-137">Predictive IntelliSense is disabled by default.</span></span> <span data-ttu-id="f55fd-138">Чтобы включить прогнозы, просто выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="f55fd-138">To enable predictions, just run the following command:</span></span>

```powershell
Set-PSReadLineOption -PredictionSource History
```

<span data-ttu-id="f55fd-139">Параметр **предиктионсаурце** также может принимать подключаемые модули для конкретных требований, связанных с доменами, и пользовательскими требованиями.</span><span class="sxs-lookup"><span data-stu-id="f55fd-139">The **PredictionSource** parameter can also accept plugins for domain specific and custom requirements.</span></span>

<span data-ttu-id="f55fd-140">Чтобы отключить прогнозную IntelliSense, просто выполните команду:</span><span class="sxs-lookup"><span data-stu-id="f55fd-140">To disable Predictive IntelliSense, just run:</span></span>

```powershell
Set-PSReadLineOption -PredictionSource None
```

<span data-ttu-id="f55fd-141">В классе **[Microsoft. PowerShell. псконсолереадлине]** доступны следующие функции.</span><span class="sxs-lookup"><span data-stu-id="f55fd-141">The following functions are available in the class **[Microsoft.PowerShell.PSConsoleReadLine]**.</span></span>

## <a name="basic-editing-functions"></a><span data-ttu-id="f55fd-142">Базовые функции редактирования</span><span class="sxs-lookup"><span data-stu-id="f55fd-142">Basic editing functions</span></span>

### <a name="abort"></a><span data-ttu-id="f55fd-143">Прервать</span><span class="sxs-lookup"><span data-stu-id="f55fd-143">Abort</span></span>

<span data-ttu-id="f55fd-144">Прервать текущее действие, например добавочный поиск по журналу.</span><span class="sxs-lookup"><span data-stu-id="f55fd-144">Abort current action, e.g. incremental history search.</span></span>

- <span data-ttu-id="f55fd-145">Emacs: `<Ctrl+g>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-145">Emacs: `<Ctrl+g>`</span></span>

### <a name="acceptandgetnext"></a><span data-ttu-id="f55fd-146">акцептанджетнекст</span><span class="sxs-lookup"><span data-stu-id="f55fd-146">AcceptAndGetNext</span></span>

<span data-ttu-id="f55fd-147">Попытка выполнить текущий вход.</span><span class="sxs-lookup"><span data-stu-id="f55fd-147">Attempt to execute the current input.</span></span> <span data-ttu-id="f55fd-148">Если его можно выполнить (например, Акцептлине), то следует отозвать следующий элемент из журнала при следующем вызове метода ReadLine.</span><span class="sxs-lookup"><span data-stu-id="f55fd-148">If it can be executed (like AcceptLine), then recall the next item from history the next time ReadLine is called.</span></span>

- <span data-ttu-id="f55fd-149">Emacs: `<Ctrl+o>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-149">Emacs: `<Ctrl+o>`</span></span>

### <a name="acceptline"></a><span data-ttu-id="f55fd-150">акцептлине</span><span class="sxs-lookup"><span data-stu-id="f55fd-150">AcceptLine</span></span>

<span data-ttu-id="f55fd-151">Попытка выполнить текущий вход.</span><span class="sxs-lookup"><span data-stu-id="f55fd-151">Attempt to execute the current input.</span></span> <span data-ttu-id="f55fd-152">Если текущий ввод неполон (например, отсутствует закрывающая круглая скобка, квадратная скобка или кавычка, запрос продолжения отображается на следующей строке, а PSReadLine ожидает ввода ключей для изменения текущих входных данных.</span><span class="sxs-lookup"><span data-stu-id="f55fd-152">If the current input is incomplete (for example there is a missing closing parenthesis, bracket, or quote, then the continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span>

- <span data-ttu-id="f55fd-153">Процессор `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-153">Cmd: `<Enter>`</span></span>
- <span data-ttu-id="f55fd-154">Emacs: `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-154">Emacs: `<Enter>`</span></span>
- <span data-ttu-id="f55fd-155">Режим вставки в VI: `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-155">Vi insert mode: `<Enter>`</span></span>

### <a name="addline"></a><span data-ttu-id="f55fd-156">аддлине</span><span class="sxs-lookup"><span data-stu-id="f55fd-156">AddLine</span></span>

<span data-ttu-id="f55fd-157">Запрос продолжения отображается на следующей строке, а PSReadLine ожидает ввода ключей для изменения текущих входных данных.</span><span class="sxs-lookup"><span data-stu-id="f55fd-157">The continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span> <span data-ttu-id="f55fd-158">Это полезно для ввода многострочных входных данных в виде одной команды, даже если одна строка завершается самим вводом.</span><span class="sxs-lookup"><span data-stu-id="f55fd-158">This is useful to enter multi-line input as a single command even when a single line is complete input by itself.</span></span>

- <span data-ttu-id="f55fd-159">Процессор `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-159">Cmd: `<Shift+Enter>`</span></span>
- <span data-ttu-id="f55fd-160">Emacs: `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-160">Emacs: `<Shift+Enter>`</span></span>
- <span data-ttu-id="f55fd-161">Режим вставки в VI: `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-161">Vi insert mode: `<Shift+Enter>`</span></span>
- <span data-ttu-id="f55fd-162">Режим команд VI: `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-162">Vi command mode: `<Shift+Enter>`</span></span>

### <a name="backwarddeletechar"></a><span data-ttu-id="f55fd-163">бакквардделетечар</span><span class="sxs-lookup"><span data-stu-id="f55fd-163">BackwardDeleteChar</span></span>

<span data-ttu-id="f55fd-164">Удалить символ перед курсором.</span><span class="sxs-lookup"><span data-stu-id="f55fd-164">Delete the character before the cursor.</span></span>

- <span data-ttu-id="f55fd-165">Cmd: `<Backspace>` , `<Ctrl+h>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-165">Cmd: `<Backspace>`, `<Ctrl+h>`</span></span>
- <span data-ttu-id="f55fd-166">Emacs: `<Backspace>` , `<Ctrl+Backspace>` , `<Ctrl+h>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-166">Emacs: `<Backspace>`, `<Ctrl+Backspace>`, `<Ctrl+h>`</span></span>
- <span data-ttu-id="f55fd-167">Режим вставки в VI: `<Backspace>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-167">Vi insert mode: `<Backspace>`</span></span>
- <span data-ttu-id="f55fd-168">Режим команд VI: `<X>` , `<d,h>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-168">Vi command mode: `<X>`, `<d,h>`</span></span>

### <a name="backwarddeleteline"></a><span data-ttu-id="f55fd-169">бакквардделетелине</span><span class="sxs-lookup"><span data-stu-id="f55fd-169">BackwardDeleteLine</span></span>

<span data-ttu-id="f55fd-170">Like Бакквардкилллине — удаляет текст с точки до начала строки, но не помещает удаленный текст в инструкцию KILL-Ring.</span><span class="sxs-lookup"><span data-stu-id="f55fd-170">Like BackwardKillLine - deletes text from the point to the start of the line, but does not put the deleted text in the kill-ring.</span></span>

- <span data-ttu-id="f55fd-171">Процессор `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-171">Cmd: `<Ctrl+Home>`</span></span>
- <span data-ttu-id="f55fd-172">Режим вставки в VI: `<Ctrl+u>` , `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-172">Vi insert mode: `<Ctrl+u>`, `<Ctrl+Home>`</span></span>
- <span data-ttu-id="f55fd-173">Режим команд VI: `<Ctrl+u>` , `<Ctrl+Home>` , `<d,0>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-173">Vi command mode: `<Ctrl+u>`, `<Ctrl+Home>`, `<d,0>`</span></span>

### <a name="backwarddeleteword"></a><span data-ttu-id="f55fd-174">бакквардделетеворд</span><span class="sxs-lookup"><span data-stu-id="f55fd-174">BackwardDeleteWord</span></span>

<span data-ttu-id="f55fd-175">Удаляет предыдущее слово.</span><span class="sxs-lookup"><span data-stu-id="f55fd-175">Deletes the previous word.</span></span>

- <span data-ttu-id="f55fd-176">Режим команд VI: `<Ctrl+w>` , `<d,b>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-176">Vi command mode: `<Ctrl+w>`, `<d,b>`</span></span>

### <a name="backwardkillline"></a><span data-ttu-id="f55fd-177">бакквардкилллине</span><span class="sxs-lookup"><span data-stu-id="f55fd-177">BackwardKillLine</span></span>

<span data-ttu-id="f55fd-178">Очистить входные данные от начала ввода до курсора.</span><span class="sxs-lookup"><span data-stu-id="f55fd-178">Clear the input from the start of the input to the cursor.</span></span> <span data-ttu-id="f55fd-179">Очистка текста помещается в буфер Kill.</span><span class="sxs-lookup"><span data-stu-id="f55fd-179">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="f55fd-180">Emacs: `<Ctrl+u>` , `<Ctrl+x,Backspace>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-180">Emacs: `<Ctrl+u>`, `<Ctrl+x,Backspace>`</span></span>

### <a name="backwardkillword"></a><span data-ttu-id="f55fd-181">бакквардкиллворд</span><span class="sxs-lookup"><span data-stu-id="f55fd-181">BackwardKillWord</span></span>

<span data-ttu-id="f55fd-182">Очистить ввод от начала текущего слова до курсора.</span><span class="sxs-lookup"><span data-stu-id="f55fd-182">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="f55fd-183">Если курсор находится между словами, входные данные очищаются от начала предыдущего слова до курсора.</span><span class="sxs-lookup"><span data-stu-id="f55fd-183">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="f55fd-184">Очистка текста помещается в буфер Kill.</span><span class="sxs-lookup"><span data-stu-id="f55fd-184">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="f55fd-185">Cmd: `<Ctrl+Backspace>` , `<Ctrl+w>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-185">Cmd: `<Ctrl+Backspace>`, `<Ctrl+w>`</span></span>
- <span data-ttu-id="f55fd-186">Emacs: `<Alt+Backspace>` , `<Escape,Backspace>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-186">Emacs: `<Alt+Backspace>`, `<Escape,Backspace>`</span></span>
- <span data-ttu-id="f55fd-187">Режим вставки в VI: `<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-187">Vi insert mode: `<Ctrl+Backspace>`</span></span>
- <span data-ttu-id="f55fd-188">Режим команд VI: `<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-188">Vi command mode: `<Ctrl+Backspace>`</span></span>

### <a name="cancelline"></a><span data-ttu-id="f55fd-189">канцеллине</span><span class="sxs-lookup"><span data-stu-id="f55fd-189">CancelLine</span></span>

<span data-ttu-id="f55fd-190">Отмена текущих входных данных с выходом на экран, но возврат к узлу, чтобы снова выполнить оценку запроса.</span><span class="sxs-lookup"><span data-stu-id="f55fd-190">Cancel the current input, leaving the input on the screen, but returns back to the host so the prompt is evaluated again.</span></span>

- <span data-ttu-id="f55fd-191">Режим вставки в VI: `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-191">Vi insert mode: `<Ctrl+c>`</span></span>
- <span data-ttu-id="f55fd-192">Режим команд VI: `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-192">Vi command mode: `<Ctrl+c>`</span></span>

### <a name="copy"></a><span data-ttu-id="f55fd-193">Копировать</span><span class="sxs-lookup"><span data-stu-id="f55fd-193">Copy</span></span>

<span data-ttu-id="f55fd-194">Копировать выбранный регион в буфер обмена системы.</span><span class="sxs-lookup"><span data-stu-id="f55fd-194">Copy selected region to the system clipboard.</span></span> <span data-ttu-id="f55fd-195">Если регион не выбран, скопируйте всю строку.</span><span class="sxs-lookup"><span data-stu-id="f55fd-195">If no region is selected, copy the whole line.</span></span>

- <span data-ttu-id="f55fd-196">Процессор `<Ctrl+C>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-196">Cmd: `<Ctrl+C>`</span></span>

### <a name="copyorcancelline"></a><span data-ttu-id="f55fd-197">копйорканцеллине</span><span class="sxs-lookup"><span data-stu-id="f55fd-197">CopyOrCancelLine</span></span>

<span data-ttu-id="f55fd-198">Если выбран текст, скопируйте в буфер обмена, в противном случае отмените строку.</span><span class="sxs-lookup"><span data-stu-id="f55fd-198">If text is selected, copy to the clipboard, otherwise cancel the line.</span></span>

- <span data-ttu-id="f55fd-199">Процессор `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-199">Cmd: `<Ctrl+c>`</span></span>
- <span data-ttu-id="f55fd-200">Emacs: `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-200">Emacs: `<Ctrl+c>`</span></span>

### <a name="cut"></a><span data-ttu-id="f55fd-201">Вырезать</span><span class="sxs-lookup"><span data-stu-id="f55fd-201">Cut</span></span>

<span data-ttu-id="f55fd-202">Удалить выбранный регион, поместив удаленный текст в системный буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="f55fd-202">Delete selected region placing deleted text in the system clipboard.</span></span>

- <span data-ttu-id="f55fd-203">Процессор `<Ctrl+x>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-203">Cmd: `<Ctrl+x>`</span></span>

### <a name="deletechar"></a><span data-ttu-id="f55fd-204">делетечар</span><span class="sxs-lookup"><span data-stu-id="f55fd-204">DeleteChar</span></span>

<span data-ttu-id="f55fd-205">Удалите символ под курсором.</span><span class="sxs-lookup"><span data-stu-id="f55fd-205">Delete the character under the cursor.</span></span>

- <span data-ttu-id="f55fd-206">Процессор `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-206">Cmd: `<Delete>`</span></span>
- <span data-ttu-id="f55fd-207">Emacs: `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-207">Emacs: `<Delete>`</span></span>
- <span data-ttu-id="f55fd-208">Режим вставки в VI: `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-208">Vi insert mode: `<Delete>`</span></span>
- <span data-ttu-id="f55fd-209">Режим команд VI: `<Delete>` , `<x>` , `<d,l>` , `<d,Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-209">Vi command mode: `<Delete>`, `<x>`, `<d,l>`, `<d,Spacebar>`</span></span>

### <a name="deletecharorexit"></a><span data-ttu-id="f55fd-210">делетечарорексит</span><span class="sxs-lookup"><span data-stu-id="f55fd-210">DeleteCharOrExit</span></span>

<span data-ttu-id="f55fd-211">Удалите символ под курсором или, если строка пуста, завершите процесс.</span><span class="sxs-lookup"><span data-stu-id="f55fd-211">Delete the character under the cursor, or if the line is empty, exit the process.</span></span>

- <span data-ttu-id="f55fd-212">Emacs: `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-212">Emacs: `<Ctrl+d>`</span></span>

### <a name="deleteendofbuffer"></a><span data-ttu-id="f55fd-213">делетиндофбуффер</span><span class="sxs-lookup"><span data-stu-id="f55fd-213">DeleteEndOfBuffer</span></span>

<span data-ttu-id="f55fd-214">Удаляет до конца многострочного буфера.</span><span class="sxs-lookup"><span data-stu-id="f55fd-214">Deletes to the end of the multiline buffer.</span></span>

- <span data-ttu-id="f55fd-215">Режим команд VI: `<d,G>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-215">Vi command mode: `<d,G>`</span></span>

### <a name="deleteendofword"></a><span data-ttu-id="f55fd-216">делетиндофворд</span><span class="sxs-lookup"><span data-stu-id="f55fd-216">DeleteEndOfWord</span></span>

<span data-ttu-id="f55fd-217">Удалить до конца слова.</span><span class="sxs-lookup"><span data-stu-id="f55fd-217">Delete to the end of the word.</span></span>

- <span data-ttu-id="f55fd-218">Режим команд VI: `<d,e>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-218">Vi command mode: `<d,e>`</span></span>

### <a name="deleteline"></a><span data-ttu-id="f55fd-219">Сбой deleteline</span><span class="sxs-lookup"><span data-stu-id="f55fd-219">DeleteLine</span></span>

<span data-ttu-id="f55fd-220">Удаляет текущую логическую строку многострочного буфера, включая отмену.</span><span class="sxs-lookup"><span data-stu-id="f55fd-220">Deletes the current logical line of a multiline buffer, enabling undo.</span></span>

- <span data-ttu-id="f55fd-221">Режим команд VI: `<d,d>` , `<d,_>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-221">Vi command mode: `<d,d>`, `<d,_>`</span></span>

### <a name="deletepreviouslines"></a><span data-ttu-id="f55fd-222">делетепревиауслинес</span><span class="sxs-lookup"><span data-stu-id="f55fd-222">DeletePreviousLines</span></span>

<span data-ttu-id="f55fd-223">Удаляет предыдущие запрошенные логические строки и текущую логическую строку в многострочном буфере.</span><span class="sxs-lookup"><span data-stu-id="f55fd-223">Deletes the previous requested logical lines and the current logical line in a multiline buffer.</span></span>

- <span data-ttu-id="f55fd-224">Режим команд VI: `<d,k>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-224">Vi command mode: `<d,k>`</span></span>

### <a name="deleterelativelines"></a><span data-ttu-id="f55fd-225">делетерелативелинес</span><span class="sxs-lookup"><span data-stu-id="f55fd-225">DeleteRelativeLines</span></span>

<span data-ttu-id="f55fd-226">Удаляет с начала буфера до текущей логической строки в многострочном буфере.</span><span class="sxs-lookup"><span data-stu-id="f55fd-226">Deletes from the beginning of the buffer to the current logical line in a multiline buffer.</span></span>

<span data-ttu-id="f55fd-227">Как и в большинстве команд VI, `<d,g,g>` команду можно добавить в начало с числовым аргументом, который указывает абсолютный номер строки, который вместе с текущим номером строки позволяет удалить диапазон строк.</span><span class="sxs-lookup"><span data-stu-id="f55fd-227">As most Vi commands, the `<d,g,g>` command can be prepended with a numeric argument that specifies an absolute line number, which, together with the current line number, make up a range of lines to be deleted.</span></span>
<span data-ttu-id="f55fd-228">Если не указано, числовой аргумент по умолчанию равен 1, что означает первую логическую строку в многострочном буфере.</span><span class="sxs-lookup"><span data-stu-id="f55fd-228">If not specified, the numeric argument defaults to 1, which refers to the first logical line in a multiline buffer.</span></span>

<span data-ttu-id="f55fd-229">Фактическое число строк, удаляемых из многострочного, вычисляются как разница между текущим логическим номером и заданным числовым аргументом, который, таким образом, может быть отрицательным.</span><span class="sxs-lookup"><span data-stu-id="f55fd-229">The actual number of lines to be deleted from the multiline is computed as the difference between the current logical line number and the specified numeric argument, which can thus be negative.</span></span> <span data-ttu-id="f55fd-230">Поэтому это _Относительная_ часть имени метода.</span><span class="sxs-lookup"><span data-stu-id="f55fd-230">Hence the _relative_ part of method name.</span></span>

- <span data-ttu-id="f55fd-231">Режим команд VI: `<d,g,g>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-231">Vi command mode: `<d,g,g>`</span></span>

### <a name="deletenextlines"></a><span data-ttu-id="f55fd-232">делетенекстлинес</span><span class="sxs-lookup"><span data-stu-id="f55fd-232">DeleteNextLines</span></span>

<span data-ttu-id="f55fd-233">Удаляет текущую логическую строку и следующие запрошенные логические строки в многострочном буфере.</span><span class="sxs-lookup"><span data-stu-id="f55fd-233">Deletes the current logical line and the next requested logical lines in a multiline buffer.</span></span>

- <span data-ttu-id="f55fd-234">Режим команд VI: `<d,j>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-234">Vi command mode: `<d,j>`</span></span>

### <a name="deletelinetofirstchar"></a><span data-ttu-id="f55fd-235">делетелинетофирстчар</span><span class="sxs-lookup"><span data-stu-id="f55fd-235">DeleteLineToFirstChar</span></span>

<span data-ttu-id="f55fd-236">Удаляет из первого непустого символа текущей логической строки в многострочном буфере.</span><span class="sxs-lookup"><span data-stu-id="f55fd-236">Deletes from the first non-blank character of the current logical line in a multiline buffer.</span></span>

- <span data-ttu-id="f55fd-237">Режим команд VI: `<d,^>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-237">Vi command mode: `<d,^>`</span></span>

### <a name="deletetoend"></a><span data-ttu-id="f55fd-238">делететоенд</span><span class="sxs-lookup"><span data-stu-id="f55fd-238">DeleteToEnd</span></span>

<span data-ttu-id="f55fd-239">Удалить до конца строки.</span><span class="sxs-lookup"><span data-stu-id="f55fd-239">Delete to the end of the line.</span></span>

- <span data-ttu-id="f55fd-240">Режим команд VI: `<D>` , `<d,$>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-240">Vi command mode: `<D>`, `<d,$>`</span></span>

### <a name="deleteword"></a><span data-ttu-id="f55fd-241">DeleteWord</span><span class="sxs-lookup"><span data-stu-id="f55fd-241">DeleteWord</span></span>

<span data-ttu-id="f55fd-242">Удалить следующее слово.</span><span class="sxs-lookup"><span data-stu-id="f55fd-242">Delete the next word.</span></span>

- <span data-ttu-id="f55fd-243">Режим команд VI: `<d,w>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-243">Vi command mode: `<d,w>`</span></span>

### <a name="forwarddeleteline"></a><span data-ttu-id="f55fd-244">форвардделетелине</span><span class="sxs-lookup"><span data-stu-id="f55fd-244">ForwardDeleteLine</span></span>

<span data-ttu-id="f55fd-245">Как и Форвардкилллине — удаляет текст с точки до конца строки, но не помещает удаленный текст в инструкцию KILL-Ring.</span><span class="sxs-lookup"><span data-stu-id="f55fd-245">Like ForwardKillLine - deletes text from the point to the end of the line, but does not put the deleted text in the kill-ring.</span></span>

- <span data-ttu-id="f55fd-246">Процессор `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-246">Cmd: `<Ctrl+End>`</span></span>
- <span data-ttu-id="f55fd-247">Режим вставки в VI: `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-247">Vi insert mode: `<Ctrl+End>`</span></span>
- <span data-ttu-id="f55fd-248">Режим команд VI: `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-248">Vi command mode: `<Ctrl+End>`</span></span>

### <a name="insertlineabove"></a><span data-ttu-id="f55fd-249">инсертлинеабове</span><span class="sxs-lookup"><span data-stu-id="f55fd-249">InsertLineAbove</span></span>

<span data-ttu-id="f55fd-250">Новая пустая строка создается над текущей строкой, независимо от того, где находится курсор на текущей строке.</span><span class="sxs-lookup"><span data-stu-id="f55fd-250">A new empty line is created above the current line regardless of where the cursor is on the current line.</span></span> <span data-ttu-id="f55fd-251">Курсор переместится в начало новой строки.</span><span class="sxs-lookup"><span data-stu-id="f55fd-251">The cursor moves to the beginning of the new line.</span></span>

- <span data-ttu-id="f55fd-252">Процессор `<Ctrl+Enter>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-252">Cmd: `<Ctrl+Enter>`</span></span>

### <a name="insertlinebelow"></a><span data-ttu-id="f55fd-253">инсертлинебелов</span><span class="sxs-lookup"><span data-stu-id="f55fd-253">InsertLineBelow</span></span>

<span data-ttu-id="f55fd-254">Новая пустая строка создается под текущей строкой независимо от того, где находится курсор на текущей строке.</span><span class="sxs-lookup"><span data-stu-id="f55fd-254">A new empty line is created below the current line regardless of where the cursor is on the current line.</span></span> <span data-ttu-id="f55fd-255">Курсор переместится в начало новой строки.</span><span class="sxs-lookup"><span data-stu-id="f55fd-255">The cursor moves to the beginning of the new line.</span></span>

- <span data-ttu-id="f55fd-256">Процессор `<Shift+Ctrl+Enter>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-256">Cmd: `<Shift+Ctrl+Enter>`</span></span>

### <a name="invertcase"></a><span data-ttu-id="f55fd-257">инверткасе</span><span class="sxs-lookup"><span data-stu-id="f55fd-257">InvertCase</span></span>

<span data-ttu-id="f55fd-258">Инвертировать регистр текущего символа и перейти к следующему.</span><span class="sxs-lookup"><span data-stu-id="f55fd-258">Invert the case of the current character and move to the next one.</span></span>

- <span data-ttu-id="f55fd-259">Режим команд VI: `<~>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-259">Vi command mode: `<~>`</span></span>

### <a name="killline"></a><span data-ttu-id="f55fd-260">килллине</span><span class="sxs-lookup"><span data-stu-id="f55fd-260">KillLine</span></span>

<span data-ttu-id="f55fd-261">Очистить входные данные от курсора до конца входных данных.</span><span class="sxs-lookup"><span data-stu-id="f55fd-261">Clear the input from the cursor to the end of the input.</span></span> <span data-ttu-id="f55fd-262">Очистка текста помещается в буфер Kill.</span><span class="sxs-lookup"><span data-stu-id="f55fd-262">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="f55fd-263">Emacs: `<Ctrl+k>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-263">Emacs: `<Ctrl+k>`</span></span>

### <a name="killregion"></a><span data-ttu-id="f55fd-264">киллрегион</span><span class="sxs-lookup"><span data-stu-id="f55fd-264">KillRegion</span></span>

<span data-ttu-id="f55fd-265">Удалить текст между курсором и меткой.</span><span class="sxs-lookup"><span data-stu-id="f55fd-265">Kill the text between the cursor and the mark.</span></span>

- <span data-ttu-id="f55fd-266">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="f55fd-266">Function is unbound.</span></span>

### <a name="killword"></a><span data-ttu-id="f55fd-267">киллворд</span><span class="sxs-lookup"><span data-stu-id="f55fd-267">KillWord</span></span>

<span data-ttu-id="f55fd-268">Очистить ввод от курсора до конца текущего слова.</span><span class="sxs-lookup"><span data-stu-id="f55fd-268">Clear the input from the cursor to the end of the current word.</span></span> <span data-ttu-id="f55fd-269">Если курсор находится между словами, входные данные очищаются от курсора до конца следующего слова.</span><span class="sxs-lookup"><span data-stu-id="f55fd-269">If the cursor is between words, the input is cleared from the cursor to the end of the next word.</span></span> <span data-ttu-id="f55fd-270">Очистка текста помещается в буфер Kill.</span><span class="sxs-lookup"><span data-stu-id="f55fd-270">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="f55fd-271">Cmd: `<Alt+d>` , `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-271">Cmd: `<Alt+d>`, `<Ctrl+Delete>`</span></span>
- <span data-ttu-id="f55fd-272">Emacs: `<Alt+d>` , `<Escape,d>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-272">Emacs: `<Alt+d>`, `<Escape,d>`</span></span>
- <span data-ttu-id="f55fd-273">Режим вставки в VI: `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-273">Vi insert mode: `<Ctrl+Delete>`</span></span>
- <span data-ttu-id="f55fd-274">Режим команд VI: `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-274">Vi command mode: `<Ctrl+Delete>`</span></span>

### <a name="paste"></a><span data-ttu-id="f55fd-275">Вставить</span><span class="sxs-lookup"><span data-stu-id="f55fd-275">Paste</span></span>

<span data-ttu-id="f55fd-276">Вставка текста из буфера обмена системы.</span><span class="sxs-lookup"><span data-stu-id="f55fd-276">Paste text from the system clipboard.</span></span>

- <span data-ttu-id="f55fd-277">Cmd: `<Ctrl+v>` , `<Shift+Insert>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-277">Cmd: `<Ctrl+v>`, `<Shift+Insert>`</span></span>
- <span data-ttu-id="f55fd-278">Режим вставки в VI: `<Ctrl+v>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-278">Vi insert mode: `<Ctrl+v>`</span></span>
- <span data-ttu-id="f55fd-279">Режим команд VI: `<Ctrl+v>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-279">Vi command mode: `<Ctrl+v>`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f55fd-280">При использовании функции **вставки** все содержимое буфера буфера обмена вставляется во входной буфер PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="f55fd-280">When using the **Paste** function, the entire contents of the clipboard buffer is pasted into the input buffer of PSReadLine.</span></span> <span data-ttu-id="f55fd-281">Затем входной буфер передается средству синтаксического анализа PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f55fd-281">The input buffer is then passed to the PowerShell parser.</span></span> <span data-ttu-id="f55fd-282">Вход, вставленный с помощью консольного приложения, щелкните **правой кнопкой мыши** метод вставки, скопированный во входной буфер по одному символу за раз.</span><span class="sxs-lookup"><span data-stu-id="f55fd-282">Input pasted using the console application's **right-click** paste method is copied to the input buffer one character at a time.</span></span> <span data-ttu-id="f55fd-283">Входной буфер передается средству синтаксического анализа при копировании символа новой строки.</span><span class="sxs-lookup"><span data-stu-id="f55fd-283">The input buffer is passed to the parser when a newline character is copied.</span></span> <span data-ttu-id="f55fd-284">Поэтому входные данные анализируются по одной строке за раз.</span><span class="sxs-lookup"><span data-stu-id="f55fd-284">Therefore, the input is parsed one line at a time.</span></span> <span data-ttu-id="f55fd-285">Различие между методами вставки приводит к различному поведению при выполнении.</span><span class="sxs-lookup"><span data-stu-id="f55fd-285">The difference between paste methods results in different execution behavior.</span></span>

### <a name="pasteafter"></a><span data-ttu-id="f55fd-286">пастеафтер</span><span class="sxs-lookup"><span data-stu-id="f55fd-286">PasteAfter</span></span>

<span data-ttu-id="f55fd-287">Вставьте буфер обмена после курсора, переместив курсор в конец вставленного текста.</span><span class="sxs-lookup"><span data-stu-id="f55fd-287">Paste the clipboard after the cursor, moving the cursor to the end of the pasted text.</span></span>

- <span data-ttu-id="f55fd-288">Режим команд VI: `<p>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-288">Vi command mode: `<p>`</span></span>

### <a name="pastebefore"></a><span data-ttu-id="f55fd-289">пастебефоре</span><span class="sxs-lookup"><span data-stu-id="f55fd-289">PasteBefore</span></span>

<span data-ttu-id="f55fd-290">Вставьте буфер обмена перед курсором, переместив курсор в конец вставленного текста.</span><span class="sxs-lookup"><span data-stu-id="f55fd-290">Paste the clipboard before the cursor, moving the cursor to the end of the pasted text.</span></span>

- <span data-ttu-id="f55fd-291">Режим команд VI: `<P>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-291">Vi command mode: `<P>`</span></span>

### <a name="prependandaccept"></a><span data-ttu-id="f55fd-292">препендандакцепт</span><span class="sxs-lookup"><span data-stu-id="f55fd-292">PrependAndAccept</span></span>

<span data-ttu-id="f55fd-293">Добавьте в начало "#" и примите строку.</span><span class="sxs-lookup"><span data-stu-id="f55fd-293">Prepend a '#' and accept the line.</span></span>

- <span data-ttu-id="f55fd-294">Режим команд VI: `<#>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-294">Vi command mode: `<#>`</span></span>

### <a name="redo"></a><span data-ttu-id="f55fd-295">Повторить</span><span class="sxs-lookup"><span data-stu-id="f55fd-295">Redo</span></span>

<span data-ttu-id="f55fd-296">Отмена отмены.</span><span class="sxs-lookup"><span data-stu-id="f55fd-296">Undo an undo.</span></span>

- <span data-ttu-id="f55fd-297">Процессор `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-297">Cmd: `<Ctrl+y>`</span></span>
- <span data-ttu-id="f55fd-298">Режим вставки в VI: `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-298">Vi insert mode: `<Ctrl+y>`</span></span>
- <span data-ttu-id="f55fd-299">Режим команд VI: `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-299">Vi command mode: `<Ctrl+y>`</span></span>

### <a name="repeatlastcommand"></a><span data-ttu-id="f55fd-300">репеатласткомманд</span><span class="sxs-lookup"><span data-stu-id="f55fd-300">RepeatLastCommand</span></span>

<span data-ttu-id="f55fd-301">Повторите Последнее изменение текста.</span><span class="sxs-lookup"><span data-stu-id="f55fd-301">Repeat the last text modification.</span></span>

- <span data-ttu-id="f55fd-302">Режим команд VI: `<.>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-302">Vi command mode: `<.>`</span></span>

### <a name="revertline"></a><span data-ttu-id="f55fd-303">ревертлине</span><span class="sxs-lookup"><span data-stu-id="f55fd-303">RevertLine</span></span>

<span data-ttu-id="f55fd-304">Меняет все входные данные на текущие входные данные.</span><span class="sxs-lookup"><span data-stu-id="f55fd-304">Reverts all of the input to the current input.</span></span>

- <span data-ttu-id="f55fd-305">Процессор `<Escape>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-305">Cmd: `<Escape>`</span></span>
- <span data-ttu-id="f55fd-306">Emacs: `<Alt+r>` , `<Escape,r>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-306">Emacs: `<Alt+r>`, `<Escape,r>`</span></span>

### <a name="shellbackwardkillword"></a><span data-ttu-id="f55fd-307">шеллбакквардкиллворд</span><span class="sxs-lookup"><span data-stu-id="f55fd-307">ShellBackwardKillWord</span></span>

<span data-ttu-id="f55fd-308">Очистить ввод от начала текущего слова до курсора.</span><span class="sxs-lookup"><span data-stu-id="f55fd-308">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="f55fd-309">Если курсор находится между словами, входные данные очищаются от начала предыдущего слова до курсора.</span><span class="sxs-lookup"><span data-stu-id="f55fd-309">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="f55fd-310">Очистка текста помещается в буфер Kill.</span><span class="sxs-lookup"><span data-stu-id="f55fd-310">The cleared text is placed in the kill-ring.</span></span>

<span data-ttu-id="f55fd-311">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="f55fd-311">Function is unbound.</span></span>

### <a name="shellkillword"></a><span data-ttu-id="f55fd-312">шеллкиллворд</span><span class="sxs-lookup"><span data-stu-id="f55fd-312">ShellKillWord</span></span>

<span data-ttu-id="f55fd-313">Очистить ввод от курсора до конца текущего слова.</span><span class="sxs-lookup"><span data-stu-id="f55fd-313">Clear the input from the cursor to the end of the current word.</span></span> <span data-ttu-id="f55fd-314">Если курсор находится между словами, входные данные очищаются от курсора до конца следующего слова.</span><span class="sxs-lookup"><span data-stu-id="f55fd-314">If the cursor is between words, the input is cleared from the cursor to the end of the next word.</span></span> <span data-ttu-id="f55fd-315">Очистка текста помещается в буфер Kill.</span><span class="sxs-lookup"><span data-stu-id="f55fd-315">The cleared text is placed in the kill-ring.</span></span>

<span data-ttu-id="f55fd-316">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="f55fd-316">Function is unbound.</span></span>

### <a name="swapcharacters"></a><span data-ttu-id="f55fd-317">свапчарактерс</span><span class="sxs-lookup"><span data-stu-id="f55fd-317">SwapCharacters</span></span>

<span data-ttu-id="f55fd-318">Поменять местами текущий и тот же символ.</span><span class="sxs-lookup"><span data-stu-id="f55fd-318">Swap the current character and the one before it.</span></span>

- <span data-ttu-id="f55fd-319">Emacs: `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-319">Emacs: `<Ctrl+t>`</span></span>
- <span data-ttu-id="f55fd-320">Режим вставки в VI: `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-320">Vi insert mode: `<Ctrl+t>`</span></span>
- <span data-ttu-id="f55fd-321">Режим команд VI: `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-321">Vi command mode: `<Ctrl+t>`</span></span>

### <a name="undo"></a><span data-ttu-id="f55fd-322">Отменить</span><span class="sxs-lookup"><span data-stu-id="f55fd-322">Undo</span></span>

<span data-ttu-id="f55fd-323">Отмена предыдущего изменения.</span><span class="sxs-lookup"><span data-stu-id="f55fd-323">Undo a previous edit.</span></span>

- <span data-ttu-id="f55fd-324">Процессор `<Ctrl+z>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-324">Cmd: `<Ctrl+z>`</span></span>
- <span data-ttu-id="f55fd-325">Emacs: `<Ctrl+_>` , `<Ctrl+x,Ctrl+u>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-325">Emacs: `<Ctrl+_>`, `<Ctrl+x,Ctrl+u>`</span></span>
- <span data-ttu-id="f55fd-326">Режим вставки в VI: `<Ctrl+z>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-326">Vi insert mode: `<Ctrl+z>`</span></span>
- <span data-ttu-id="f55fd-327">Режим команд VI: `<Ctrl+z>` , `<u>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-327">Vi command mode: `<Ctrl+z>`, `<u>`</span></span>

### <a name="undoall"></a><span data-ttu-id="f55fd-328">ундоалл</span><span class="sxs-lookup"><span data-stu-id="f55fd-328">UndoAll</span></span>

<span data-ttu-id="f55fd-329">Отмена всех предыдущих изменений для строки.</span><span class="sxs-lookup"><span data-stu-id="f55fd-329">Undo all previous edits for line.</span></span>

- <span data-ttu-id="f55fd-330">Режим команд VI: `<U>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-330">Vi command mode: `<U>`</span></span>

### <a name="unixwordrubout"></a><span data-ttu-id="f55fd-331">униксвордрубаут</span><span class="sxs-lookup"><span data-stu-id="f55fd-331">UnixWordRubout</span></span>

<span data-ttu-id="f55fd-332">Очистить ввод от начала текущего слова до курсора.</span><span class="sxs-lookup"><span data-stu-id="f55fd-332">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="f55fd-333">Если курсор находится между словами, входные данные очищаются от начала предыдущего слова до курсора.</span><span class="sxs-lookup"><span data-stu-id="f55fd-333">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="f55fd-334">Очистка текста помещается в буфер Kill.</span><span class="sxs-lookup"><span data-stu-id="f55fd-334">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="f55fd-335">Emacs: `<Ctrl+w>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-335">Emacs: `<Ctrl+w>`</span></span>

### <a name="validateandacceptline"></a><span data-ttu-id="f55fd-336">валидатеандакцептлине</span><span class="sxs-lookup"><span data-stu-id="f55fd-336">ValidateAndAcceptLine</span></span>

<span data-ttu-id="f55fd-337">Попытка выполнить текущий вход.</span><span class="sxs-lookup"><span data-stu-id="f55fd-337">Attempt to execute the current input.</span></span> <span data-ttu-id="f55fd-338">Если текущий ввод неполон (например, отсутствует закрывающая круглая скобка, квадратная скобка или кавычка, запрос продолжения отображается на следующей строке, а PSReadLine ожидает ввода ключей для изменения текущих входных данных.</span><span class="sxs-lookup"><span data-stu-id="f55fd-338">If the current input is incomplete (for example there is a missing closing parenthesis, bracket, or quote, then the continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span>

- <span data-ttu-id="f55fd-339">Emacs: `<Ctrl+m>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-339">Emacs: `<Ctrl+m>`</span></span>

### <a name="viacceptline"></a><span data-ttu-id="f55fd-340">виакцептлине</span><span class="sxs-lookup"><span data-stu-id="f55fd-340">ViAcceptLine</span></span>

<span data-ttu-id="f55fd-341">Примите строку и переключитесь в режим вставки.</span><span class="sxs-lookup"><span data-stu-id="f55fd-341">Accept the line and switch to Insert mode.</span></span>

- <span data-ttu-id="f55fd-342">Режим команд VI: `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-342">Vi command mode: `<Enter>`</span></span>

### <a name="viacceptlineorexit"></a><span data-ttu-id="f55fd-343">виакцептлинеорексит</span><span class="sxs-lookup"><span data-stu-id="f55fd-343">ViAcceptLineOrExit</span></span>

<span data-ttu-id="f55fd-344">Как и Делетечарорексит в режиме Emacs, но принимает строку вместо удаления символа.</span><span class="sxs-lookup"><span data-stu-id="f55fd-344">Like DeleteCharOrExit in Emacs mode, but accepts the line instead of deleting a character.</span></span>

- <span data-ttu-id="f55fd-345">Режим вставки в VI: `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-345">Vi insert mode: `<Ctrl+d>`</span></span>
- <span data-ttu-id="f55fd-346">Режим команд VI: `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-346">Vi command mode: `<Ctrl+d>`</span></span>

### <a name="viappendline"></a><span data-ttu-id="f55fd-347">виаппендлине</span><span class="sxs-lookup"><span data-stu-id="f55fd-347">ViAppendLine</span></span>

<span data-ttu-id="f55fd-348">Новая строка вставляется под текущей строкой.</span><span class="sxs-lookup"><span data-stu-id="f55fd-348">A new line is inserted below the current line.</span></span>

- <span data-ttu-id="f55fd-349">Режим команд VI: `<o>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-349">Vi command mode: `<o>`</span></span>

### <a name="vibackwarddeleteglob"></a><span data-ttu-id="f55fd-350">вибакквардделетеглоб</span><span class="sxs-lookup"><span data-stu-id="f55fd-350">ViBackwardDeleteGlob</span></span>

<span data-ttu-id="f55fd-351">Удаляет предыдущее слово, используя только пробелы в качестве разделителя слов.</span><span class="sxs-lookup"><span data-stu-id="f55fd-351">Deletes the previous word, using only white space as the word delimiter.</span></span>

- <span data-ttu-id="f55fd-352">Режим команд VI: `<d,B>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-352">Vi command mode: `<d,B>`</span></span>

### <a name="vibackwardglob"></a><span data-ttu-id="f55fd-353">вибакквардглоб</span><span class="sxs-lookup"><span data-stu-id="f55fd-353">ViBackwardGlob</span></span>

<span data-ttu-id="f55fd-354">Перемещает курсор назад к началу предыдущего слова, используя только пробелы в качестве разделителей.</span><span class="sxs-lookup"><span data-stu-id="f55fd-354">Moves the cursor back to the beginning of the previous word, using only white space as delimiters.</span></span>

- <span data-ttu-id="f55fd-355">Режим команд VI: `<B>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-355">Vi command mode: `<B>`</span></span>

### <a name="videletebrace"></a><span data-ttu-id="f55fd-356">виделетебраце</span><span class="sxs-lookup"><span data-stu-id="f55fd-356">ViDeleteBrace</span></span>

<span data-ttu-id="f55fd-357">Найдите парную фигурную скобку, круглую скобку или квадратную скобку и удалите все содержимое внутри, включая фигурную скобку.</span><span class="sxs-lookup"><span data-stu-id="f55fd-357">Find the matching brace, parenthesis, or square bracket and delete all contents within, including the brace.</span></span>

- <span data-ttu-id="f55fd-358">Режим команд VI: `<d,%>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-358">Vi command mode: `<d,%>`</span></span>

### <a name="videleteendofglob"></a><span data-ttu-id="f55fd-359">виделетиндофглоб</span><span class="sxs-lookup"><span data-stu-id="f55fd-359">ViDeleteEndOfGlob</span></span>

<span data-ttu-id="f55fd-360">Удалить до конца слова.</span><span class="sxs-lookup"><span data-stu-id="f55fd-360">Delete to the end of the word.</span></span>

- <span data-ttu-id="f55fd-361">Режим команд VI: `<d,E>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-361">Vi command mode: `<d,E>`</span></span>

### <a name="videleteglob"></a><span data-ttu-id="f55fd-362">виделетеглоб</span><span class="sxs-lookup"><span data-stu-id="f55fd-362">ViDeleteGlob</span></span>

<span data-ttu-id="f55fd-363">Удалите следующий стандартная маска (слово, разделенное пробелами).</span><span class="sxs-lookup"><span data-stu-id="f55fd-363">Delete the next glob (white space delimited word).</span></span>

- <span data-ttu-id="f55fd-364">Режим команд VI: `<d,W>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-364">Vi command mode: `<d,W>`</span></span>

### <a name="videletetobeforechar"></a><span data-ttu-id="f55fd-365">виделететобефоречар</span><span class="sxs-lookup"><span data-stu-id="f55fd-365">ViDeleteToBeforeChar</span></span>

<span data-ttu-id="f55fd-366">Удаляет до заданного символа.</span><span class="sxs-lookup"><span data-stu-id="f55fd-366">Deletes until given character.</span></span>

- <span data-ttu-id="f55fd-367">Режим команд VI: `<d,t>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-367">Vi command mode: `<d,t>`</span></span>

### <a name="videletetobeforecharbackward"></a><span data-ttu-id="f55fd-368">виделететобефоречарбакквард</span><span class="sxs-lookup"><span data-stu-id="f55fd-368">ViDeleteToBeforeCharBackward</span></span>

<span data-ttu-id="f55fd-369">Удаляет до заданного символа.</span><span class="sxs-lookup"><span data-stu-id="f55fd-369">Deletes until given character.</span></span>

- <span data-ttu-id="f55fd-370">Режим команд VI: `<d,T>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-370">Vi command mode: `<d,T>`</span></span>

### <a name="videletetochar"></a><span data-ttu-id="f55fd-371">виделететочар</span><span class="sxs-lookup"><span data-stu-id="f55fd-371">ViDeleteToChar</span></span>

<span data-ttu-id="f55fd-372">Удаляет до заданного символа.</span><span class="sxs-lookup"><span data-stu-id="f55fd-372">Deletes until given character.</span></span>

- <span data-ttu-id="f55fd-373">Режим команд VI: `<d,f>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-373">Vi command mode: `<d,f>`</span></span>

### <a name="videletetocharbackward"></a><span data-ttu-id="f55fd-374">виделететочарбакквард</span><span class="sxs-lookup"><span data-stu-id="f55fd-374">ViDeleteToCharBackward</span></span>

<span data-ttu-id="f55fd-375">Удаляет обратную сторону до заданного символа.</span><span class="sxs-lookup"><span data-stu-id="f55fd-375">Deletes backwards until given character.</span></span>

- <span data-ttu-id="f55fd-376">Режим команд VI: `<d,F>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-376">Vi command mode: `<d,F>`</span></span>

### <a name="viinsertatbegining"></a><span data-ttu-id="f55fd-377">виинсертатбегининг</span><span class="sxs-lookup"><span data-stu-id="f55fd-377">ViInsertAtBegining</span></span>

<span data-ttu-id="f55fd-378">Переключитесь в режим вставки и поместите курсор в начало строки.</span><span class="sxs-lookup"><span data-stu-id="f55fd-378">Switch to Insert mode and position the cursor at the beginning of the line.</span></span>

- <span data-ttu-id="f55fd-379">Режим команд VI: `<I>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-379">Vi command mode: `<I>`</span></span>

### <a name="viinsertatend"></a><span data-ttu-id="f55fd-380">виинсертатенд</span><span class="sxs-lookup"><span data-stu-id="f55fd-380">ViInsertAtEnd</span></span>

<span data-ttu-id="f55fd-381">Переключитесь в режим вставки и поместите курсор в конец строки.</span><span class="sxs-lookup"><span data-stu-id="f55fd-381">Switch to Insert mode and position the cursor at the end of the line.</span></span>

- <span data-ttu-id="f55fd-382">Режим команд VI: `<A>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-382">Vi command mode: `<A>`</span></span>

### <a name="viinsertline"></a><span data-ttu-id="f55fd-383">виинсертлине</span><span class="sxs-lookup"><span data-stu-id="f55fd-383">ViInsertLine</span></span>

<span data-ttu-id="f55fd-384">Новая строка вставляется над текущей строкой.</span><span class="sxs-lookup"><span data-stu-id="f55fd-384">A new line is inserted above the current line.</span></span>

- <span data-ttu-id="f55fd-385">Режим команд VI: `<O>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-385">Vi command mode: `<O>`</span></span>

### <a name="viinsertwithappend"></a><span data-ttu-id="f55fd-386">виинсертвисаппенд</span><span class="sxs-lookup"><span data-stu-id="f55fd-386">ViInsertWithAppend</span></span>

<span data-ttu-id="f55fd-387">Добавление из текущей позицией строки.</span><span class="sxs-lookup"><span data-stu-id="f55fd-387">Append from the current line position.</span></span>

- <span data-ttu-id="f55fd-388">Режим команд VI: `<a>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-388">Vi command mode: `<a>`</span></span>

### <a name="viinsertwithdelete"></a><span data-ttu-id="f55fd-389">виинсертвисделете</span><span class="sxs-lookup"><span data-stu-id="f55fd-389">ViInsertWithDelete</span></span>

<span data-ttu-id="f55fd-390">Удалите текущий символ и переключитесь в режим вставки.</span><span class="sxs-lookup"><span data-stu-id="f55fd-390">Delete the current character and switch to Insert mode.</span></span>

- <span data-ttu-id="f55fd-391">Режим команд VI: `<s>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-391">Vi command mode: `<s>`</span></span>

### <a name="vijoinlines"></a><span data-ttu-id="f55fd-392">вижоинлинес</span><span class="sxs-lookup"><span data-stu-id="f55fd-392">ViJoinLines</span></span>

<span data-ttu-id="f55fd-393">Объединяет текущую строку и следующую строку.</span><span class="sxs-lookup"><span data-stu-id="f55fd-393">Joins the current line and the next line.</span></span>

- <span data-ttu-id="f55fd-394">Режим команд VI: `<J>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-394">Vi command mode: `<J>`</span></span>

### <a name="vireplaceline"></a><span data-ttu-id="f55fd-395">виреплацелине</span><span class="sxs-lookup"><span data-stu-id="f55fd-395">ViReplaceLine</span></span>

<span data-ttu-id="f55fd-396">Очистить всю командную строку.</span><span class="sxs-lookup"><span data-stu-id="f55fd-396">Erase the entire command line.</span></span>

- <span data-ttu-id="f55fd-397">Режим команд VI: `<S>` , `<c,c>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-397">Vi command mode: `<S>`, `<c,c>`</span></span>

### <a name="vireplacetobeforechar"></a><span data-ttu-id="f55fd-398">виреплацетобефоречар</span><span class="sxs-lookup"><span data-stu-id="f55fd-398">ViReplaceToBeforeChar</span></span>

<span data-ttu-id="f55fd-399">Заменяет заданный символ.</span><span class="sxs-lookup"><span data-stu-id="f55fd-399">Replaces until given character.</span></span>

- <span data-ttu-id="f55fd-400">Режим команд VI: `<c,t>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-400">Vi command mode: `<c,t>`</span></span>

### <a name="vireplacetobeforecharbackward"></a><span data-ttu-id="f55fd-401">виреплацетобефоречарбакквард</span><span class="sxs-lookup"><span data-stu-id="f55fd-401">ViReplaceToBeforeCharBackward</span></span>

<span data-ttu-id="f55fd-402">Заменяет заданный символ.</span><span class="sxs-lookup"><span data-stu-id="f55fd-402">Replaces until given character.</span></span>

- <span data-ttu-id="f55fd-403">Режим команд VI: `<c,T>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-403">Vi command mode: `<c,T>`</span></span>

### <a name="vireplacetochar"></a><span data-ttu-id="f55fd-404">виреплацеточар</span><span class="sxs-lookup"><span data-stu-id="f55fd-404">ViReplaceToChar</span></span>

<span data-ttu-id="f55fd-405">Удаляет до заданного символа.</span><span class="sxs-lookup"><span data-stu-id="f55fd-405">Deletes until given character.</span></span>

- <span data-ttu-id="f55fd-406">Режим команд VI: `<c,f>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-406">Vi command mode: `<c,f>`</span></span>

### <a name="vireplacetocharbackward"></a><span data-ttu-id="f55fd-407">виреплацеточарбакквард</span><span class="sxs-lookup"><span data-stu-id="f55fd-407">ViReplaceToCharBackward</span></span>

<span data-ttu-id="f55fd-408">Заменяет заданный символ.</span><span class="sxs-lookup"><span data-stu-id="f55fd-408">Replaces until given character.</span></span>

- <span data-ttu-id="f55fd-409">Режим команд VI: `<c,F>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-409">Vi command mode: `<c,F>`</span></span>

### <a name="viyankbeginningofline"></a><span data-ttu-id="f55fd-410">вийанкбегиннингофлине</span><span class="sxs-lookup"><span data-stu-id="f55fd-410">ViYankBeginningOfLine</span></span>

<span data-ttu-id="f55fd-411">Янк от начала буфера до курсора.</span><span class="sxs-lookup"><span data-stu-id="f55fd-411">Yank from the beginning of the buffer to the cursor.</span></span>

- <span data-ttu-id="f55fd-412">Режим команд VI: `<y,0>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-412">Vi command mode: `<y,0>`</span></span>

### <a name="viyankendofglob"></a><span data-ttu-id="f55fd-413">вийанкендофглоб</span><span class="sxs-lookup"><span data-stu-id="f55fd-413">ViYankEndOfGlob</span></span>

<span data-ttu-id="f55fd-414">Янк от курсора до конца слова.</span><span class="sxs-lookup"><span data-stu-id="f55fd-414">Yank from the cursor to the end of the WORD(s).</span></span>

- <span data-ttu-id="f55fd-415">Режим команд VI: `<y,E>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-415">Vi command mode: `<y,E>`</span></span>

### <a name="viyankendofword"></a><span data-ttu-id="f55fd-416">вийанкендофворд</span><span class="sxs-lookup"><span data-stu-id="f55fd-416">ViYankEndOfWord</span></span>

<span data-ttu-id="f55fd-417">Янк от курсора до конца слова.</span><span class="sxs-lookup"><span data-stu-id="f55fd-417">Yank from the cursor to the end of the word(s).</span></span>

- <span data-ttu-id="f55fd-418">Режим команд VI: `<y,e>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-418">Vi command mode: `<y,e>`</span></span>

### <a name="viyankleft"></a><span data-ttu-id="f55fd-419">вийанклефт</span><span class="sxs-lookup"><span data-stu-id="f55fd-419">ViYankLeft</span></span>

<span data-ttu-id="f55fd-420">Янк символы слева от курсора.</span><span class="sxs-lookup"><span data-stu-id="f55fd-420">Yank character(s) to the left of the cursor.</span></span>

- <span data-ttu-id="f55fd-421">Режим команд VI: `<y,h>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-421">Vi command mode: `<y,h>`</span></span>

### <a name="viyankline"></a><span data-ttu-id="f55fd-422">вийанклине</span><span class="sxs-lookup"><span data-stu-id="f55fd-422">ViYankLine</span></span>

<span data-ttu-id="f55fd-423">Янк весь буфер.</span><span class="sxs-lookup"><span data-stu-id="f55fd-423">Yank the entire buffer.</span></span>

- <span data-ttu-id="f55fd-424">Режим команд VI: `<y,y>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-424">Vi command mode: `<y,y>`</span></span>

### <a name="viyanknextglob"></a><span data-ttu-id="f55fd-425">вийанкнекстглоб</span><span class="sxs-lookup"><span data-stu-id="f55fd-425">ViYankNextGlob</span></span>

<span data-ttu-id="f55fd-426">Янк от курсора до начала следующего слова.</span><span class="sxs-lookup"><span data-stu-id="f55fd-426">Yank from cursor to the start of the next WORD(s).</span></span>

- <span data-ttu-id="f55fd-427">Режим команд VI: `<y,W>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-427">Vi command mode: `<y,W>`</span></span>

### <a name="viyanknextword"></a><span data-ttu-id="f55fd-428">вийанкнекстворд</span><span class="sxs-lookup"><span data-stu-id="f55fd-428">ViYankNextWord</span></span>

<span data-ttu-id="f55fd-429">Янк слова после курсора.</span><span class="sxs-lookup"><span data-stu-id="f55fd-429">Yank the word(s) after the cursor.</span></span>

- <span data-ttu-id="f55fd-430">Режим команд VI: `<y,w>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-430">Vi command mode: `<y,w>`</span></span>

### <a name="viyankpercent"></a><span data-ttu-id="f55fd-431">вийанкперцент</span><span class="sxs-lookup"><span data-stu-id="f55fd-431">ViYankPercent</span></span>

<span data-ttu-id="f55fd-432">Янк в парную фигурную скобку.</span><span class="sxs-lookup"><span data-stu-id="f55fd-432">Yank to/from matching brace.</span></span>

- <span data-ttu-id="f55fd-433">Режим команд VI: `<y,%>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-433">Vi command mode: `<y,%>`</span></span>

### <a name="viyankpreviousglob"></a><span data-ttu-id="f55fd-434">вийанкпревиаусглоб</span><span class="sxs-lookup"><span data-stu-id="f55fd-434">ViYankPreviousGlob</span></span>

<span data-ttu-id="f55fd-435">Янк от начала слов до курсора.</span><span class="sxs-lookup"><span data-stu-id="f55fd-435">Yank from beginning of the WORD(s) to cursor.</span></span>

- <span data-ttu-id="f55fd-436">Режим команд VI: `<y,B>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-436">Vi command mode: `<y,B>`</span></span>

### <a name="viyankpreviousword"></a><span data-ttu-id="f55fd-437">вийанкпревиаусворд</span><span class="sxs-lookup"><span data-stu-id="f55fd-437">ViYankPreviousWord</span></span>

<span data-ttu-id="f55fd-438">Янк слова перед курсором.</span><span class="sxs-lookup"><span data-stu-id="f55fd-438">Yank the word(s) before the cursor.</span></span>

- <span data-ttu-id="f55fd-439">Режим команд VI: `<y,b>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-439">Vi command mode: `<y,b>`</span></span>

### <a name="viyankright"></a><span data-ttu-id="f55fd-440">вийанкригхт</span><span class="sxs-lookup"><span data-stu-id="f55fd-440">ViYankRight</span></span>

<span data-ttu-id="f55fd-441">Янк символы в положении и справа от курсора.</span><span class="sxs-lookup"><span data-stu-id="f55fd-441">Yank character(s) under and to the right of the cursor.</span></span>

- <span data-ttu-id="f55fd-442">Режим команд VI: `<y,l>` , `<y,Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-442">Vi command mode: `<y,l>`, `<y,Spacebar>`</span></span>

### <a name="viyanktoendofline"></a><span data-ttu-id="f55fd-443">вийанктоендофлине</span><span class="sxs-lookup"><span data-stu-id="f55fd-443">ViYankToEndOfLine</span></span>

<span data-ttu-id="f55fd-444">Янк от курсора до конца буфера.</span><span class="sxs-lookup"><span data-stu-id="f55fd-444">Yank from the cursor to the end of the buffer.</span></span>

- <span data-ttu-id="f55fd-445">Режим команд VI: `<y,$>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-445">Vi command mode: `<y,$>`</span></span>

### <a name="viyanktofirstchar"></a><span data-ttu-id="f55fd-446">вийанктофирстчар</span><span class="sxs-lookup"><span data-stu-id="f55fd-446">ViYankToFirstChar</span></span>

<span data-ttu-id="f55fd-447">Янк от первого символа, отличного от пробела, к курсору.</span><span class="sxs-lookup"><span data-stu-id="f55fd-447">Yank from the first non-whitespace character to the cursor.</span></span>

- <span data-ttu-id="f55fd-448">Режим команд VI: `<y,^>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-448">Vi command mode: `<y,^>`</span></span>

### <a name="yank"></a><span data-ttu-id="f55fd-449">янк</span><span class="sxs-lookup"><span data-stu-id="f55fd-449">Yank</span></span>

<span data-ttu-id="f55fd-450">Добавление последнего недавнего текста во входные данные.</span><span class="sxs-lookup"><span data-stu-id="f55fd-450">Add the most recently killed text to the input.</span></span>

- <span data-ttu-id="f55fd-451">Emacs: `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-451">Emacs: `<Ctrl+y>`</span></span>

### <a name="yanklastarg"></a><span data-ttu-id="f55fd-452">янкластарг</span><span class="sxs-lookup"><span data-stu-id="f55fd-452">YankLastArg</span></span>

<span data-ttu-id="f55fd-453">Янк последний аргумент из предыдущей строки журнала.</span><span class="sxs-lookup"><span data-stu-id="f55fd-453">Yank the last argument from the previous history line.</span></span> <span data-ttu-id="f55fd-454">С аргументом при первом вызове он ведет себя так же, как Янкнсарг.</span><span class="sxs-lookup"><span data-stu-id="f55fd-454">With an argument, the first time it is invoked, behaves just like YankNthArg.</span></span> <span data-ttu-id="f55fd-455">Если вызывается несколько раз, вместо этого выполняется итерация по журналу, а аргумент устанавливает направление (отрицательно меняет направление на противоположное).</span><span class="sxs-lookup"><span data-stu-id="f55fd-455">If invoked multiple times, instead it iterates through history and arg sets the direction (negative reverses the direction.)</span></span>

- <span data-ttu-id="f55fd-456">Процессор `<Alt+.>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-456">Cmd: `<Alt+.>`</span></span>
- <span data-ttu-id="f55fd-457">Emacs: `<Alt+.>` , `<Alt+_>` , `<Escape,.>` , `<Escape,_>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-457">Emacs: `<Alt+.>`, `<Alt+_>`, `<Escape,.>`, `<Escape,_>`</span></span>

### <a name="yankntharg"></a><span data-ttu-id="f55fd-458">янкнсарг</span><span class="sxs-lookup"><span data-stu-id="f55fd-458">YankNthArg</span></span>

<span data-ttu-id="f55fd-459">Янк первый аргумент (после команды) из предыдущей строки журнала.</span><span class="sxs-lookup"><span data-stu-id="f55fd-459">Yank the first argument (after the command) from the previous history line.</span></span>
<span data-ttu-id="f55fd-460">При использовании аргумента Янк аргумент n (начиная с 0), если аргумент является отрицательным, начните с последнего аргумента.</span><span class="sxs-lookup"><span data-stu-id="f55fd-460">With an argument, yank the nth argument (starting from 0), if the argument is negative, start from the last argument.</span></span>

- <span data-ttu-id="f55fd-461">Emacs: `<Ctrl+Alt+y>` , `<Escape,Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-461">Emacs: `<Ctrl+Alt+y>`, `<Escape,Ctrl+y>`</span></span>

### <a name="yankpop"></a><span data-ttu-id="f55fd-462">янкпоп</span><span class="sxs-lookup"><span data-stu-id="f55fd-462">YankPop</span></span>

<span data-ttu-id="f55fd-463">Если предыдущая операция была Янк или Янкпоп, замените ранее янкед текст следующим уничтоженным текстом из Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="f55fd-463">If the previous operation was Yank or YankPop, replace the previously yanked text with the next killed text from the kill-ring.</span></span>

- <span data-ttu-id="f55fd-464">Emacs: `<Alt+y>` , `<Escape,y>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-464">Emacs: `<Alt+y>`, `<Escape,y>`</span></span>

## <a name="cursor-movement-functions"></a><span data-ttu-id="f55fd-465">Функции перемещения курсора</span><span class="sxs-lookup"><span data-stu-id="f55fd-465">Cursor movement functions</span></span>

### <a name="backwardchar"></a><span data-ttu-id="f55fd-466">бакквардчар</span><span class="sxs-lookup"><span data-stu-id="f55fd-466">BackwardChar</span></span>

<span data-ttu-id="f55fd-467">Переместить курсор на один символ влево.</span><span class="sxs-lookup"><span data-stu-id="f55fd-467">Move the cursor one character to the left.</span></span> <span data-ttu-id="f55fd-468">Это может переместить курсор к предыдущей строке многострочного ввода.</span><span class="sxs-lookup"><span data-stu-id="f55fd-468">This may move the cursor to the previous line of multi-line input.</span></span>

- <span data-ttu-id="f55fd-469">Процессор `<LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-469">Cmd: `<LeftArrow>`</span></span>
- <span data-ttu-id="f55fd-470">Emacs: `<LeftArrow>` , `<Ctrl+b>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-470">Emacs: `<LeftArrow>`, `<Ctrl+b>`</span></span>

### <a name="backwardword"></a><span data-ttu-id="f55fd-471">бакквардворд</span><span class="sxs-lookup"><span data-stu-id="f55fd-471">BackwardWord</span></span>

<span data-ttu-id="f55fd-472">Перемещение курсора назад к началу текущего слова или между словами, с начала предыдущего слова.</span><span class="sxs-lookup"><span data-stu-id="f55fd-472">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="f55fd-473">Границы слов определяются с помощью настраиваемого набора символов.</span><span class="sxs-lookup"><span data-stu-id="f55fd-473">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="f55fd-474">Процессор `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-474">Cmd: `<Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="f55fd-475">Emacs: `<Alt+b>` , `<Escape,b>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-475">Emacs: `<Alt+b>`, `<Escape,b>`</span></span>
- <span data-ttu-id="f55fd-476">Режим вставки в VI: `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-476">Vi insert mode: `<Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="f55fd-477">Режим команд VI: `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-477">Vi command mode: `<Ctrl+LeftArrow>`</span></span>

### <a name="beginningofline"></a><span data-ttu-id="f55fd-478">бегиннингофлине</span><span class="sxs-lookup"><span data-stu-id="f55fd-478">BeginningOfLine</span></span>

<span data-ttu-id="f55fd-479">Если входные данные имеют несколько строк, переместитесь в начало текущей строки или, если они уже находятся в начале строки, перейдите к началу входного элемента.</span><span class="sxs-lookup"><span data-stu-id="f55fd-479">If the input has multiple lines, move to the start of the current line, or if already at the start of the line, move to the start of the input.</span></span> <span data-ttu-id="f55fd-480">Если входные данные имеют одну строку, переходите к началу входных данных.</span><span class="sxs-lookup"><span data-stu-id="f55fd-480">If the input has a single line, move to the start of the input.</span></span>

- <span data-ttu-id="f55fd-481">Процессор `<Home>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-481">Cmd: `<Home>`</span></span>
- <span data-ttu-id="f55fd-482">Emacs: `<Home>` , `<Ctrl+a>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-482">Emacs: `<Home>`, `<Ctrl+a>`</span></span>
- <span data-ttu-id="f55fd-483">Режим вставки в VI: `<Home>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-483">Vi insert mode: `<Home>`</span></span>
- <span data-ttu-id="f55fd-484">Режим команд VI: `<Home>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-484">Vi command mode: `<Home>`</span></span>

### <a name="endofline"></a><span data-ttu-id="f55fd-485">ендофлине</span><span class="sxs-lookup"><span data-stu-id="f55fd-485">EndOfLine</span></span>

<span data-ttu-id="f55fd-486">Если входные данные имеют несколько строк, переместитесь в конец текущей строки или, если они уже находятся в конце строки, перейдите к концу входных данных.</span><span class="sxs-lookup"><span data-stu-id="f55fd-486">If the input has multiple lines, move to the end of the current line, or if already at the end of the line, move to the end of the input.</span></span> <span data-ttu-id="f55fd-487">Если входные данные имеют одну строку, переходите к концу входных данных.</span><span class="sxs-lookup"><span data-stu-id="f55fd-487">If the input has a single line, move to the end of the input.</span></span>

- <span data-ttu-id="f55fd-488">Процессор `<End>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-488">Cmd: `<End>`</span></span>
- <span data-ttu-id="f55fd-489">Emacs: `<End>` , `<Ctrl+e>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-489">Emacs: `<End>`, `<Ctrl+e>`</span></span>
- <span data-ttu-id="f55fd-490">Режим вставки в VI: `<End>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-490">Vi insert mode: `<End>`</span></span>

### <a name="forwardchar"></a><span data-ttu-id="f55fd-491">форвардчар</span><span class="sxs-lookup"><span data-stu-id="f55fd-491">ForwardChar</span></span>

<span data-ttu-id="f55fd-492">Переместить курсор на один символ вправо.</span><span class="sxs-lookup"><span data-stu-id="f55fd-492">Move the cursor one character to the right.</span></span> <span data-ttu-id="f55fd-493">Это может переместить курсор на следующую строку многострочного ввода.</span><span class="sxs-lookup"><span data-stu-id="f55fd-493">This may move the cursor to the next line of multi-line input.</span></span>

- <span data-ttu-id="f55fd-494">Процессор `<RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-494">Cmd: `<RightArrow>`</span></span>
- <span data-ttu-id="f55fd-495">Emacs: `<RightArrow>` , `<Ctrl+f>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-495">Emacs: `<RightArrow>`, `<Ctrl+f>`</span></span>

### <a name="forwardword"></a><span data-ttu-id="f55fd-496">форвардворд</span><span class="sxs-lookup"><span data-stu-id="f55fd-496">ForwardWord</span></span>

<span data-ttu-id="f55fd-497">Переместить курсор вперед к концу текущего слова или между словами, до конца следующего слова.</span><span class="sxs-lookup"><span data-stu-id="f55fd-497">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="f55fd-498">Границы слов определяются с помощью настраиваемого набора символов.</span><span class="sxs-lookup"><span data-stu-id="f55fd-498">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="f55fd-499">Emacs: `<Alt+f>` , `<Escape,f>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-499">Emacs: `<Alt+f>`, `<Escape,f>`</span></span>

### <a name="gotobrace"></a><span data-ttu-id="f55fd-500">GotoBrace</span><span class="sxs-lookup"><span data-stu-id="f55fd-500">GotoBrace</span></span>

<span data-ttu-id="f55fd-501">Перейдите к парной фигурной скобке, круглой скобке или квадратной скобке.</span><span class="sxs-lookup"><span data-stu-id="f55fd-501">Go to the matching brace, parenthesis, or square bracket.</span></span>

- <span data-ttu-id="f55fd-502">Процессор `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-502">Cmd: `<Ctrl+]>`</span></span>
- <span data-ttu-id="f55fd-503">Режим вставки в VI: `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-503">Vi insert mode: `<Ctrl+]>`</span></span>
- <span data-ttu-id="f55fd-504">Режим команд VI: `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-504">Vi command mode: `<Ctrl+]>`</span></span>

### <a name="gotocolumn"></a><span data-ttu-id="f55fd-505">готоколумн</span><span class="sxs-lookup"><span data-stu-id="f55fd-505">GotoColumn</span></span>

<span data-ttu-id="f55fd-506">Переход к столбцу, указанному аргументом arg.</span><span class="sxs-lookup"><span data-stu-id="f55fd-506">Move to the column indicated by arg.</span></span>

- <span data-ttu-id="f55fd-507">Режим команд VI: `<|>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-507">Vi command mode: `<|>`</span></span>

### <a name="gotofirstnonblankofline"></a><span data-ttu-id="f55fd-508">готофирстнонбланкофлине</span><span class="sxs-lookup"><span data-stu-id="f55fd-508">GotoFirstNonBlankOfLine</span></span>

<span data-ttu-id="f55fd-509">Переместить курсор к первому непустому символу в строке.</span><span class="sxs-lookup"><span data-stu-id="f55fd-509">Move the cursor to the first non-blank character in the line.</span></span>

- <span data-ttu-id="f55fd-510">Режим команд VI: `<^>` , `<_>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-510">Vi command mode: `<^>`, `<_>`</span></span>

### <a name="movetoendofline"></a><span data-ttu-id="f55fd-511">моветоендофлине</span><span class="sxs-lookup"><span data-stu-id="f55fd-511">MoveToEndOfLine</span></span>

<span data-ttu-id="f55fd-512">Переместить курсор в конец входных данных.</span><span class="sxs-lookup"><span data-stu-id="f55fd-512">Move the cursor to the end of the input.</span></span>

- <span data-ttu-id="f55fd-513">Режим команд VI: `<End>` , `<$>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-513">Vi command mode: `<End>`, `<$>`</span></span>

### <a name="nextline"></a><span data-ttu-id="f55fd-514">некстлине</span><span class="sxs-lookup"><span data-stu-id="f55fd-514">NextLine</span></span>

<span data-ttu-id="f55fd-515">Переместить курсор на следующую строку.</span><span class="sxs-lookup"><span data-stu-id="f55fd-515">Move the cursor to the next line.</span></span>

- <span data-ttu-id="f55fd-516">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="f55fd-516">Function is unbound.</span></span>

### <a name="nextword"></a><span data-ttu-id="f55fd-517">некстворд</span><span class="sxs-lookup"><span data-stu-id="f55fd-517">NextWord</span></span>

<span data-ttu-id="f55fd-518">Переместить курсор вперед к началу следующего слова.</span><span class="sxs-lookup"><span data-stu-id="f55fd-518">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="f55fd-519">Границы слов определяются с помощью настраиваемого набора символов.</span><span class="sxs-lookup"><span data-stu-id="f55fd-519">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="f55fd-520">Процессор `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-520">Cmd: `<Ctrl+RightArrow>`</span></span>
- <span data-ttu-id="f55fd-521">Режим вставки в VI: `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-521">Vi insert mode: `<Ctrl+RightArrow>`</span></span>
- <span data-ttu-id="f55fd-522">Режим команд VI: `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-522">Vi command mode: `<Ctrl+RightArrow>`</span></span>

### <a name="nextwordend"></a><span data-ttu-id="f55fd-523">некстворденд</span><span class="sxs-lookup"><span data-stu-id="f55fd-523">NextWordEnd</span></span>

<span data-ttu-id="f55fd-524">Переместить курсор вперед к концу текущего слова или между словами, до конца следующего слова.</span><span class="sxs-lookup"><span data-stu-id="f55fd-524">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="f55fd-525">Границы слов определяются с помощью настраиваемого набора символов.</span><span class="sxs-lookup"><span data-stu-id="f55fd-525">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="f55fd-526">Режим команд VI: `<e>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-526">Vi command mode: `<e>`</span></span>

### <a name="previousline"></a><span data-ttu-id="f55fd-527">превиауслине</span><span class="sxs-lookup"><span data-stu-id="f55fd-527">PreviousLine</span></span>

<span data-ttu-id="f55fd-528">Переместить курсор на предыдущую строку.</span><span class="sxs-lookup"><span data-stu-id="f55fd-528">Move the cursor to the previous line.</span></span>

- <span data-ttu-id="f55fd-529">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="f55fd-529">Function is unbound.</span></span>

### <a name="shellbackwardword"></a><span data-ttu-id="f55fd-530">шеллбакквардворд</span><span class="sxs-lookup"><span data-stu-id="f55fd-530">ShellBackwardWord</span></span>

<span data-ttu-id="f55fd-531">Перемещение курсора назад к началу текущего слова или между словами, с начала предыдущего слова.</span><span class="sxs-lookup"><span data-stu-id="f55fd-531">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="f55fd-532">Границы слов определяются токенами PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f55fd-532">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="f55fd-533">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="f55fd-533">Function is unbound.</span></span>

### <a name="shellforwardword"></a><span data-ttu-id="f55fd-534">шеллфорвардворд</span><span class="sxs-lookup"><span data-stu-id="f55fd-534">ShellForwardWord</span></span>

<span data-ttu-id="f55fd-535">Переместить курсор вперед к началу следующего слова.</span><span class="sxs-lookup"><span data-stu-id="f55fd-535">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="f55fd-536">Границы слов определяются токенами PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f55fd-536">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="f55fd-537">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="f55fd-537">Function is unbound.</span></span>

### <a name="shellnextword"></a><span data-ttu-id="f55fd-538">шеллнекстворд</span><span class="sxs-lookup"><span data-stu-id="f55fd-538">ShellNextWord</span></span>

<span data-ttu-id="f55fd-539">Переместить курсор вперед к концу текущего слова или между словами, до конца следующего слова.</span><span class="sxs-lookup"><span data-stu-id="f55fd-539">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="f55fd-540">Границы слов определяются токенами PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f55fd-540">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="f55fd-541">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="f55fd-541">Function is unbound.</span></span>

### <a name="vibackwardchar"></a><span data-ttu-id="f55fd-542">вибакквардчар</span><span class="sxs-lookup"><span data-stu-id="f55fd-542">ViBackwardChar</span></span>

<span data-ttu-id="f55fd-543">Переместить курсор на один символ влево в режиме редактирования VI.</span><span class="sxs-lookup"><span data-stu-id="f55fd-543">Move the cursor one character to the left in the Vi edit mode.</span></span> <span data-ttu-id="f55fd-544">Это может переместить курсор к предыдущей строке многострочного ввода.</span><span class="sxs-lookup"><span data-stu-id="f55fd-544">This may move the cursor to the previous line of multi-line input.</span></span>

- <span data-ttu-id="f55fd-545">Режим вставки в VI: `<LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-545">Vi insert mode: `<LeftArrow>`</span></span>
- <span data-ttu-id="f55fd-546">Режим команд VI: `<LeftArrow>` , `<Backspace>` , `<h>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-546">Vi command mode: `<LeftArrow>`, `<Backspace>`, `<h>`</span></span>

### <a name="vibackwardword"></a><span data-ttu-id="f55fd-547">вибакквардворд</span><span class="sxs-lookup"><span data-stu-id="f55fd-547">ViBackwardWord</span></span>

<span data-ttu-id="f55fd-548">Перемещение курсора назад к началу текущего слова или между словами, с начала предыдущего слова.</span><span class="sxs-lookup"><span data-stu-id="f55fd-548">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="f55fd-549">Границы слов определяются с помощью настраиваемого набора символов.</span><span class="sxs-lookup"><span data-stu-id="f55fd-549">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="f55fd-550">Режим команд VI: `<b>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-550">Vi command mode: `<b>`</span></span>

### <a name="viforwardchar"></a><span data-ttu-id="f55fd-551">вифорвардчар</span><span class="sxs-lookup"><span data-stu-id="f55fd-551">ViForwardChar</span></span>

<span data-ttu-id="f55fd-552">Переместить курсор на один символ вправо в режиме редактирования VI.</span><span class="sxs-lookup"><span data-stu-id="f55fd-552">Move the cursor one character to the right in the Vi edit mode.</span></span> <span data-ttu-id="f55fd-553">Это может переместить курсор на следующую строку многострочного ввода.</span><span class="sxs-lookup"><span data-stu-id="f55fd-553">This may move the cursor to the next line of multi-line input.</span></span>

- <span data-ttu-id="f55fd-554">Режим вставки в VI: `<RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-554">Vi insert mode: `<RightArrow>`</span></span>
- <span data-ttu-id="f55fd-555">Режим команд VI: `<RightArrow>` , `<Spacebar>` , `<l>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-555">Vi command mode: `<RightArrow>`, `<Spacebar>`, `<l>`</span></span>

### <a name="viendofglob"></a><span data-ttu-id="f55fd-556">виендофглоб</span><span class="sxs-lookup"><span data-stu-id="f55fd-556">ViEndOfGlob</span></span>

<span data-ttu-id="f55fd-557">Перемещает курсор в конец слова, используя только пробелы в качестве разделителей.</span><span class="sxs-lookup"><span data-stu-id="f55fd-557">Moves the cursor to the end of the word, using only white space as delimiters.</span></span>

- <span data-ttu-id="f55fd-558">Режим команд VI: `<E>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-558">Vi command mode: `<E>`</span></span>

### <a name="viendofpreviousglob"></a><span data-ttu-id="f55fd-559">виендофпревиаусглоб</span><span class="sxs-lookup"><span data-stu-id="f55fd-559">ViEndOfPreviousGlob</span></span>

<span data-ttu-id="f55fd-560">Переход к концу предыдущего слова с использованием только пробелов в качестве разделителя слов.</span><span class="sxs-lookup"><span data-stu-id="f55fd-560">Moves to the end of the previous word, using only white space as a word delimiter.</span></span>

- <span data-ttu-id="f55fd-561">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="f55fd-561">Function is unbound.</span></span>

### <a name="vigotobrace"></a><span data-ttu-id="f55fd-562">виготобраце</span><span class="sxs-lookup"><span data-stu-id="f55fd-562">ViGotoBrace</span></span>

<span data-ttu-id="f55fd-563">Аналогичен Готобраце, но является символом, а не основан на токене.</span><span class="sxs-lookup"><span data-stu-id="f55fd-563">Similar to GotoBrace, but is character based instead of token based.</span></span>

- <span data-ttu-id="f55fd-564">Режим команд VI: `<%>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-564">Vi command mode: `<%>`</span></span>

### <a name="vinextglob"></a><span data-ttu-id="f55fd-565">винекстглоб</span><span class="sxs-lookup"><span data-stu-id="f55fd-565">ViNextGlob</span></span>

<span data-ttu-id="f55fd-566">Переход к следующему слову с использованием только пробелов в качестве разделителя слов.</span><span class="sxs-lookup"><span data-stu-id="f55fd-566">Moves to the next word, using only white space as a word delimiter.</span></span>

- <span data-ttu-id="f55fd-567">Режим команд VI: `<W>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-567">Vi command mode: `<W>`</span></span>

### <a name="vinextword"></a><span data-ttu-id="f55fd-568">винекстворд</span><span class="sxs-lookup"><span data-stu-id="f55fd-568">ViNextWord</span></span>

<span data-ttu-id="f55fd-569">Переместить курсор вперед к началу следующего слова.</span><span class="sxs-lookup"><span data-stu-id="f55fd-569">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="f55fd-570">Границы слов определяются с помощью настраиваемого набора символов.</span><span class="sxs-lookup"><span data-stu-id="f55fd-570">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="f55fd-571">Режим команд VI: `<w>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-571">Vi command mode: `<w>`</span></span>

## <a name="history-functions"></a><span data-ttu-id="f55fd-572">Функции журнала</span><span class="sxs-lookup"><span data-stu-id="f55fd-572">History functions</span></span>

### <a name="beginningofhistory"></a><span data-ttu-id="f55fd-573">бегиннингофхистори</span><span class="sxs-lookup"><span data-stu-id="f55fd-573">BeginningOfHistory</span></span>

<span data-ttu-id="f55fd-574">Перейти к первому элементу в журнале.</span><span class="sxs-lookup"><span data-stu-id="f55fd-574">Move to the first item in the history.</span></span>

- <span data-ttu-id="f55fd-575">Emacs: `<Alt+<>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-575">Emacs: `<Alt+<>`</span></span>

### <a name="clearhistory"></a><span data-ttu-id="f55fd-576">клеархистори</span><span class="sxs-lookup"><span data-stu-id="f55fd-576">ClearHistory</span></span>

<span data-ttu-id="f55fd-577">Очищает журнал в PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="f55fd-577">Clears history in PSReadLine.</span></span> <span data-ttu-id="f55fd-578">Это не влияет на журнал PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f55fd-578">This does not affect PowerShell history.</span></span>

- <span data-ttu-id="f55fd-579">Процессор `<Alt+F7>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-579">Cmd: `<Alt+F7>`</span></span>

### <a name="endofhistory"></a><span data-ttu-id="f55fd-580">ендофхистори</span><span class="sxs-lookup"><span data-stu-id="f55fd-580">EndOfHistory</span></span>

<span data-ttu-id="f55fd-581">Переход к последнему элементу (текущему входному объекту) в журнале.</span><span class="sxs-lookup"><span data-stu-id="f55fd-581">Move to the last item (the current input) in the history.</span></span>

- <span data-ttu-id="f55fd-582">Emacs: `<Alt+>>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-582">Emacs: `<Alt+>>`</span></span>

### <a name="forwardsearchhistory"></a><span data-ttu-id="f55fd-583">форвардсеарчхистори</span><span class="sxs-lookup"><span data-stu-id="f55fd-583">ForwardSearchHistory</span></span>

<span data-ttu-id="f55fd-584">Выполните добавочный поиск по журналу.</span><span class="sxs-lookup"><span data-stu-id="f55fd-584">Perform an incremental forward search through history.</span></span>

- <span data-ttu-id="f55fd-585">Процессор `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-585">Cmd: `<Ctrl+s>`</span></span>
- <span data-ttu-id="f55fd-586">Emacs: `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-586">Emacs: `<Ctrl+s>`</span></span>

### <a name="historysearchbackward"></a><span data-ttu-id="f55fd-587">хисторисеарчбакквард</span><span class="sxs-lookup"><span data-stu-id="f55fd-587">HistorySearchBackward</span></span>

<span data-ttu-id="f55fd-588">Замените текущие входные данные элементом "Previous" из журнала PSReadLine, который соответствует символам между началом и входом и курсором.</span><span class="sxs-lookup"><span data-stu-id="f55fd-588">Replace the current input with the 'previous' item from PSReadLine history that matches the characters between the start and the input and the cursor.</span></span>

- <span data-ttu-id="f55fd-589">Процессор `<F8>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-589">Cmd: `<F8>`</span></span>

### <a name="historysearchforward"></a><span data-ttu-id="f55fd-590">хисторисеарчфорвард</span><span class="sxs-lookup"><span data-stu-id="f55fd-590">HistorySearchForward</span></span>

<span data-ttu-id="f55fd-591">Замените текущие входные данные элементом "Next" из журнала PSReadLine, который соответствует символам между началом и входом и курсором.</span><span class="sxs-lookup"><span data-stu-id="f55fd-591">Replace the current input with the 'next' item from PSReadLine history that matches the characters between the start and the input and the cursor.</span></span>

- <span data-ttu-id="f55fd-592">Процессор `<Shift+F8>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-592">Cmd: `<Shift+F8>`</span></span>

### <a name="nexthistory"></a><span data-ttu-id="f55fd-593">некссистори</span><span class="sxs-lookup"><span data-stu-id="f55fd-593">NextHistory</span></span>

<span data-ttu-id="f55fd-594">Замените текущие входные данные на элемент "Next" из журнала PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="f55fd-594">Replace the current input with the 'next' item from PSReadLine history.</span></span>

- <span data-ttu-id="f55fd-595">Процессор `<DownArrow>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-595">Cmd: `<DownArrow>`</span></span>
- <span data-ttu-id="f55fd-596">Emacs: `<DownArrow>` , `<Ctrl+n>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-596">Emacs: `<DownArrow>`, `<Ctrl+n>`</span></span>
- <span data-ttu-id="f55fd-597">Режим вставки в VI: `<DownArrow>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-597">Vi insert mode: `<DownArrow>`</span></span>
- <span data-ttu-id="f55fd-598">Режим команд VI: `<DownArrow>` , `<j>` , `<+>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-598">Vi command mode: `<DownArrow>`, `<j>`, `<+>`</span></span>

### <a name="previoushistory"></a><span data-ttu-id="f55fd-599">превиаушистори</span><span class="sxs-lookup"><span data-stu-id="f55fd-599">PreviousHistory</span></span>

<span data-ttu-id="f55fd-600">Замените текущие входные данные элементом "Previous" из журнала PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="f55fd-600">Replace the current input with the 'previous' item from PSReadLine history.</span></span>

- <span data-ttu-id="f55fd-601">Процессор `<UpArrow>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-601">Cmd: `<UpArrow>`</span></span>
- <span data-ttu-id="f55fd-602">Emacs: `<UpArrow>` , `<Ctrl+p>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-602">Emacs: `<UpArrow>`, `<Ctrl+p>`</span></span>
- <span data-ttu-id="f55fd-603">Режим вставки в VI: `<UpArrow>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-603">Vi insert mode: `<UpArrow>`</span></span>
- <span data-ttu-id="f55fd-604">Режим команд VI: `<UpArrow>` , `<k>` , `<->`</span><span class="sxs-lookup"><span data-stu-id="f55fd-604">Vi command mode: `<UpArrow>`, `<k>`, `<->`</span></span>

### <a name="reversesearchhistory"></a><span data-ttu-id="f55fd-605">реверсесеарчхистори</span><span class="sxs-lookup"><span data-stu-id="f55fd-605">ReverseSearchHistory</span></span>

<span data-ttu-id="f55fd-606">Выполните добавочный поиск по журналу.</span><span class="sxs-lookup"><span data-stu-id="f55fd-606">Perform an incremental backward search through history.</span></span>

- <span data-ttu-id="f55fd-607">Процессор `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-607">Cmd: `<Ctrl+r>`</span></span>
- <span data-ttu-id="f55fd-608">Emacs: `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-608">Emacs: `<Ctrl+r>`</span></span>

### <a name="visearchhistorybackward"></a><span data-ttu-id="f55fd-609">висеарчхисторибакквард</span><span class="sxs-lookup"><span data-stu-id="f55fd-609">ViSearchHistoryBackward</span></span>

<span data-ttu-id="f55fd-610">Запрашивает строку поиска и инициирует поиск по запросу Акцептлине.</span><span class="sxs-lookup"><span data-stu-id="f55fd-610">Prompts for a search string and initiates search upon AcceptLine.</span></span>

- <span data-ttu-id="f55fd-611">Режим вставки в VI: `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-611">Vi insert mode: `<Ctrl+r>`</span></span>
- <span data-ttu-id="f55fd-612">Режим команд VI: `</>` , `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-612">Vi command mode: `</>`, `<Ctrl+r>`</span></span>

## <a name="completion-functions"></a><span data-ttu-id="f55fd-613">Функции завершения</span><span class="sxs-lookup"><span data-stu-id="f55fd-613">Completion functions</span></span>

### <a name="complete"></a><span data-ttu-id="f55fd-614">Завершить</span><span class="sxs-lookup"><span data-stu-id="f55fd-614">Complete</span></span>

<span data-ttu-id="f55fd-615">Попытка выполнить завершение в тексте, окружающем курсор.</span><span class="sxs-lookup"><span data-stu-id="f55fd-615">Attempt to perform completion on the text surrounding the cursor.</span></span> <span data-ttu-id="f55fd-616">Если существует несколько возможных завершений, для завершения используется самый длинный ненеоднозначный префикс.</span><span class="sxs-lookup"><span data-stu-id="f55fd-616">If there are multiple possible completions, the longest unambiguous prefix is used for completion.</span></span> <span data-ttu-id="f55fd-617">При попытке выполнить наибольшее неоднозначное Завершение отображается список возможных завершений.</span><span class="sxs-lookup"><span data-stu-id="f55fd-617">If trying to complete the longest unambiguous completion, a list of possible completions is displayed.</span></span>

- <span data-ttu-id="f55fd-618">Emacs: `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-618">Emacs: `<Tab>`</span></span>

### <a name="menucomplete"></a><span data-ttu-id="f55fd-619">менукомплете</span><span class="sxs-lookup"><span data-stu-id="f55fd-619">MenuComplete</span></span>

<span data-ttu-id="f55fd-620">Попытка выполнить завершение в тексте, окружающем курсор.</span><span class="sxs-lookup"><span data-stu-id="f55fd-620">Attempt to perform completion on the text surrounding the cursor.</span></span> <span data-ttu-id="f55fd-621">Если существует несколько возможных завершений, для завершения используется самый длинный ненеоднозначный префикс.</span><span class="sxs-lookup"><span data-stu-id="f55fd-621">If there are multiple possible completions, the longest unambiguous prefix is used for completion.</span></span> <span data-ttu-id="f55fd-622">При попытке выполнить наибольшее неоднозначное Завершение отображается список возможных завершений.</span><span class="sxs-lookup"><span data-stu-id="f55fd-622">If trying to complete the longest unambiguous completion, a list of possible completions is displayed.</span></span>

- <span data-ttu-id="f55fd-623">Cmd: `<Ctrl+@>` , `<Ctrl+Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-623">Cmd: `<Ctrl+@>`, `<Ctrl+Spacebar>`</span></span>
- <span data-ttu-id="f55fd-624">Emacs: `<Ctrl+Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-624">Emacs: `<Ctrl+Spacebar>`</span></span>

### <a name="possiblecompletions"></a><span data-ttu-id="f55fd-625">поссиблекомплетионс</span><span class="sxs-lookup"><span data-stu-id="f55fd-625">PossibleCompletions</span></span>

<span data-ttu-id="f55fd-626">Отображение списка возможных завершений.</span><span class="sxs-lookup"><span data-stu-id="f55fd-626">Display the list of possible completions.</span></span>

- <span data-ttu-id="f55fd-627">Emacs: `<Alt+=>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-627">Emacs: `<Alt+=>`</span></span>
- <span data-ttu-id="f55fd-628">Режим вставки в VI: `<Ctrl+Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-628">Vi insert mode: `<Ctrl+Spacebar>`</span></span>
- <span data-ttu-id="f55fd-629">Режим команд VI: `<Ctrl+Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-629">Vi command mode: `<Ctrl+Spacebar>`</span></span>

### <a name="tabcompletenext"></a><span data-ttu-id="f55fd-630">табкомплетенекст</span><span class="sxs-lookup"><span data-stu-id="f55fd-630">TabCompleteNext</span></span>

<span data-ttu-id="f55fd-631">Попытайтесь завершить текст, окружающий курсор, с помощью следующего доступного завершения.</span><span class="sxs-lookup"><span data-stu-id="f55fd-631">Attempt to complete the text surrounding the cursor with the next available completion.</span></span>

- <span data-ttu-id="f55fd-632">Процессор `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-632">Cmd: `<Tab>`</span></span>
- <span data-ttu-id="f55fd-633">Режим команд VI: `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-633">Vi command mode: `<Tab>`</span></span>

### <a name="tabcompleteprevious"></a><span data-ttu-id="f55fd-634">табкомплетепревиаус</span><span class="sxs-lookup"><span data-stu-id="f55fd-634">TabCompletePrevious</span></span>

<span data-ttu-id="f55fd-635">Попытайтесь завершить текст, окружающий курсор, с предыдущим доступным завершением.</span><span class="sxs-lookup"><span data-stu-id="f55fd-635">Attempt to complete the text surrounding the cursor with the previous available completion.</span></span>

- <span data-ttu-id="f55fd-636">Процессор `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-636">Cmd: `<Shift+Tab>`</span></span>
- <span data-ttu-id="f55fd-637">Режим команд VI: `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-637">Vi command mode: `<Shift+Tab>`</span></span>

### <a name="vitabcompletenext"></a><span data-ttu-id="f55fd-638">витабкомплетенекст</span><span class="sxs-lookup"><span data-stu-id="f55fd-638">ViTabCompleteNext</span></span>

<span data-ttu-id="f55fd-639">При необходимости завершает текущую группу редактирования и вызывает Табкомплетенекст.</span><span class="sxs-lookup"><span data-stu-id="f55fd-639">Ends the current edit group, if needed, and invokes TabCompleteNext.</span></span>

- <span data-ttu-id="f55fd-640">Режим вставки в VI: `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-640">Vi insert mode: `<Tab>`</span></span>

### <a name="vitabcompleteprevious"></a><span data-ttu-id="f55fd-641">витабкомплетепревиаус</span><span class="sxs-lookup"><span data-stu-id="f55fd-641">ViTabCompletePrevious</span></span>

<span data-ttu-id="f55fd-642">При необходимости завершает текущую группу редактирования и вызывает Табкомплетепревиаус.</span><span class="sxs-lookup"><span data-stu-id="f55fd-642">Ends the current edit group, if needed, and invokes TabCompletePrevious.</span></span>

- <span data-ttu-id="f55fd-643">Режим вставки в VI: `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-643">Vi insert mode: `<Shift+Tab>`</span></span>

## <a name="prediction-functions"></a><span data-ttu-id="f55fd-644">Прогнозирующие функции</span><span class="sxs-lookup"><span data-stu-id="f55fd-644">Prediction functions</span></span>

### <a name="acceptnextsuggestionword"></a><span data-ttu-id="f55fd-645">акцептнекстсугжестионворд</span><span class="sxs-lookup"><span data-stu-id="f55fd-645">AcceptNextSuggestionWord</span></span>

<span data-ttu-id="f55fd-646">При использовании `InlineView` в качестве стиля представления для прогноза примите следующее слово встроенного предложения.</span><span class="sxs-lookup"><span data-stu-id="f55fd-646">When using `InlineView` as the view style for prediction, accept the next word of the inline suggestion.</span></span>

- <span data-ttu-id="f55fd-647">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="f55fd-647">Function is unbound.</span></span>

### <a name="acceptsuggestion"></a><span data-ttu-id="f55fd-648">акцептсугжестион</span><span class="sxs-lookup"><span data-stu-id="f55fd-648">AcceptSuggestion</span></span>

<span data-ttu-id="f55fd-649">При использовании `InlineView` в качестве стиля представления для прогноза примите текущее встроенное предложение.</span><span class="sxs-lookup"><span data-stu-id="f55fd-649">When using `InlineView` as the view style for prediction, accept the current inline suggestion.</span></span>

- <span data-ttu-id="f55fd-650">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="f55fd-650">Function is unbound.</span></span>

### <a name="nextsuggestion"></a><span data-ttu-id="f55fd-651">некстсугжестион</span><span class="sxs-lookup"><span data-stu-id="f55fd-651">NextSuggestion</span></span>

<span data-ttu-id="f55fd-652">При использовании в `ListView` качестве стиля представления для прогноза перейдите к следующему предложению в списке.</span><span class="sxs-lookup"><span data-stu-id="f55fd-652">When using `ListView` as the view style for prediction, navigate to the next suggestion in the list.</span></span>

- <span data-ttu-id="f55fd-653">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="f55fd-653">Function is unbound.</span></span>

### <a name="previoussuggestion"></a><span data-ttu-id="f55fd-654">превиауссугжестион</span><span class="sxs-lookup"><span data-stu-id="f55fd-654">PreviousSuggestion</span></span>

<span data-ttu-id="f55fd-655">При использовании в `ListView` качестве стиля представления для прогноза перейдите к предыдущему предложению в списке.</span><span class="sxs-lookup"><span data-stu-id="f55fd-655">When using `ListView` as the view style for prediction, navigate to the previous suggestion in the list.</span></span>

- <span data-ttu-id="f55fd-656">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="f55fd-656">Function is unbound.</span></span>

### <a name="switchpredictionview"></a><span data-ttu-id="f55fd-657">свитчпредиктионвиев</span><span class="sxs-lookup"><span data-stu-id="f55fd-657">SwitchPredictionView</span></span>

<span data-ttu-id="f55fd-658">Переключите стиль представления для прогнозирования между `InlineView` и `ListView` .</span><span class="sxs-lookup"><span data-stu-id="f55fd-658">Switch the view style for prediction between `InlineView` and `ListView`.</span></span>

- <span data-ttu-id="f55fd-659">Процессор `<F2>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-659">Cmd: `<F2>`</span></span>

## <a name="miscellaneous-functions"></a><span data-ttu-id="f55fd-660">Прочие функции</span><span class="sxs-lookup"><span data-stu-id="f55fd-660">Miscellaneous functions</span></span>

### <a name="capturescreen"></a><span data-ttu-id="f55fd-661">каптурескрин</span><span class="sxs-lookup"><span data-stu-id="f55fd-661">CaptureScreen</span></span>

<span data-ttu-id="f55fd-662">Запуск интерактивной записи экрана — стрелки вверх и вниз выбор строк, ввод копирует выделенный текст в буфер обмена в виде текста и HTML.</span><span class="sxs-lookup"><span data-stu-id="f55fd-662">Start interactive screen capture - up/down arrows select lines, enter copies selected text to clipboard as text and html.</span></span>

- <span data-ttu-id="f55fd-663">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="f55fd-663">Function is unbound.</span></span>

### <a name="clearscreen"></a><span data-ttu-id="f55fd-664">клеарскрин</span><span class="sxs-lookup"><span data-stu-id="f55fd-664">ClearScreen</span></span>

<span data-ttu-id="f55fd-665">Очистить экран и нарисовать текущую строку в верхней части экрана.</span><span class="sxs-lookup"><span data-stu-id="f55fd-665">Clear the screen and draw the current line at the top of the screen.</span></span>

- <span data-ttu-id="f55fd-666">Процессор `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-666">Cmd: `<Ctrl+l>`</span></span>
- <span data-ttu-id="f55fd-667">Emacs: `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-667">Emacs: `<Ctrl+l>`</span></span>
- <span data-ttu-id="f55fd-668">Режим вставки в VI: `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-668">Vi insert mode: `<Ctrl+l>`</span></span>
- <span data-ttu-id="f55fd-669">Режим команд VI: `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-669">Vi command mode: `<Ctrl+l>`</span></span>

### <a name="digitargument"></a><span data-ttu-id="f55fd-670">дигитаргумент</span><span class="sxs-lookup"><span data-stu-id="f55fd-670">DigitArgument</span></span>

<span data-ttu-id="f55fd-671">Начните новый аргумент цифры для передачи другим функциям.</span><span class="sxs-lookup"><span data-stu-id="f55fd-671">Start a new digit argument to pass to other functions.</span></span>

- <span data-ttu-id="f55fd-672">Cmd: `<Alt+0>` , `<Alt+1>` , `<Alt+2>` , `<Alt+3>` , `<Alt+4>` , `<Alt+5>` , `<Alt+6>` , `<Alt+7>` , `<Alt+8>` , `<Alt+9>` , `<Alt+->`</span><span class="sxs-lookup"><span data-stu-id="f55fd-672">Cmd: `<Alt+0>`, `<Alt+1>`, `<Alt+2>`, `<Alt+3>`, `<Alt+4>`, `<Alt+5>`, `<Alt+6>`, `<Alt+7>`, `<Alt+8>`, `<Alt+9>`, `<Alt+->`</span></span>
- <span data-ttu-id="f55fd-673">Emacs: `<Alt+0>` , `<Alt+1>` , `<Alt+2>` , `<Alt+3>` , `<Alt+4>` , `<Alt+5>` , `<Alt+6>` , `<Alt+7>` , `<Alt+8>` , `<Alt+9>` , `<Alt+->`</span><span class="sxs-lookup"><span data-stu-id="f55fd-673">Emacs: `<Alt+0>`, `<Alt+1>`, `<Alt+2>`, `<Alt+3>`, `<Alt+4>`, `<Alt+5>`, `<Alt+6>`, `<Alt+7>`, `<Alt+8>`, `<Alt+9>`, `<Alt+->`</span></span>
- <span data-ttu-id="f55fd-674">Режим команд VI: `<0>` , `<1>` , `<2>` , `<3>` , `<4>` , `<5>` , `<6>` , `<7>` , `<8>` , `<9>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-674">Vi command mode: `<0>`, `<1>`, `<2>`, `<3>`, `<4>`, `<5>`, `<6>`, `<7>`, `<8>`, `<9>`</span></span>

### <a name="invokeprompt"></a><span data-ttu-id="f55fd-675">инвокепромпт</span><span class="sxs-lookup"><span data-stu-id="f55fd-675">InvokePrompt</span></span>

<span data-ttu-id="f55fd-676">Стирает текущий запрос и вызывает функцию Prompt для повторного вывода запроса.</span><span class="sxs-lookup"><span data-stu-id="f55fd-676">Erases the current prompt and calls the prompt function to redisplay the prompt.</span></span> <span data-ttu-id="f55fd-677">Полезен для обработчиков пользовательских ключей, изменяющих состояние, например для изменения текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="f55fd-677">Useful for custom key handlers that change state, e.g. change the current directory.</span></span>

- <span data-ttu-id="f55fd-678">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="f55fd-678">Function is unbound.</span></span>

### <a name="scrolldisplaydown"></a><span data-ttu-id="f55fd-679">скроллдисплайдовн</span><span class="sxs-lookup"><span data-stu-id="f55fd-679">ScrollDisplayDown</span></span>

<span data-ttu-id="f55fd-680">Прокрутите экран вниз на один экран.</span><span class="sxs-lookup"><span data-stu-id="f55fd-680">Scroll the display down one screen.</span></span>

- <span data-ttu-id="f55fd-681">Процессор `<PageDown>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-681">Cmd: `<PageDown>`</span></span>
- <span data-ttu-id="f55fd-682">Emacs: `<PageDown>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-682">Emacs: `<PageDown>`</span></span>

### <a name="scrolldisplaydownline"></a><span data-ttu-id="f55fd-683">скроллдисплайдовнлине</span><span class="sxs-lookup"><span data-stu-id="f55fd-683">ScrollDisplayDownLine</span></span>

<span data-ttu-id="f55fd-684">Прокрутите экран вниз на одну строку.</span><span class="sxs-lookup"><span data-stu-id="f55fd-684">Scroll the display down one line.</span></span>

- <span data-ttu-id="f55fd-685">Процессор `<Ctrl+PageDown>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-685">Cmd: `<Ctrl+PageDown>`</span></span>
- <span data-ttu-id="f55fd-686">Emacs: `<Ctrl+PageDown>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-686">Emacs: `<Ctrl+PageDown>`</span></span>

### <a name="scrolldisplaytocursor"></a><span data-ttu-id="f55fd-687">скроллдисплайтокурсор</span><span class="sxs-lookup"><span data-stu-id="f55fd-687">ScrollDisplayToCursor</span></span>

<span data-ttu-id="f55fd-688">Прокрутить экран до курсора.</span><span class="sxs-lookup"><span data-stu-id="f55fd-688">Scroll the display to the cursor.</span></span>

- <span data-ttu-id="f55fd-689">Emacs: `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-689">Emacs: `<Ctrl+End>`</span></span>

### <a name="scrolldisplaytop"></a><span data-ttu-id="f55fd-690">скроллдисплайтоп</span><span class="sxs-lookup"><span data-stu-id="f55fd-690">ScrollDisplayTop</span></span>

<span data-ttu-id="f55fd-691">Прокрутите экран до верха.</span><span class="sxs-lookup"><span data-stu-id="f55fd-691">Scroll the display to the top.</span></span>

- <span data-ttu-id="f55fd-692">Emacs: `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-692">Emacs: `<Ctrl+Home>`</span></span>

### <a name="scrolldisplayup"></a><span data-ttu-id="f55fd-693">скроллдисплайуп</span><span class="sxs-lookup"><span data-stu-id="f55fd-693">ScrollDisplayUp</span></span>

<span data-ttu-id="f55fd-694">Прокрутите экран вверх на один экран.</span><span class="sxs-lookup"><span data-stu-id="f55fd-694">Scroll the display up one screen.</span></span>

- <span data-ttu-id="f55fd-695">Процессор `<PageUp>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-695">Cmd: `<PageUp>`</span></span>
- <span data-ttu-id="f55fd-696">Emacs: `<PageUp>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-696">Emacs: `<PageUp>`</span></span>

### <a name="scrolldisplayupline"></a><span data-ttu-id="f55fd-697">скроллдисплайуплине</span><span class="sxs-lookup"><span data-stu-id="f55fd-697">ScrollDisplayUpLine</span></span>

<span data-ttu-id="f55fd-698">Прокрутите экран вверх на одну строку.</span><span class="sxs-lookup"><span data-stu-id="f55fd-698">Scroll the display up one line.</span></span>

- <span data-ttu-id="f55fd-699">Процессор `<Ctrl+PageUp>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-699">Cmd: `<Ctrl+PageUp>`</span></span>
- <span data-ttu-id="f55fd-700">Emacs: `<Ctrl+PageUp>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-700">Emacs: `<Ctrl+PageUp>`</span></span>

### <a name="selfinsert"></a><span data-ttu-id="f55fd-701">селфинсерт</span><span class="sxs-lookup"><span data-stu-id="f55fd-701">SelfInsert</span></span>

<span data-ttu-id="f55fd-702">Вставьте ключ.</span><span class="sxs-lookup"><span data-stu-id="f55fd-702">Insert the key.</span></span>

- <span data-ttu-id="f55fd-703">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="f55fd-703">Function is unbound.</span></span>

### <a name="showcommandhelp"></a><span data-ttu-id="f55fd-704">шовкоммандхелп</span><span class="sxs-lookup"><span data-stu-id="f55fd-704">ShowCommandHelp</span></span>

<span data-ttu-id="f55fd-705">Предоставляет представление полной справки по командлетам для альтернативного буфера экрана с помощью пейджера из **Microsoft. PowerShell. пейджер**.</span><span class="sxs-lookup"><span data-stu-id="f55fd-705">Provides a view of full cmdlet help on alternate screen buffer using a Pager from **Microsoft.PowerShell.Pager**.</span></span>

- <span data-ttu-id="f55fd-706">Процессор `<F1>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-706">Cmd: `<F1>`</span></span>
- <span data-ttu-id="f55fd-707">Emacs: `<F1>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-707">Emacs: `<F1>`</span></span>
- <span data-ttu-id="f55fd-708">Режим вставки в VI: `<F1>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-708">Vi insert mode: `<F1>`</span></span>
- <span data-ttu-id="f55fd-709">Режим команд VI: `<F1>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-709">Vi command mode: `<F1>`</span></span>

### <a name="showkeybindings"></a><span data-ttu-id="f55fd-710">шовкэйбиндингс</span><span class="sxs-lookup"><span data-stu-id="f55fd-710">ShowKeyBindings</span></span>

<span data-ttu-id="f55fd-711">Отображение всех связанных ключей.</span><span class="sxs-lookup"><span data-stu-id="f55fd-711">Show all bound keys.</span></span>

- <span data-ttu-id="f55fd-712">Процессор `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-712">Cmd: `<Ctrl+Alt+?>`</span></span>
- <span data-ttu-id="f55fd-713">Emacs: `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-713">Emacs: `<Ctrl+Alt+?>`</span></span>
- <span data-ttu-id="f55fd-714">Режим вставки в VI: `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-714">Vi insert mode: `<Ctrl+Alt+?>`</span></span>

### <a name="showparameterhelp"></a><span data-ttu-id="f55fd-715">шовпараметерхелп</span><span class="sxs-lookup"><span data-stu-id="f55fd-715">ShowParameterHelp</span></span>

<span data-ttu-id="f55fd-716">Предоставляет динамическую справку по параметрам, отображая ее под текущей командной строкой, например `MenuComplete` .</span><span class="sxs-lookup"><span data-stu-id="f55fd-716">Provides dynamic help for parameters by showing it below the current command line like `MenuComplete`.</span></span>

- <span data-ttu-id="f55fd-717">Процессор `<Alt+h>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-717">Cmd: `<Alt+h>`</span></span>
- <span data-ttu-id="f55fd-718">Emacs: `<Alt+h>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-718">Emacs: `<Alt+h>`</span></span>
- <span data-ttu-id="f55fd-719">Режим вставки в VI: `<Alt+h>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-719">Vi insert mode: `<Alt+h>`</span></span>
- <span data-ttu-id="f55fd-720">Режим команд VI: `<Alt+h>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-720">Vi command mode: `<Alt+h>`</span></span>

### <a name="vicommandmode"></a><span data-ttu-id="f55fd-721">викоммандмоде</span><span class="sxs-lookup"><span data-stu-id="f55fd-721">ViCommandMode</span></span>

<span data-ttu-id="f55fd-722">Переключите текущий режим работы с Vi-Insert на VI-Command.</span><span class="sxs-lookup"><span data-stu-id="f55fd-722">Switch the current operating mode from Vi-Insert to Vi-Command.</span></span>

- <span data-ttu-id="f55fd-723">Режим вставки в VI: `<Escape>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-723">Vi insert mode: `<Escape>`</span></span>

### <a name="vidigitargumentinchord"></a><span data-ttu-id="f55fd-724">видигитаргументинчорд</span><span class="sxs-lookup"><span data-stu-id="f55fd-724">ViDigitArgumentInChord</span></span>

<span data-ttu-id="f55fd-725">Начните новый числовой аргумент, чтобы передать его другим функциям в одной из сочетаний VI.</span><span class="sxs-lookup"><span data-stu-id="f55fd-725">Start a new digit argument to pass to other functions while in one of vi's chords.</span></span>

- <span data-ttu-id="f55fd-726">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="f55fd-726">Function is unbound.</span></span>

### <a name="vieditvisually"></a><span data-ttu-id="f55fd-727">виедитвисуалли</span><span class="sxs-lookup"><span data-stu-id="f55fd-727">ViEditVisually</span></span>

<span data-ttu-id="f55fd-728">Измените командную строку в текстовом редакторе, заданном $env: EDITOR или $env: VISUAL.</span><span class="sxs-lookup"><span data-stu-id="f55fd-728">Edit the command line in a text editor specified by $env:EDITOR or $env:VISUAL.</span></span>

- <span data-ttu-id="f55fd-729">Emacs: `<Ctrl+x,Ctrl+e>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-729">Emacs: `<Ctrl+x,Ctrl+e>`</span></span>
- <span data-ttu-id="f55fd-730">Режим команд VI: `<v>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-730">Vi command mode: `<v>`</span></span>

### <a name="viexit"></a><span data-ttu-id="f55fd-731">виексит</span><span class="sxs-lookup"><span data-stu-id="f55fd-731">ViExit</span></span>

<span data-ttu-id="f55fd-732">Завершает работу оболочки.</span><span class="sxs-lookup"><span data-stu-id="f55fd-732">Exits the shell.</span></span>

- <span data-ttu-id="f55fd-733">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="f55fd-733">Function is unbound.</span></span>

### <a name="viinsertmode"></a><span data-ttu-id="f55fd-734">виинсертмоде</span><span class="sxs-lookup"><span data-stu-id="f55fd-734">ViInsertMode</span></span>

<span data-ttu-id="f55fd-735">Переключитесь в режим вставки.</span><span class="sxs-lookup"><span data-stu-id="f55fd-735">Switch to Insert mode.</span></span>

- <span data-ttu-id="f55fd-736">Режим команд VI: `<i>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-736">Vi command mode: `<i>`</span></span>

### <a name="whatiskey"></a><span data-ttu-id="f55fd-737">вхатискэй</span><span class="sxs-lookup"><span data-stu-id="f55fd-737">WhatIsKey</span></span>

<span data-ttu-id="f55fd-738">Прочитайте ключ и расскажите, к чему привязан ключ.</span><span class="sxs-lookup"><span data-stu-id="f55fd-738">Read a key and tell me what the key is bound to.</span></span>

- <span data-ttu-id="f55fd-739">Процессор `<Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-739">Cmd: `<Alt+?>`</span></span>
- <span data-ttu-id="f55fd-740">Emacs: `<Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-740">Emacs: `<Alt+?>`</span></span>

## <a name="selection-functions"></a><span data-ttu-id="f55fd-741">Функции выбора</span><span class="sxs-lookup"><span data-stu-id="f55fd-741">Selection functions</span></span>

### <a name="exchangepointandmark"></a><span data-ttu-id="f55fd-742">ексчанжепоинтандмарк</span><span class="sxs-lookup"><span data-stu-id="f55fd-742">ExchangePointAndMark</span></span>

<span data-ttu-id="f55fd-743">Курсор помещается в позицию метки, а метка перемещается в положение курсора.</span><span class="sxs-lookup"><span data-stu-id="f55fd-743">The cursor is placed at the location of the mark and the mark is moved to the location of the cursor.</span></span>

- <span data-ttu-id="f55fd-744">Emacs: `<Ctrl+x,Ctrl+x>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-744">Emacs: `<Ctrl+x,Ctrl+x>`</span></span>

### <a name="selectall"></a><span data-ttu-id="f55fd-745">SelectAll</span><span class="sxs-lookup"><span data-stu-id="f55fd-745">SelectAll</span></span>

<span data-ttu-id="f55fd-746">Выделите всю строку.</span><span class="sxs-lookup"><span data-stu-id="f55fd-746">Select the entire line.</span></span>

- <span data-ttu-id="f55fd-747">Процессор `<Ctrl+a>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-747">Cmd: `<Ctrl+a>`</span></span>

### <a name="selectbackwardchar"></a><span data-ttu-id="f55fd-748">селектбакквардчар</span><span class="sxs-lookup"><span data-stu-id="f55fd-748">SelectBackwardChar</span></span>

<span data-ttu-id="f55fd-749">Настройка текущего выделения для включения предыдущего символа.</span><span class="sxs-lookup"><span data-stu-id="f55fd-749">Adjust the current selection to include the previous character.</span></span>

- <span data-ttu-id="f55fd-750">Процессор `<Shift+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-750">Cmd: `<Shift+LeftArrow>`</span></span>
- <span data-ttu-id="f55fd-751">Emacs: `<Shift+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-751">Emacs: `<Shift+LeftArrow>`</span></span>

### <a name="selectbackwardsline"></a><span data-ttu-id="f55fd-752">селектбакквардслине</span><span class="sxs-lookup"><span data-stu-id="f55fd-752">SelectBackwardsLine</span></span>

<span data-ttu-id="f55fd-753">Изменить текущее выделение, чтобы включить его от курсора до начала строки.</span><span class="sxs-lookup"><span data-stu-id="f55fd-753">Adjust the current selection to include from the cursor to the start of the line.</span></span>

- <span data-ttu-id="f55fd-754">Процессор `<Shift+Home>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-754">Cmd: `<Shift+Home>`</span></span>
- <span data-ttu-id="f55fd-755">Emacs: `<Shift+Home>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-755">Emacs: `<Shift+Home>`</span></span>

### <a name="selectbackwardword"></a><span data-ttu-id="f55fd-756">селектбакквардворд</span><span class="sxs-lookup"><span data-stu-id="f55fd-756">SelectBackwardWord</span></span>

<span data-ttu-id="f55fd-757">Настройка текущего выделения для включения предыдущего слова.</span><span class="sxs-lookup"><span data-stu-id="f55fd-757">Adjust the current selection to include the previous word.</span></span>

- <span data-ttu-id="f55fd-758">Процессор `<Shift+Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-758">Cmd: `<Shift+Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="f55fd-759">Emacs: `<Alt+B>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-759">Emacs: `<Alt+B>`</span></span>

### <a name="selectforwardchar"></a><span data-ttu-id="f55fd-760">селектфорвардчар</span><span class="sxs-lookup"><span data-stu-id="f55fd-760">SelectForwardChar</span></span>

<span data-ttu-id="f55fd-761">Измените текущее выделение, чтобы включить следующий символ.</span><span class="sxs-lookup"><span data-stu-id="f55fd-761">Adjust the current selection to include the next character.</span></span>

- <span data-ttu-id="f55fd-762">Процессор `<Shift+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-762">Cmd: `<Shift+RightArrow>`</span></span>
- <span data-ttu-id="f55fd-763">Emacs: `<Shift+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-763">Emacs: `<Shift+RightArrow>`</span></span>

### <a name="selectforwardword"></a><span data-ttu-id="f55fd-764">селектфорвардворд</span><span class="sxs-lookup"><span data-stu-id="f55fd-764">SelectForwardWord</span></span>

<span data-ttu-id="f55fd-765">Измените текущее выделение, чтобы включить следующее слово с помощью Форвардворд.</span><span class="sxs-lookup"><span data-stu-id="f55fd-765">Adjust the current selection to include the next word using ForwardWord.</span></span>

- <span data-ttu-id="f55fd-766">Emacs: `<Alt+F>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-766">Emacs: `<Alt+F>`</span></span>

### <a name="selectline"></a><span data-ttu-id="f55fd-767">селектлине</span><span class="sxs-lookup"><span data-stu-id="f55fd-767">SelectLine</span></span>

<span data-ttu-id="f55fd-768">Настройка текущего выделения для включения курсора в конец строки.</span><span class="sxs-lookup"><span data-stu-id="f55fd-768">Adjust the current selection to include from the cursor to the end of the line.</span></span>

- <span data-ttu-id="f55fd-769">Процессор `<Shift+End>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-769">Cmd: `<Shift+End>`</span></span>
- <span data-ttu-id="f55fd-770">Emacs: `<Shift+End>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-770">Emacs: `<Shift+End>`</span></span>

### <a name="selectnextword"></a><span data-ttu-id="f55fd-771">селектнекстворд</span><span class="sxs-lookup"><span data-stu-id="f55fd-771">SelectNextWord</span></span>

<span data-ttu-id="f55fd-772">Настройка текущего выделения для включения следующего слова.</span><span class="sxs-lookup"><span data-stu-id="f55fd-772">Adjust the current selection to include the next word.</span></span>

- <span data-ttu-id="f55fd-773">Процессор `<Shift+Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-773">Cmd: `<Shift+Ctrl+RightArrow>`</span></span>

### <a name="selectshellbackwardword"></a><span data-ttu-id="f55fd-774">селектшеллбакквардворд</span><span class="sxs-lookup"><span data-stu-id="f55fd-774">SelectShellBackwardWord</span></span>

<span data-ttu-id="f55fd-775">Измените текущее выделение, чтобы включить предыдущее слово с помощью Шеллбакквардворд.</span><span class="sxs-lookup"><span data-stu-id="f55fd-775">Adjust the current selection to include the previous word using ShellBackwardWord.</span></span>

- <span data-ttu-id="f55fd-776">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="f55fd-776">Function is unbound.</span></span>

### <a name="selectshellforwardword"></a><span data-ttu-id="f55fd-777">селектшеллфорвардворд</span><span class="sxs-lookup"><span data-stu-id="f55fd-777">SelectShellForwardWord</span></span>

<span data-ttu-id="f55fd-778">Измените текущее выделение, чтобы включить следующее слово с помощью Шеллфорвардворд.</span><span class="sxs-lookup"><span data-stu-id="f55fd-778">Adjust the current selection to include the next word using ShellForwardWord.</span></span>

- <span data-ttu-id="f55fd-779">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="f55fd-779">Function is unbound.</span></span>

### <a name="selectshellnextword"></a><span data-ttu-id="f55fd-780">селектшеллнекстворд</span><span class="sxs-lookup"><span data-stu-id="f55fd-780">SelectShellNextWord</span></span>

<span data-ttu-id="f55fd-781">Измените текущее выделение, чтобы включить следующее слово с помощью Шеллнекстворд.</span><span class="sxs-lookup"><span data-stu-id="f55fd-781">Adjust the current selection to include the next word using ShellNextWord.</span></span>

- <span data-ttu-id="f55fd-782">Функция не привязана.</span><span class="sxs-lookup"><span data-stu-id="f55fd-782">Function is unbound.</span></span>

### <a name="setmark"></a><span data-ttu-id="f55fd-783">сетмарк</span><span class="sxs-lookup"><span data-stu-id="f55fd-783">SetMark</span></span>

<span data-ttu-id="f55fd-784">Пометка текущего положения курсора для использования в последующей команде редактирования.</span><span class="sxs-lookup"><span data-stu-id="f55fd-784">Mark the current location of the cursor for use in a subsequent editing command.</span></span>

- <span data-ttu-id="f55fd-785">Emacs: `<Ctrl+@>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-785">Emacs: `<Ctrl+@>`</span></span>

## <a name="predictive-intellisense-functions"></a><span data-ttu-id="f55fd-786">Функции прогнозной IntelliSense</span><span class="sxs-lookup"><span data-stu-id="f55fd-786">Predictive IntelliSense functions</span></span>

> [!NOTE]
> <span data-ttu-id="f55fd-787">Для использования этих функций необходимо включить прогнозную технологию IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="f55fd-787">Predictive IntelliSense needs to be enabled to use these functions.</span></span>

### <a name="acceptnextwordsuggestion"></a><span data-ttu-id="f55fd-788">акцептнекствордсугжестион</span><span class="sxs-lookup"><span data-stu-id="f55fd-788">AcceptNextWordSuggestion</span></span>

<span data-ttu-id="f55fd-789">Принимает следующее слово встроенного предложения из прогнозной IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="f55fd-789">Accepts the next word of the inline suggestion from Predictive IntelliSense.</span></span>
<span data-ttu-id="f55fd-790">Эту функцию можно привязать с помощью <kbd>клавиши CTRL</kbd> + <kbd>F</kbd> , выполнив следующую команду.</span><span class="sxs-lookup"><span data-stu-id="f55fd-790">This function can be bound with <kbd>Ctrl</kbd>+<kbd>F</kbd> by running the following command.</span></span>

```powershell
Set-PSReadLineKeyHandler -Chord "Ctrl+f" -Function ForwardWord
```

### <a name="acceptsuggestion"></a><span data-ttu-id="f55fd-791">акцептсугжестион</span><span class="sxs-lookup"><span data-stu-id="f55fd-791">AcceptSuggestion</span></span>

<span data-ttu-id="f55fd-792">Принимает текущее встроенное предложение от прогнозной IntelliSense, нажимая клавишу <kbd>RightArrow</kbd> , когда курсор находится в конце текущей строки.</span><span class="sxs-lookup"><span data-stu-id="f55fd-792">Accepts the current inline suggestion from Predictive IntelliSense by pressing <kbd>RightArrow</kbd> when the cursor is at the end of the current line.</span></span>

## <a name="search-functions"></a><span data-ttu-id="f55fd-793">Функции поиска</span><span class="sxs-lookup"><span data-stu-id="f55fd-793">Search functions</span></span>

### <a name="charactersearch"></a><span data-ttu-id="f55fd-794">чарактерсеарч</span><span class="sxs-lookup"><span data-stu-id="f55fd-794">CharacterSearch</span></span>

<span data-ttu-id="f55fd-795">Чтение символа и поиск вперед для следующего вхождения этого символа.</span><span class="sxs-lookup"><span data-stu-id="f55fd-795">Read a character and search forward for the next occurrence of that character.</span></span>
<span data-ttu-id="f55fd-796">Если указан аргумент, то для n-го вхождения выполните поиск вперед (или назад, если отрицательное).</span><span class="sxs-lookup"><span data-stu-id="f55fd-796">If an argument is specified, search forward (or backward if negative) for the nth occurrence.</span></span>

- <span data-ttu-id="f55fd-797">Процессор `<F3>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-797">Cmd: `<F3>`</span></span>
- <span data-ttu-id="f55fd-798">Emacs: `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-798">Emacs: `<Ctrl+]>`</span></span>
- <span data-ttu-id="f55fd-799">Режим вставки в VI: `<F3>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-799">Vi insert mode: `<F3>`</span></span>
- <span data-ttu-id="f55fd-800">Режим команд VI: `<F3>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-800">Vi command mode: `<F3>`</span></span>

### <a name="charactersearchbackward"></a><span data-ttu-id="f55fd-801">чарактерсеарчбакквард</span><span class="sxs-lookup"><span data-stu-id="f55fd-801">CharacterSearchBackward</span></span>

<span data-ttu-id="f55fd-802">Чтение символа и поиск следующего вхождения этого символа в обратном направлении.</span><span class="sxs-lookup"><span data-stu-id="f55fd-802">Read a character and search backward for the next occurrence of that character.</span></span> <span data-ttu-id="f55fd-803">Если аргумент указан, поиск в n-й последовательности осуществляется назад (или вперед, если отрицательное).</span><span class="sxs-lookup"><span data-stu-id="f55fd-803">If an argument is specified, search backward (or forward if negative) for the nth occurrence.</span></span>

- <span data-ttu-id="f55fd-804">Процессор `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-804">Cmd: `<Shift+F3>`</span></span>
- <span data-ttu-id="f55fd-805">Emacs: `<Ctrl+Alt+]>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-805">Emacs: `<Ctrl+Alt+]>`</span></span>
- <span data-ttu-id="f55fd-806">Режим вставки в VI: `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-806">Vi insert mode: `<Shift+F3>`</span></span>
- <span data-ttu-id="f55fd-807">Режим команд VI: `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-807">Vi command mode: `<Shift+F3>`</span></span>

### <a name="repeatlastcharsearch"></a><span data-ttu-id="f55fd-808">репеатластчарсеарч</span><span class="sxs-lookup"><span data-stu-id="f55fd-808">RepeatLastCharSearch</span></span>

<span data-ttu-id="f55fd-809">Повторите поиск последнего записанного символа.</span><span class="sxs-lookup"><span data-stu-id="f55fd-809">Repeat the last recorded character search.</span></span>

- <span data-ttu-id="f55fd-810">Режим команд VI: `<;>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-810">Vi command mode: `<;>`</span></span>

### <a name="repeatlastcharsearchbackwards"></a><span data-ttu-id="f55fd-811">репеатластчарсеарчбакквардс</span><span class="sxs-lookup"><span data-stu-id="f55fd-811">RepeatLastCharSearchBackwards</span></span>

<span data-ttu-id="f55fd-812">Повторите поиск последнего записанного символа, но в обратном направлении.</span><span class="sxs-lookup"><span data-stu-id="f55fd-812">Repeat the last recorded character search, but in the opposite direction.</span></span>

- <span data-ttu-id="f55fd-813">Режим команд VI: `<,>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-813">Vi command mode: `<,>`</span></span>

### <a name="repeatsearch"></a><span data-ttu-id="f55fd-814">репеатсеарч</span><span class="sxs-lookup"><span data-stu-id="f55fd-814">RepeatSearch</span></span>

<span data-ttu-id="f55fd-815">Повторите последний поиск в том же направлении, что и раньше.</span><span class="sxs-lookup"><span data-stu-id="f55fd-815">Repeat the last search in the same direction as before.</span></span>

- <span data-ttu-id="f55fd-816">Режим команд VI: `<n>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-816">Vi command mode: `<n>`</span></span>

### <a name="repeatsearchbackward"></a><span data-ttu-id="f55fd-817">репеатсеарчбакквард</span><span class="sxs-lookup"><span data-stu-id="f55fd-817">RepeatSearchBackward</span></span>

<span data-ttu-id="f55fd-818">Повторите последний поиск в том же направлении, что и раньше.</span><span class="sxs-lookup"><span data-stu-id="f55fd-818">Repeat the last search in the same direction as before.</span></span>

- <span data-ttu-id="f55fd-819">Режим команд VI: `<N>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-819">Vi command mode: `<N>`</span></span>

### <a name="searchchar"></a><span data-ttu-id="f55fd-820">сеарччар</span><span class="sxs-lookup"><span data-stu-id="f55fd-820">SearchChar</span></span>

<span data-ttu-id="f55fd-821">Прочитать следующий символ, затем найти его, перейти вперед, а затем отследить символ.</span><span class="sxs-lookup"><span data-stu-id="f55fd-821">Read the next character and then find it, going forward, and then back off a character.</span></span> <span data-ttu-id="f55fd-822">Это относится к функциональным возможностям.</span><span class="sxs-lookup"><span data-stu-id="f55fd-822">This is for 't' functionality.</span></span>

- <span data-ttu-id="f55fd-823">Режим команд VI: `<f>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-823">Vi command mode: `<f>`</span></span>

### <a name="searchcharbackward"></a><span data-ttu-id="f55fd-824">сеарччарбакквард</span><span class="sxs-lookup"><span data-stu-id="f55fd-824">SearchCharBackward</span></span>

<span data-ttu-id="f55fd-825">Прочитать следующий символ, а затем найти его, вернуться назад, а затем отследить символ.</span><span class="sxs-lookup"><span data-stu-id="f55fd-825">Read the next character and then find it, going backward, and then back off a character.</span></span> <span data-ttu-id="f55fd-826">Это относится к функциональным возможностям.</span><span class="sxs-lookup"><span data-stu-id="f55fd-826">This is for 'T' functionality.</span></span>

- <span data-ttu-id="f55fd-827">Режим команд VI: `<F>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-827">Vi command mode: `<F>`</span></span>

### <a name="searchcharbackwardwithbackoff"></a><span data-ttu-id="f55fd-828">сеарччарбакквардвисбаккофф</span><span class="sxs-lookup"><span data-stu-id="f55fd-828">SearchCharBackwardWithBackoff</span></span>

<span data-ttu-id="f55fd-829">Прочитать следующий символ, а затем найти его, вернуться назад, а затем отследить символ.</span><span class="sxs-lookup"><span data-stu-id="f55fd-829">Read the next character and then find it, going backward, and then back off a character.</span></span> <span data-ttu-id="f55fd-830">Это относится к функциональным возможностям.</span><span class="sxs-lookup"><span data-stu-id="f55fd-830">This is for 'T' functionality.</span></span>

- <span data-ttu-id="f55fd-831">Режим команд VI: `<T>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-831">Vi command mode: `<T>`</span></span>

### <a name="searchcharwithbackoff"></a><span data-ttu-id="f55fd-832">сеарччарвисбаккофф</span><span class="sxs-lookup"><span data-stu-id="f55fd-832">SearchCharWithBackoff</span></span>

<span data-ttu-id="f55fd-833">Прочитать следующий символ, затем найти его, перейти вперед, а затем отследить символ.</span><span class="sxs-lookup"><span data-stu-id="f55fd-833">Read the next character and then find it, going forward, and then back off a character.</span></span> <span data-ttu-id="f55fd-834">Это относится к функциональным возможностям.</span><span class="sxs-lookup"><span data-stu-id="f55fd-834">This is for 't' functionality.</span></span>

- <span data-ttu-id="f55fd-835">Режим команд VI: `<t>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-835">Vi command mode: `<t>`</span></span>

### <a name="searchforward"></a><span data-ttu-id="f55fd-836">сеарчфорвард</span><span class="sxs-lookup"><span data-stu-id="f55fd-836">SearchForward</span></span>

<span data-ttu-id="f55fd-837">Запрашивает строку поиска и инициирует поиск по запросу Акцептлине.</span><span class="sxs-lookup"><span data-stu-id="f55fd-837">Prompts for a search string and initiates search upon AcceptLine.</span></span>

- <span data-ttu-id="f55fd-838">Режим вставки в VI: `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-838">Vi insert mode: `<Ctrl+s>`</span></span>
- <span data-ttu-id="f55fd-839">Режим команд VI: `<?>` , `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="f55fd-839">Vi command mode: `<?>`, `<Ctrl+s>`</span></span>

## <a name="custom-key-bindings"></a><span data-ttu-id="f55fd-840">Пользовательские привязки клавиш</span><span class="sxs-lookup"><span data-stu-id="f55fd-840">Custom Key Bindings</span></span>

<span data-ttu-id="f55fd-841">PSReadLine поддерживает пользовательские привязки клавиш с помощью командлета `Set-PSReadLineKeyHandler` .</span><span class="sxs-lookup"><span data-stu-id="f55fd-841">PSReadLine supports custom key bindings using the cmdlet `Set-PSReadLineKeyHandler`.</span></span> <span data-ttu-id="f55fd-842">Большинство пользовательских привязок вызывают одну из приведенных выше функций, например</span><span class="sxs-lookup"><span data-stu-id="f55fd-842">Most custom key bindings call one of the above functions, for example</span></span>

```powershell
Set-PSReadLineKeyHandler -Key UpArrow -Function HistorySearchBackward
```

<span data-ttu-id="f55fd-843">Можно привязать ScriptBlock к ключу.</span><span class="sxs-lookup"><span data-stu-id="f55fd-843">You can bind a ScriptBlock to a key.</span></span> <span data-ttu-id="f55fd-844">Блок ScriptBlock может выполнять практически все необходимые действия.</span><span class="sxs-lookup"><span data-stu-id="f55fd-844">The ScriptBlock can do pretty much anything you want.</span></span> <span data-ttu-id="f55fd-845">Ниже приведены некоторые полезные примеры.</span><span class="sxs-lookup"><span data-stu-id="f55fd-845">Some useful examples include</span></span>

- <span data-ttu-id="f55fd-846">Изменение командной строки</span><span class="sxs-lookup"><span data-stu-id="f55fd-846">edit the command line</span></span>
- <span data-ttu-id="f55fd-847">Открытие нового окна (например, Справка)</span><span class="sxs-lookup"><span data-stu-id="f55fd-847">opening a new window (e.g. help)</span></span>
- <span data-ttu-id="f55fd-848">Изменение каталогов без изменения командной строки</span><span class="sxs-lookup"><span data-stu-id="f55fd-848">change directories without changing the command line</span></span>

<span data-ttu-id="f55fd-849">Блок ScriptBlock получает два аргумента:</span><span class="sxs-lookup"><span data-stu-id="f55fd-849">The ScriptBlock receives two arguments:</span></span>

- <span data-ttu-id="f55fd-850">`$key` — Объект **[консолекэйинфо]** , который является ключом, запускающим пользовательскую привязку.</span><span class="sxs-lookup"><span data-stu-id="f55fd-850">`$key` - A **[ConsoleKeyInfo]** object that is the key that triggered the custom binding.</span></span> <span data-ttu-id="f55fd-851">Если один и тот же блок сценария привязан к нескольким ключам и необходимо выполнять различные действия в зависимости от ключа, можно проверить $key.</span><span class="sxs-lookup"><span data-stu-id="f55fd-851">If you bind the same ScriptBlock to multiple keys and need to perform different actions depending on the key, you can check $key.</span></span> <span data-ttu-id="f55fd-852">Многие пользовательские привязки игнорируют этот аргумент.</span><span class="sxs-lookup"><span data-stu-id="f55fd-852">Many custom bindings ignore this argument.</span></span>

- <span data-ttu-id="f55fd-853">`$arg` — Произвольный аргумент.</span><span class="sxs-lookup"><span data-stu-id="f55fd-853">`$arg` - An arbitrary argument.</span></span> <span data-ttu-id="f55fd-854">Чаще всего это будет целочисленный аргумент, который пользователь передает из ключевых привязок Дигитаргумент.</span><span class="sxs-lookup"><span data-stu-id="f55fd-854">Most often, this would be an integer argument that the user passes from the key bindings DigitArgument.</span></span> <span data-ttu-id="f55fd-855">Если привязка не принимает аргументы, целесообразно проигнорировать этот аргумент.</span><span class="sxs-lookup"><span data-stu-id="f55fd-855">If your binding doesn't accept arguments, it's reasonable to ignore this argument.</span></span>

<span data-ttu-id="f55fd-856">Рассмотрим пример, который добавляет в журнал командную строку, не выполняя ее.</span><span class="sxs-lookup"><span data-stu-id="f55fd-856">Let's take a look at an example that adds a command line to history without executing it.</span></span> <span data-ttu-id="f55fd-857">Это полезно, если вы забыли сделать что-то, но не хотите повторно вводить уже введенную командную строку.</span><span class="sxs-lookup"><span data-stu-id="f55fd-857">This is useful when you realize you forgot to do something, but don't want to re-enter the command line you've already entered.</span></span>

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

<span data-ttu-id="f55fd-858">В файле, `SamplePSReadLineProfile.ps1` который устанавливается в папку модуля PSReadLine, можно увидеть много других примеров.</span><span class="sxs-lookup"><span data-stu-id="f55fd-858">You can see many more examples in the file `SamplePSReadLineProfile.ps1` which is installed in the PSReadLine module folder.</span></span>

<span data-ttu-id="f55fd-859">Большинство ключевых привязок используют некоторые вспомогательные функции для редактирования командной строки.</span><span class="sxs-lookup"><span data-stu-id="f55fd-859">Most key bindings use some helper functions for editing the command line.</span></span>
<span data-ttu-id="f55fd-860">Эти API-интерфейсы описаны в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="f55fd-860">Those APIs are documented in the next section.</span></span>

## <a name="custom-key-binding-support-apis"></a><span data-ttu-id="f55fd-861">API поддержки пользовательского сочетания клавиш</span><span class="sxs-lookup"><span data-stu-id="f55fd-861">Custom Key Binding Support APIs</span></span>

<span data-ttu-id="f55fd-862">Следующие функции являются открытыми в Microsoft. PowerShell. Псконсолереадлине, но не могут быть напрямую привязаны к ключу.</span><span class="sxs-lookup"><span data-stu-id="f55fd-862">The following functions are public in Microsoft.PowerShell.PSConsoleReadLine, but cannot be directly bound to a key.</span></span> <span data-ttu-id="f55fd-863">Большинство из них удобно использовать в пользовательских привязках клавиш.</span><span class="sxs-lookup"><span data-stu-id="f55fd-863">Most are useful in custom key bindings.</span></span>

```csharp
void AddToHistory(string command)
```

<span data-ttu-id="f55fd-864">Добавьте командную строку в журнал, не выполняя ее.</span><span class="sxs-lookup"><span data-stu-id="f55fd-864">Add a command line to history without executing it.</span></span>

```csharp
void ClearKillRing()
```

<span data-ttu-id="f55fd-865">Снимите флажок Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="f55fd-865">Clear the kill-ring.</span></span>  <span data-ttu-id="f55fd-866">Это в основном используется для тестирования.</span><span class="sxs-lookup"><span data-stu-id="f55fd-866">This is mostly used for testing.</span></span>

```csharp
void Delete(int start, int length)
```

<span data-ttu-id="f55fd-867">Удалить символы длины из Start.</span><span class="sxs-lookup"><span data-stu-id="f55fd-867">Delete length characters from start.</span></span>  <span data-ttu-id="f55fd-868">Эта операция поддерживает операцию отмены и повтора.</span><span class="sxs-lookup"><span data-stu-id="f55fd-868">This operation supports undo/redo.</span></span>

```csharp
void Ding()
```

<span data-ttu-id="f55fd-869">Выполните действие DING, основанное на предпочтениях пользователей.</span><span class="sxs-lookup"><span data-stu-id="f55fd-869">Perform the Ding action based on the users preference.</span></span>

```csharp
void GetBufferState([ref] string input, [ref] int cursor)
void GetBufferState([ref] Ast ast, [ref] Token[] tokens,
  [ref] ParseError[] parseErrors, [ref] int cursor)
```

<span data-ttu-id="f55fd-870">Эти две функции извлекают полезную информацию о текущем состоянии входного буфера.</span><span class="sxs-lookup"><span data-stu-id="f55fd-870">These two functions retrieve useful information about the current state of the input buffer.</span></span>  <span data-ttu-id="f55fd-871">Первый из них чаще всего используется в простых случаях.</span><span class="sxs-lookup"><span data-stu-id="f55fd-871">The first is more commonly used for simple cases.</span></span>  <span data-ttu-id="f55fd-872">Второй используется, если привязка делает что-то более сложное с AST.</span><span class="sxs-lookup"><span data-stu-id="f55fd-872">The second is used if your binding is doing something more advanced with the Ast.</span></span>

```csharp
IEnumerable[Microsoft.PowerShell.KeyHandler]
  GetKeyHandlers(bool includeBound, bool includeUnbound)

IEnumerable[Microsoft.PowerShell.KeyHandler]
  GetKeyHandlers(string[] Chord)
```

<span data-ttu-id="f55fd-873">Эти две функции используются `Get-PSReadLineKeyHandler` .</span><span class="sxs-lookup"><span data-stu-id="f55fd-873">These two functions are used by `Get-PSReadLineKeyHandler`.</span></span> <span data-ttu-id="f55fd-874">Первый используется для получения всех привязок клавиш.</span><span class="sxs-lookup"><span data-stu-id="f55fd-874">The first is used to get all key bindings.</span></span> <span data-ttu-id="f55fd-875">Второй используется для получения конкретных привязок клавиш.</span><span class="sxs-lookup"><span data-stu-id="f55fd-875">The second is used to get specific key bindings.</span></span>

```csharp
Microsoft.PowerShell.PSConsoleReadLineOptions GetOptions()
```

<span data-ttu-id="f55fd-876">Эта функция используется Get-PSReadLineOption и, возможно, не слишком полезна в пользовательской привязке ключа.</span><span class="sxs-lookup"><span data-stu-id="f55fd-876">This function is used by Get-PSReadLineOption and probably isn't too useful in a custom key binding.</span></span>

```csharp
void GetSelectionState([ref] int start, [ref] int length)
```

<span data-ttu-id="f55fd-877">Если в командной строке ничего не выбрано, значение-1 будет возвращено как в начале, так и в длине.</span><span class="sxs-lookup"><span data-stu-id="f55fd-877">If there is no selection on the command line, -1 will be returned in both start and length.</span></span> <span data-ttu-id="f55fd-878">Если в командной строке имеется выделенный фрагмент, то начинается и длина выбора возвращается.</span><span class="sxs-lookup"><span data-stu-id="f55fd-878">If there is a selection on the command line, the start and length of the selection are returned.</span></span>

```csharp
void Insert(char c)
void Insert(string s)
```

<span data-ttu-id="f55fd-879">Вставка символа или строки в курсоре.</span><span class="sxs-lookup"><span data-stu-id="f55fd-879">Insert a character or string at the cursor.</span></span>  <span data-ttu-id="f55fd-880">Эта операция поддерживает операцию отмены и повтора.</span><span class="sxs-lookup"><span data-stu-id="f55fd-880">This operation supports undo/redo.</span></span>

```csharp
string ReadLine(runspace remoteRunspace,
  System.Management.Automation.EngineIntrinsics engineIntrinsics)
```

<span data-ttu-id="f55fd-881">Это Главная точка входа для PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="f55fd-881">This is the main entry point to PSReadLine.</span></span> <span data-ttu-id="f55fd-882">Она не поддерживает рекурсию, поэтому она не полезна в пользовательской привязке ключа.</span><span class="sxs-lookup"><span data-stu-id="f55fd-882">It does not support recursion, so is not useful in a custom key binding.</span></span>

```csharp
void RemoveKeyHandler(string[] key)
```

<span data-ttu-id="f55fd-883">Эта функция используется Remove-PSReadLineKeyHandler и, возможно, не слишком полезна в пользовательской привязке ключа.</span><span class="sxs-lookup"><span data-stu-id="f55fd-883">This function is used by Remove-PSReadLineKeyHandler and probably isn't too useful in a custom key binding.</span></span>

```csharp
void Replace(int start, int length, string replacement)
```

<span data-ttu-id="f55fd-884">Замените некоторые входные данные.</span><span class="sxs-lookup"><span data-stu-id="f55fd-884">Replace some of the input.</span></span> <span data-ttu-id="f55fd-885">Эта операция поддерживает операцию отмены и повтора.</span><span class="sxs-lookup"><span data-stu-id="f55fd-885">This operation supports undo/redo.</span></span> <span data-ttu-id="f55fd-886">Это предпочтительнее удаление с последующим вставкой, так как оно обрабатывается как одно действие для отмены.</span><span class="sxs-lookup"><span data-stu-id="f55fd-886">This is preferred over Delete followed by Insert because it is treated as a single action for undo.</span></span>

```csharp
void SetCursorPosition(int cursor)
```

<span data-ttu-id="f55fd-887">Переместить курсор к заданному смещению.</span><span class="sxs-lookup"><span data-stu-id="f55fd-887">Move the cursor to the given offset.</span></span> <span data-ttu-id="f55fd-888">Перемещение курсора не ведется для отмены.</span><span class="sxs-lookup"><span data-stu-id="f55fd-888">Cursor movement is not tracked for undo.</span></span>

```csharp
void SetOptions(Microsoft.PowerShell.SetPSReadLineOption options)
```

<span data-ttu-id="f55fd-889">Эта функция является вспомогательным методом, используемым командлетом Set-PSReadLineOption, но может быть полезен для пользовательской привязки ключа, которая хочет временно изменить параметр.</span><span class="sxs-lookup"><span data-stu-id="f55fd-889">This function is a helper method used by the cmdlet Set-PSReadLineOption, but might be useful to a custom key binding that wants to temporarily change a setting.</span></span>

```csharp
bool TryGetArgAsInt(System.Object arg, [ref] int numericArg,
  int defaultNumericArg)
```

<span data-ttu-id="f55fd-890">Этот вспомогательный метод используется для пользовательских привязок, которые учитывают Дигитаргумент.</span><span class="sxs-lookup"><span data-stu-id="f55fd-890">This helper method is used for custom bindings that honor DigitArgument.</span></span> <span data-ttu-id="f55fd-891">Обычный вызов выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="f55fd-891">A typical call looks like</span></span>

```powershell
[int]$numericArg = 0
[Microsoft.PowerShell.PSConsoleReadLine]::TryGetArgAsInt($arg,
  [ref]$numericArg, 1)
```

## <a name="notes"></a><span data-ttu-id="f55fd-892">Примечания</span><span class="sxs-lookup"><span data-stu-id="f55fd-892">Notes</span></span>

### <a name="command-history"></a><span data-ttu-id="f55fd-893">Журнал команд</span><span class="sxs-lookup"><span data-stu-id="f55fd-893">Command History</span></span>

<span data-ttu-id="f55fd-894">PSReadLine поддерживает файл журнала, содержащий все команды и данные, введенные из командной строки.</span><span class="sxs-lookup"><span data-stu-id="f55fd-894">PSReadLine maintains a history file containing all the commands and data you have entered from the command line.</span></span> <span data-ttu-id="f55fd-895">Это может быть конфиденциальные данные, включая пароли.</span><span class="sxs-lookup"><span data-stu-id="f55fd-895">This may contain sensitive data including passwords.</span></span> <span data-ttu-id="f55fd-896">Например, при использовании `ConvertTo-SecureString` командлета пароль заносится в файл журнала в виде обычного текста.</span><span class="sxs-lookup"><span data-stu-id="f55fd-896">For example, if you use the `ConvertTo-SecureString` cmdlet the password is logged in the history file as plain text.</span></span> <span data-ttu-id="f55fd-897">Файлы журнала — это файл с именем `$($host.Name)_history.txt` .</span><span class="sxs-lookup"><span data-stu-id="f55fd-897">The history files is a file named `$($host.Name)_history.txt`.</span></span> <span data-ttu-id="f55fd-898">В системах Windows файл журнала хранится в файле `$env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine` .</span><span class="sxs-lookup"><span data-stu-id="f55fd-898">On Windows systems the history file is stored at `$env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine`.</span></span> <span data-ttu-id="f55fd-899">В системах, отличных от Windows, файлы журнала хранятся в `$env:XDG_DATA_HOME/powershell/PSReadLine` или `$env:HOME/.local/share/powershell/PSReadLine` .</span><span class="sxs-lookup"><span data-stu-id="f55fd-899">On non-Windows systems, the history files is stored at `$env:XDG_DATA_HOME/powershell/PSReadLine` or `$env:HOME/.local/share/powershell/PSReadLine`.</span></span>

### <a name="feedback--contributing-to-psreadline"></a><span data-ttu-id="f55fd-900">Обратная связь & участие в PSReadLine</span><span class="sxs-lookup"><span data-stu-id="f55fd-900">Feedback & Contributing To PSReadLine</span></span>

[<span data-ttu-id="f55fd-901">PSReadLine на GitHub</span><span class="sxs-lookup"><span data-stu-id="f55fd-901">PSReadLine on GitHub</span></span>](https://github.com/PowerShell/PSReadLine)

<span data-ttu-id="f55fd-902">Вы можете отправить запрос на вытягивание или отправить отзыв на страницу GitHub.</span><span class="sxs-lookup"><span data-stu-id="f55fd-902">Feel free to submit a pull request or submit feedback on the GitHub page.</span></span>

## <a name="see-also"></a><span data-ttu-id="f55fd-903">См. также:</span><span class="sxs-lookup"><span data-stu-id="f55fd-903">See Also</span></span>

<span data-ttu-id="f55fd-904">На PSReadLine сильно влияют библиотеки GNU [ReadLine](https://tiswww.case.edu/php/chet/readline/rltop.html) .</span><span class="sxs-lookup"><span data-stu-id="f55fd-904">PSReadLine is heavily influenced by the GNU [readline](https://tiswww.case.edu/php/chet/readline/rltop.html) library.</span></span>
