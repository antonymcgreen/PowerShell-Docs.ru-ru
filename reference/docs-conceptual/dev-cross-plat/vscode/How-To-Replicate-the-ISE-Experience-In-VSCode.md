---
title: Репликация функций интегрированной среды скриптов в Visual Studio Code
description: Репликация функций интегрированной среды скриптов в Visual Studio Code
ms.date: 08/06/2018
ms.openlocfilehash: 899e1c393fd49b0659631b88d610e80ec885e69e
ms.sourcegitcommit: 2aec310ad0c0b048400cb56f6fa64c1e554c812a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/23/2020
ms.locfileid: "83809600"
---
# <a name="how-to-replicate-the-ise-experience-in-visual-studio-code"></a><span data-ttu-id="a6ec8-103">Репликация функций интегрированной среды скриптов в Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="a6ec8-103">How to replicate the ISE experience in Visual Studio Code</span></span>

<span data-ttu-id="a6ec8-104">Расширение PowerShell для VS Code не вполне соответствует интегрированной среде скриптов PowerShell, но существуют функции, которые помогут пользователям интегрированной среды скриптов эффективней работать с VS Code.</span><span class="sxs-lookup"><span data-stu-id="a6ec8-104">While the PowerShell extension for VS Code doesn't seek complete feature parity with the PowerShell ISE, there are features in place to make the VS Code experience more natural for users of the ISE.</span></span>

<span data-ttu-id="a6ec8-105">В этой статье приведен список параметров, настраиваемых в VS Code, которые упростят работу с программой пользователям интегрированной среды скриптов.</span><span class="sxs-lookup"><span data-stu-id="a6ec8-105">This document tries to list settings you can configure in VS Code to make the user experience a bit more familiar compared to the ISE.</span></span>

## <a name="ise-mode"></a><span data-ttu-id="a6ec8-106">Режим ISE</span><span class="sxs-lookup"><span data-stu-id="a6ec8-106">ISE Mode</span></span>

> [!NOTE]
> <span data-ttu-id="a6ec8-107">Эта функция доступна в расширении предварительной версии PowerShell, начиная с версии 2019.12.0, и в расширении PowerShell, начиная с версии 2020.3.0.</span><span class="sxs-lookup"><span data-stu-id="a6ec8-107">This feature is available in the PowerShell Preview extension since version 2019.12.0 and in the PowerShell extension since version 2020.3.0.</span></span>

<span data-ttu-id="a6ec8-108">Самый простой способ реплицировать функции интегрированной среды скриптов (ISE) в Visual Studio Code — включить режим ISE.</span><span class="sxs-lookup"><span data-stu-id="a6ec8-108">The easiest way to replicate the ISE experience in Visual Studio Code is by turning on "ISE Mode".</span></span>
<span data-ttu-id="a6ec8-109">Для этого откройте палитру команд (клавиша <kbd>F1</kbd> или клавиши <kbd>CTRL</kbd>+<kbd>SHIFT</kbd>+<kbd>P</kbd> или <kbd>CMD</kbd>+<kbd>SHIFT</kbd>+<kbd>P</kbd> в macOS) и введите ISE Mode (Режим ISE).</span><span class="sxs-lookup"><span data-stu-id="a6ec8-109">To do this, open the command palette (<kbd>F1</kbd> OR <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> OR <kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> on macOS) and type in "ISE Mode".</span></span> <span data-ttu-id="a6ec8-110">Выберите в списке пункт "PowerShell: Enable ISE Mode" (PowerShell: включить режим ISE).</span><span class="sxs-lookup"><span data-stu-id="a6ec8-110">Select "PowerShell: Enable ISE Mode" from the list.</span></span>

<span data-ttu-id="a6ec8-111">Эта команда автоматически применяет многие параметры, описанные в этом документе. Результат имеет следующий вид:</span><span class="sxs-lookup"><span data-stu-id="a6ec8-111">This command automatically applies the settings described below The result looks like this:</span></span>

![Режим ISE](media/How-To-Replicate-the-ISE-Experience-In-VSCode/3-ise-mode.png)

## <a name="ise-mode-configuration-settings"></a><span data-ttu-id="a6ec8-113">Параметры конфигурации режима ISE</span><span class="sxs-lookup"><span data-stu-id="a6ec8-113">ISE Mode configuration settings</span></span>

<span data-ttu-id="a6ec8-114">Режим ISE вносит следующие изменения в параметры VS Code.</span><span class="sxs-lookup"><span data-stu-id="a6ec8-114">ISE Mode makes the following changes to VS Code settings.</span></span>

- <span data-ttu-id="a6ec8-115">Сочетания клавиш</span><span class="sxs-lookup"><span data-stu-id="a6ec8-115">Key bindings</span></span>

  |               <span data-ttu-id="a6ec8-116">Компонент</span><span class="sxs-lookup"><span data-stu-id="a6ec8-116">Function</span></span>                |         <span data-ttu-id="a6ec8-117">Привязка интегрированной среды сценариев</span><span class="sxs-lookup"><span data-stu-id="a6ec8-117">ISE Binding</span></span>          |              <span data-ttu-id="a6ec8-118">Привязка VS Code</span><span class="sxs-lookup"><span data-stu-id="a6ec8-118">VS Code Binding</span></span>                |
  | ------------------------------------- | ---------------------------- | ------------------------------------------- |
  | <span data-ttu-id="a6ec8-119">Прерывание и остановка отладчика</span><span class="sxs-lookup"><span data-stu-id="a6ec8-119">Interrupt and break debugger</span></span>          | <span data-ttu-id="a6ec8-120"><kbd>CTRL</kbd>+<kbd>B</kbd></span><span class="sxs-lookup"><span data-stu-id="a6ec8-120"><kbd>Ctrl</kbd>+<kbd>B</kbd></span></span> | <span data-ttu-id="a6ec8-121"><kbd>F6</kbd></span><span class="sxs-lookup"><span data-stu-id="a6ec8-121"><kbd>F6</kbd></span></span>                               |
  | <span data-ttu-id="a6ec8-122">Выполнение текущей строки / выделение текста</span><span class="sxs-lookup"><span data-stu-id="a6ec8-122">Execute current line/highlighted text</span></span> | <span data-ttu-id="a6ec8-123"><kbd>F8</kbd></span><span class="sxs-lookup"><span data-stu-id="a6ec8-123"><kbd>F8</kbd></span></span>                | <span data-ttu-id="a6ec8-124"><kbd>F8</kbd></span><span class="sxs-lookup"><span data-stu-id="a6ec8-124"><kbd>F8</kbd></span></span>                               |
  | <span data-ttu-id="a6ec8-125">Список доступных фрагментов</span><span class="sxs-lookup"><span data-stu-id="a6ec8-125">List available snippets</span></span>               | <span data-ttu-id="a6ec8-126"><kbd>CTRL</kbd>+<kbd>J</kbd></span><span class="sxs-lookup"><span data-stu-id="a6ec8-126"><kbd>Ctrl</kbd>+<kbd>J</kbd></span></span> | <span data-ttu-id="a6ec8-127"><kbd>CTRL</kbd>+<kbd>ALT</kbd>+<kbd>J</kbd></span><span class="sxs-lookup"><span data-stu-id="a6ec8-127"><kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>J</kbd></span></span> |

  > [!NOTE]
  > <span data-ttu-id="a6ec8-128">В VS Code также можно [настраивать собственные сочетания клавиш](https://code.visualstudio.com/docs/getstarted/keybindings#_custom-keybindings-for-refactorings).</span><span class="sxs-lookup"><span data-stu-id="a6ec8-128">You can [configure your own key bindings](https://code.visualstudio.com/docs/getstarted/keybindings#_custom-keybindings-for-refactorings) in VS Code as well.</span></span>

- <span data-ttu-id="a6ec8-129">Упрощенный интерфейс, как в интегрированной среде сценариев</span><span class="sxs-lookup"><span data-stu-id="a6ec8-129">Simplified ISE-like UI</span></span>

  <span data-ttu-id="a6ec8-130">Если вы хотите упростить пользовательский интерфейс Visual Studio Code, чтобы он стал больше похож на интерфейс интегрированной среды сценариев, примените эти два параметра:</span><span class="sxs-lookup"><span data-stu-id="a6ec8-130">If you're looking to simplify the Visual Studio Code UI to look more closely to the UI of the ISE, apply these two settings:</span></span>

  ```json
  "workbench.activityBar.visible": false,
  "debug.openDebug": "neverOpen",
  ```

  <span data-ttu-id="a6ec8-131">Эти параметры позволяют скрыть разделы с панелью действий и боковой панелью отладки, которые очерчены красной линией на следующей иллюстрации.</span><span class="sxs-lookup"><span data-stu-id="a6ec8-131">These settings hide the "Activity Bar" and the "Debug Side Bar" sections shown inside the red box below:</span></span>

  ![Выделенный раздел с панелью действий и боковой панелью отладки](media/How-To-Replicate-the-ISE-Experience-In-VSCode/1-highlighted-sidebar.png)

  <span data-ttu-id="a6ec8-133">В итоге представление будет выглядеть так:</span><span class="sxs-lookup"><span data-stu-id="a6ec8-133">The end result looks like this:</span></span>

  ![Упрощенное представление VS Code](media/How-To-Replicate-the-ISE-Experience-In-VSCode/2-simplified-ui.png)

- <span data-ttu-id="a6ec8-135">Заполнение нажатием клавиши TAB</span><span class="sxs-lookup"><span data-stu-id="a6ec8-135">Tab completion</span></span>

  <span data-ttu-id="a6ec8-136">Чтобы включить заполнение нажатием клавиши TAB (похожее на интегрированную среду сценариев), добавьте следующий параметр.</span><span class="sxs-lookup"><span data-stu-id="a6ec8-136">To enable more ISE-like tab completion, add this setting:</span></span>

  ```json
  "editor.tabCompletion": "on",
  ```

- <span data-ttu-id="a6ec8-137">Отсутствие фокуса в консоли во время выполнения</span><span class="sxs-lookup"><span data-stu-id="a6ec8-137">No focus on console when executing</span></span>

  <span data-ttu-id="a6ec8-138">Чтобы сохранить фокус в редакторе во время выполнения с помощью клавиши <kbd>F8</kbd>, выполните следующее.</span><span class="sxs-lookup"><span data-stu-id="a6ec8-138">To keep the focus in the editor when you execute with <kbd>F8</kbd>:</span></span>

  ```json
  "powershell.integratedConsole.focusConsoleOnExecute": false
  ```

  <span data-ttu-id="a6ec8-139">Значение по умолчанию `true` устанавливается в соответствии с требованиями к поддержке специальных возможностей.</span><span class="sxs-lookup"><span data-stu-id="a6ec8-139">The default is `true` for accessibility purposes.</span></span>

- <span data-ttu-id="a6ec8-140">Интегрированную консоль не следует запускать при начальной загрузке</span><span class="sxs-lookup"><span data-stu-id="a6ec8-140">Don't start integrated console on startup</span></span>

  <span data-ttu-id="a6ec8-141">Чтобы остановить запуск интегрированной консоли при начальной загрузке, установите следующий параметр.</span><span class="sxs-lookup"><span data-stu-id="a6ec8-141">To stop the integrated console on startup, set:</span></span>

  ```json
  "powershell.integratedConsole.showOnStartup": false
  ```

  > [!NOTE]
  > <span data-ttu-id="a6ec8-142">Фоновый процесс PowerShell все равно запустится, так как он предоставляет IntelliSense, анализ скриптов, навигацию по символам и т. д., но консоль не будет запущена.</span><span class="sxs-lookup"><span data-stu-id="a6ec8-142">The background PowerShell process still starts to provide IntelliSense, script analysis, symbol navigation, etc., but the console won't be shown.</span></span>

- <span data-ttu-id="a6ec8-143">Предположим, что по умолчанию файлы относятся к PowerShell</span><span class="sxs-lookup"><span data-stu-id="a6ec8-143">Assume files are PowerShell by default</span></span>

  <span data-ttu-id="a6ec8-144">Чтобы создать новые файлы без имени, по умолчанию следует зарегистрироваться в качестве PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a6ec8-144">To make new/untitled files, register as PowerShell by default:</span></span>

  ```json
  "files.defaultLanguage": "powershell",
  ```

- <span data-ttu-id="a6ec8-145">Цветовая схема</span><span class="sxs-lookup"><span data-stu-id="a6ec8-145">Color scheme</span></span>

  <span data-ttu-id="a6ec8-146">Существует большое количество тем ISE, доступных для VS Code. Они позволяют сделать редактор более похожим на интегрированную среду скриптов.</span><span class="sxs-lookup"><span data-stu-id="a6ec8-146">There are a number of ISE themes available for VS Code to make the editor look much more like the ISE.</span></span>

  <span data-ttu-id="a6ec8-147">В [Палитра команд][] введите `theme`, чтобы получить `Preferences: Color Theme`, а затем нажмите <kbd>ВВОД</kbd>.</span><span class="sxs-lookup"><span data-stu-id="a6ec8-147">In the [Command Palette][] type `theme` to get `Preferences: Color Theme` and press <kbd>Enter</kbd>.</span></span> <span data-ttu-id="a6ec8-148">В раскрывающемся списке выберите `PowerShell ISE`.</span><span class="sxs-lookup"><span data-stu-id="a6ec8-148">In the drop-down list, select `PowerShell ISE`.</span></span>

  <span data-ttu-id="a6ec8-149">Эту тему можно установить в параметрах следующим образом.</span><span class="sxs-lookup"><span data-stu-id="a6ec8-149">You can set this theme in the settings with:</span></span>

  ```json
  "workbench.colorTheme": "PowerShell ISE",
  ```

- <span data-ttu-id="a6ec8-150">Команды обозревателя PowerShell</span><span class="sxs-lookup"><span data-stu-id="a6ec8-150">PowerShell Command Explorer</span></span>

  <span data-ttu-id="a6ec8-151">Благодаря работе, проделанной [@corbob](https://github.com/corbob), теперь расширение PowerShell обладает начальными командами обозревателя.</span><span class="sxs-lookup"><span data-stu-id="a6ec8-151">Thanks to the work of [@corbob](https://github.com/corbob), the PowerShell extension has the beginnings of its own command explorer.</span></span>

  <span data-ttu-id="a6ec8-152">В [Палитра команд][] введите `PowerShell Command Explorer` и нажмите <kbd>ВВОД</kbd>.</span><span class="sxs-lookup"><span data-stu-id="a6ec8-152">In the [Command Palette][], enter `PowerShell Command Explorer` and press <kbd>Enter</kbd>.</span></span>

- <span data-ttu-id="a6ec8-153">Открытие в интегрированной среде сценариев</span><span class="sxs-lookup"><span data-stu-id="a6ec8-153">Open in the ISE</span></span>

  <span data-ttu-id="a6ec8-154">Если вы хотите открыть файл в интегрированной среде скриптов Windows PowerShell, откройте [Палитра команд][], выполните поиск по запросу open in ise (Открыть в интегрированной среде скриптов) и выберите **PowerShell: Open Current File in PowerShell ISE** (Открыть текущий файл в интегрированной среде скриптов PowerShell).</span><span class="sxs-lookup"><span data-stu-id="a6ec8-154">If you want to open a file in the Windows PowerShell ISE anyway, open the [Command Palette][], search for "open in ise", then select **PowerShell: Open Current File in PowerShell ISE**.</span></span>

## <a name="other-resources"></a><span data-ttu-id="a6ec8-155">Другие ресурсы</span><span class="sxs-lookup"><span data-stu-id="a6ec8-155">Other resources</span></span>

- <span data-ttu-id="a6ec8-156">На веб-сайте 4sysops доступна [замечательная статья][4sysops] о настройках VS Code, которые сделают интерфейс программы похожим на интегрированную среду скриптов.</span><span class="sxs-lookup"><span data-stu-id="a6ec8-156">4sysops has [a great article][4sysops] on configuring VS Code to be more like the ISE.</span></span>
- <span data-ttu-id="a6ec8-157">[Отличная статья][mikefrobbins] о настройке VS Code, написанная Майком Ф. Роббинсом (Mike F. Robbins).</span><span class="sxs-lookup"><span data-stu-id="a6ec8-157">Mike F Robbins has [a great post][mikefrobbins] on setting up VS Code.</span></span>
- <span data-ttu-id="a6ec8-158">Еще одна [хорошая статья][learnpwsh] о настройке VS Code для работы с PowerShell на сайте Learn PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a6ec8-158">Learn PowerShell has [an excellent write up][learnpwsh] setup for PowerShell.</span></span>

## <a name="vs-code-tips"></a><span data-ttu-id="a6ec8-159">Рекомендации по работе с Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="a6ec8-159">VS Code Tips</span></span>

- <span data-ttu-id="a6ec8-160">Палитра команд</span><span class="sxs-lookup"><span data-stu-id="a6ec8-160">Command Palette</span></span>

  <span data-ttu-id="a6ec8-161">Палитра команд — это удобный инструмент выполнения команд в VS Code.</span><span class="sxs-lookup"><span data-stu-id="a6ec8-161">The Command Palette is handy way of executing commands in VS Code.</span></span> <span data-ttu-id="a6ec8-162">Откройте палитру команд с помощью клавиши <kbd>F1</kbd> или клавиш <kbd>CTRL</kbd>+<kbd>SHIFT</kbd>+<kbd>P</kbd>, или <kbd>CMD</kbd>+<kbd>+</kbd>+<kbd>P</kbd> в macOS.</span><span class="sxs-lookup"><span data-stu-id="a6ec8-162">Open the command palette using <kbd>F1</kbd> OR <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> OR <kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> on macOS.</span></span>

  <span data-ttu-id="a6ec8-163">Дополнительные сведения см. в [документации по VS Code][vsc-docs].</span><span class="sxs-lookup"><span data-stu-id="a6ec8-163">For more information, see [the VS Code documentation][vsc-docs].</span></span>

- <span data-ttu-id="a6ec8-164">Отключение консоли отладки</span><span class="sxs-lookup"><span data-stu-id="a6ec8-164">Disable the Debug Console</span></span>

  <span data-ttu-id="a6ec8-165">Если вы планируете использовать VS Code только для создания скриптов PowerShell, можно скрыть **консоль отладки**, так как она не используется расширением PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a6ec8-165">If you only plan on using VS Code for PowerShell scripting, you can hide the **Debug Console** since it is not used by the PowerShell extension.</span></span> <span data-ttu-id="a6ec8-166">Для этого щелкните правой кнопкой мыши **консоль отладки** и снимите флажок, чтобы скрыть ее.</span><span class="sxs-lookup"><span data-stu-id="a6ec8-166">To do so, right click on **Debug Console** then click on the check mark to hide it.</span></span>

## <a name="more-settings"></a><span data-ttu-id="a6ec8-167">Дополнительные параметры</span><span class="sxs-lookup"><span data-stu-id="a6ec8-167">More settings</span></span>

<span data-ttu-id="a6ec8-168">Если вы знаете, как еще можно упростить работу с VS Code для пользователей интегрированной среды скриптов, дополните эту статью. Если существует конфигурация совместимости, которую вы не можете включить, не медлите и [Отправить сообщение о проблеме][].</span><span class="sxs-lookup"><span data-stu-id="a6ec8-168">If you know of more ways to make VS Code feel more familiar for ISE users, contribute to this doc. If there's a compatibility configuration you're looking for, but you can't find any way to enable it, [open an issue][] and ask away!</span></span>

<span data-ttu-id="a6ec8-169">Мы всегда рады содействию и запросам на включение внесенных изменений.</span><span class="sxs-lookup"><span data-stu-id="a6ec8-169">We're always happy to accept PRs and contributions as well!</span></span>

<!-- link references -->
[vsc-docs]: https://code.visualstudio.com/docs/getstarted/userinterface#_command-palette
[Палитра команд]: #vs-code-tips
[Command Palette]: #vs-code-tips
[Отправить сообщение о проблеме]: https://github.com/PowerShell/VSCode-powershell/issues/new/choose
[open an issue]: https://github.com/PowerShell/VSCode-powershell/issues/new/choose

[4sysops]: https://4sysops.com/archives/make-visual-studio-code-look-and-behave-like-powershell-ise/
[mikefrobbins]: https://mikefrobbins.com/2017/08/24/how-to-install-visual-studio-code-and-configure-it-as-a-replacement-for-the-powershell-ise/
[learnpwsh]: https://www.learnpwsh.com/setup-vs-code-for-powershell/
