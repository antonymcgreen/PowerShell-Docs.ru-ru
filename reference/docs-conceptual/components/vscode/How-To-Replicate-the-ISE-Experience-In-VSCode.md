---
title: Репликация функций интегрированной среды скриптов в Visual Studio Code
description: Репликация функций интегрированной среды скриптов в Visual Studio Code
ms.date: 08/06/2018
ms.openlocfilehash: 193243dc2e3e921b22a6ee068370200ae84ce4ac
ms.sourcegitcommit: 01c60c0c97542dbad48ae34339cddbd813f1353b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2020
ms.locfileid: "78279276"
---
# <a name="how-to-replicate-the-ise-experience-in-visual-studio-code"></a><span data-ttu-id="faa56-103">Репликация функций интегрированной среды скриптов в Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="faa56-103">How to replicate the ISE experience in Visual Studio Code</span></span>

<span data-ttu-id="faa56-104">В то время, как расширение PowerShell для VSCode не совсем совместимо с интегрированной средой сценариев PowerShell, существуют функции, использование которых позволит пользователям интегрированной среды сценариев почувствовать себя более свободно в VSCode.</span><span class="sxs-lookup"><span data-stu-id="faa56-104">While the PowerShell extension for VSCode doesn't seek complete feature parity with the PowerShell ISE, there are features in place to make the VSCode experience more natural for users of the ISE.</span></span>

<span data-ttu-id="faa56-105">В этой статье приведен список параметров, настраиваемых в VSCode, которые смогут облегчить ее использование для пользователей интегрированной среды сценариев.</span><span class="sxs-lookup"><span data-stu-id="faa56-105">This document tries to list settings you can configure in VSCode to make the user experience a bit more familiar compared to the ISE.</span></span>

## <a name="ise-mode"></a><span data-ttu-id="faa56-106">Режим ISE</span><span class="sxs-lookup"><span data-stu-id="faa56-106">ISE Mode</span></span>

> [!NOTE]
> <span data-ttu-id="faa56-107">Эта функция доступна в расширении предварительной версии PowerShell, начиная с версии 2019.12.0, и в расширении PowerShell, начиная с версии 2020.3.0.</span><span class="sxs-lookup"><span data-stu-id="faa56-107">This feature is available in the PowerShell Preview extension since version 2019.12.0 and in the PowerShell extension since version 2020.3.0.</span></span>

<span data-ttu-id="faa56-108">Самый простой способ реплицировать функции интегрированной среды скриптов (ISE) в Visual Studio Code — включить режим ISE.</span><span class="sxs-lookup"><span data-stu-id="faa56-108">The easiest way to replicate the ISE experience in Visual Studio Code is by turning on "ISE Mode".</span></span>
<span data-ttu-id="faa56-109">Для этого откройте палитру команд (<kbd>F1</kbd> или <kbd>CTRL</kbd>+<kbd>SHIFT</kbd>+<kbd>P</kbd> или <kbd>CMD</kbd>+<kbd>SHIFT</kbd>+<kbd>P</kbd> в macOS) и введите "ISE Mode" (Режим ISE).</span><span class="sxs-lookup"><span data-stu-id="faa56-109">To do this, open the command pallet (<kbd>F1</kbd> OR <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> OR <kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> on macOS) and type in "ISE Mode".</span></span>
<span data-ttu-id="faa56-110">Выберите в списке пункт "PowerShell: Enable ISE Mode" (PowerShell: включить режим ISE).</span><span class="sxs-lookup"><span data-stu-id="faa56-110">Select "PowerShell: Enable ISE Mode" from the list.</span></span>

<span data-ttu-id="faa56-111">Эта команда автоматически применяет многие параметры, описанные в этом документе.</span><span class="sxs-lookup"><span data-stu-id="faa56-111">This command will apply a lot of the settings found in this document automatically.</span></span>
<span data-ttu-id="faa56-112">Результат имеет следующий вид:</span><span class="sxs-lookup"><span data-stu-id="faa56-112">The result looks like this:</span></span>

![Режим ISE](media/How-To-Replicate-the-ISE-Experience-In-VSCode/3-ise-mode.png)

<span data-ttu-id="faa56-114">В оставшейся части этой статьи приводятся более подробные сведения о параметрах в режиме ISE и некоторых дополнительных параметрах.</span><span class="sxs-lookup"><span data-stu-id="faa56-114">The rest of this article includes more detailed information on settings in ISE Mode and some additional settings.</span></span>

## <a name="key-bindings"></a><span data-ttu-id="faa56-115">Сочетания клавиш</span><span class="sxs-lookup"><span data-stu-id="faa56-115">Key bindings</span></span>

| <span data-ttu-id="faa56-116">Компонент</span><span class="sxs-lookup"><span data-stu-id="faa56-116">Function</span></span>                              | <span data-ttu-id="faa56-117">Привязка интегрированной среды сценариев</span><span class="sxs-lookup"><span data-stu-id="faa56-117">ISE Binding</span></span>                  | <span data-ttu-id="faa56-118">Привязка VSCode</span><span class="sxs-lookup"><span data-stu-id="faa56-118">VSCode Binding</span></span>                              |
| ----------------                      | -----------                  | --------------                              |
| <span data-ttu-id="faa56-119">Прерывание и остановка отладчика</span><span class="sxs-lookup"><span data-stu-id="faa56-119">Interrupt and break debugger</span></span>          | <span data-ttu-id="faa56-120"><kbd>CTRL</kbd>+<kbd>B</kbd></span><span class="sxs-lookup"><span data-stu-id="faa56-120"><kbd>Ctrl</kbd>+<kbd>B</kbd></span></span> | <span data-ttu-id="faa56-121"><kbd>F6</kbd></span><span class="sxs-lookup"><span data-stu-id="faa56-121"><kbd>F6</kbd></span></span>                               |
| <span data-ttu-id="faa56-122">Выполнение текущей строки / выделение текста</span><span class="sxs-lookup"><span data-stu-id="faa56-122">Execute current line/highlighted text</span></span> | <span data-ttu-id="faa56-123"><kbd>F8</kbd></span><span class="sxs-lookup"><span data-stu-id="faa56-123"><kbd>F8</kbd></span></span>                | <span data-ttu-id="faa56-124"><kbd>F8</kbd></span><span class="sxs-lookup"><span data-stu-id="faa56-124"><kbd>F8</kbd></span></span>                               |
| <span data-ttu-id="faa56-125">Список доступных фрагментов</span><span class="sxs-lookup"><span data-stu-id="faa56-125">List available snippets</span></span>               | <span data-ttu-id="faa56-126"><kbd>CTRL</kbd>+<kbd>J</kbd></span><span class="sxs-lookup"><span data-stu-id="faa56-126"><kbd>Ctrl</kbd>+<kbd>J</kbd></span></span> | <span data-ttu-id="faa56-127"><kbd>CTRL</kbd>+<kbd>ALT</kbd>+<kbd>J</kbd></span><span class="sxs-lookup"><span data-stu-id="faa56-127"><kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>J</kbd></span></span> |

### <a name="custom-key-bindings"></a><span data-ttu-id="faa56-128">Сочетания клавиш, настраиваемые пользователем</span><span class="sxs-lookup"><span data-stu-id="faa56-128">Custom Key bindings</span></span>

<span data-ttu-id="faa56-129">Также в VSCode можно [настраивать собственные сочетания клавиш](https://code.visualstudio.com/docs/getstarted/keybindings#_custom-keybindings-for-refactorings).</span><span class="sxs-lookup"><span data-stu-id="faa56-129">You can [configure your own key bindings](https://code.visualstudio.com/docs/getstarted/keybindings#_custom-keybindings-for-refactorings) in VSCode as well.</span></span>

## <a name="simplified-ise-like-ui"></a><span data-ttu-id="faa56-130">Упрощенный интерфейс, как в интегрированной среде сценариев</span><span class="sxs-lookup"><span data-stu-id="faa56-130">Simplified ISE-like UI</span></span>

<span data-ttu-id="faa56-131">Если вы хотите упростить пользовательский интерфейс Visual Studio Code, чтобы он стал больше похож на интерфейс интегрированной среды сценариев, примените эти два параметра:</span><span class="sxs-lookup"><span data-stu-id="faa56-131">If you're looking to simplify the Visual Studio Code UI to look more closely to the UI of the ISE, apply these two settings:</span></span>

```json
"workbench.activityBar.visible": false,
"debug.openDebug": "neverOpen",
```

> [!NOTE]
> <span data-ttu-id="faa56-132">Эти параметры включены в [режим ISE](#ise-mode).</span><span class="sxs-lookup"><span data-stu-id="faa56-132">These settings are included in ["ISE Mode"](#ise-mode).</span></span>

<span data-ttu-id="faa56-133">Это скроет разделы с панелью действий и боковой панелью отладки в красной области, как на изображении ниже.</span><span class="sxs-lookup"><span data-stu-id="faa56-133">This will hide the "Activity Bar" and the "Debug Side Bar" sections below inside of the red box:</span></span>

![Выделенный раздел с панелью действий и боковой панелью отладки](media/How-To-Replicate-the-ISE-Experience-In-VSCode/1-highlighted-sidebar.png)

<span data-ttu-id="faa56-135">В итоге представление будет выглядеть так:</span><span class="sxs-lookup"><span data-stu-id="faa56-135">The end result looks like this:</span></span>

![Упрощенное представление VS Code](media/How-To-Replicate-the-ISE-Experience-In-VSCode/2-simplified-ui.png)

## <a name="tab-completion"></a><span data-ttu-id="faa56-137">Заполнение нажатием клавиши TAB</span><span class="sxs-lookup"><span data-stu-id="faa56-137">Tab completion</span></span>

<span data-ttu-id="faa56-138">Чтобы включить заполнение нажатием клавиши TAB (похожее на интегрированную среду сценариев), добавьте следующий параметр.</span><span class="sxs-lookup"><span data-stu-id="faa56-138">To enable more ISE-like tab completion, add this setting:</span></span>

```json
"editor.tabCompletion": "on",
```

> [!NOTE]
> <span data-ttu-id="faa56-139">Данный параметр был добавлен в VSCode напрямую (вместо расширения).</span><span class="sxs-lookup"><span data-stu-id="faa56-139">This setting was added directly to VSCode (rather than in the extension).</span></span> <span data-ttu-id="faa56-140">Его поведение определяется напрямую VSCode. Его невозможно изменить с помощью расширения.</span><span class="sxs-lookup"><span data-stu-id="faa56-140">Its behavior is determined by VSCode directly and cannot be changed by the extension.</span></span>

> [!NOTE]
> <span data-ttu-id="faa56-141">Этот параметр включен в [режим ISE](#ise-mode).</span><span class="sxs-lookup"><span data-stu-id="faa56-141">This setting is included in ["ISE Mode"](#ise-mode).</span></span>

## <a name="no-focus-on-console-when-executing"></a><span data-ttu-id="faa56-142">Отсутствие фокуса в консоли во время выполнения</span><span class="sxs-lookup"><span data-stu-id="faa56-142">No focus on console when executing</span></span>

<span data-ttu-id="faa56-143">Чтобы сохранить фокус в редакторе во время выполнения с помощью клавиши <kbd>F8</kbd>, выполните следующее.</span><span class="sxs-lookup"><span data-stu-id="faa56-143">To keep the focus in the editor when you execute with <kbd>F8</kbd>:</span></span>

```json
"powershell.integratedConsole.focusConsoleOnExecute": false
```

> [!NOTE]
> <span data-ttu-id="faa56-144">Этот параметр включен в [режим ISE](#ise-mode).</span><span class="sxs-lookup"><span data-stu-id="faa56-144">This setting is included in ["ISE Mode"](#ise-mode).</span></span>

<span data-ttu-id="faa56-145">Значение по умолчанию `true` устанавливается в соответствии с требованиями к поддержке специальных возможностей.</span><span class="sxs-lookup"><span data-stu-id="faa56-145">The default is `true` for accessibility purposes.</span></span>

## <a name="dont-start-integrated-console-on-startup"></a><span data-ttu-id="faa56-146">Интегрированную консоль не следует запускать при начальной загрузке</span><span class="sxs-lookup"><span data-stu-id="faa56-146">Don't start integrated console on startup</span></span>

<span data-ttu-id="faa56-147">Чтобы остановить запуск интегрированной консоли при начальной загрузке, установите следующий параметр.</span><span class="sxs-lookup"><span data-stu-id="faa56-147">To stop the integrated console on startup, set:</span></span>

```json
"powershell.integratedConsole.showOnStartup": false
```

> [!NOTE]
> <span data-ttu-id="faa56-148">Тем не менее фоновый процесс PowerShell все равно запустится, так как он предоставляет IntelliSense, анализ сценариев, навигацию по символам и т. д. Консоль не будет отображаться.</span><span class="sxs-lookup"><span data-stu-id="faa56-148">The background PowerShell process will still start since that provides IntelliSense, script analysis, symbol navigation, etc. But the console won't be shown.</span></span>

## <a name="assume-files-are-powershell-by-default"></a><span data-ttu-id="faa56-149">Предположим, что по умолчанию файлы относятся к PowerShell</span><span class="sxs-lookup"><span data-stu-id="faa56-149">Assume files are PowerShell by default</span></span>

<span data-ttu-id="faa56-150">Чтобы создать новые файлы без имени, по умолчанию следует зарегистрироваться в качестве PowerShell.</span><span class="sxs-lookup"><span data-stu-id="faa56-150">To make new/untitled files, register as PowerShell by default:</span></span>

```json
"files.defaultLanguage": "powershell",
```

> [!NOTE]
> <span data-ttu-id="faa56-151">Этот параметр включен в [режим ISE](#ise-mode).</span><span class="sxs-lookup"><span data-stu-id="faa56-151">This setting is included in ["ISE Mode"](#ise-mode).</span></span>

## <a name="color-scheme"></a><span data-ttu-id="faa56-152">Цветовая схема</span><span class="sxs-lookup"><span data-stu-id="faa56-152">Color scheme</span></span>

<span data-ttu-id="faa56-153">Существует большое количество тем интегрированной среды сценариев, которые доступны для VSCode, предназначенные для того, чтобы сделать редактор более похожим на интегрированную среду сценариев.</span><span class="sxs-lookup"><span data-stu-id="faa56-153">There are a number of ISE themes available for VSCode to make the editor look much more like the ISE.</span></span>

<span data-ttu-id="faa56-154">В [Палитра команд] введите `theme`, чтобы получить `Preferences: Color Theme`, а затем нажмите <kbd>ВВОД</kbd>.</span><span class="sxs-lookup"><span data-stu-id="faa56-154">In the [Command Palette] type `theme` to get `Preferences: Color Theme` and press <kbd>Enter</kbd>.</span></span>
<span data-ttu-id="faa56-155">В раскрывающемся списке выберите `PowerShell ISE`.</span><span class="sxs-lookup"><span data-stu-id="faa56-155">In the drop-down list, select `PowerShell ISE`.</span></span>

<span data-ttu-id="faa56-156">Эту тему можно установить в параметрах следующим образом.</span><span class="sxs-lookup"><span data-stu-id="faa56-156">You can set this theme in the settings with:</span></span>

```json
"workbench.colorTheme": "PowerShell ISE",
```

> [!NOTE]
> <span data-ttu-id="faa56-157">Этот параметр включен в [режим ISE](#ise-mode).</span><span class="sxs-lookup"><span data-stu-id="faa56-157">This setting is included in ["ISE Mode"](#ise-mode).</span></span>

## <a name="powershell-command-explorer"></a><span data-ttu-id="faa56-158">Команды обозревателя PowerShell</span><span class="sxs-lookup"><span data-stu-id="faa56-158">PowerShell Command Explorer</span></span>

<span data-ttu-id="faa56-159">Благодаря работе, проделанной [@corbob](https://github.com/corbob), теперь расширение PowerShell обладает начальными командами обозревателя.</span><span class="sxs-lookup"><span data-stu-id="faa56-159">Thanks to the work of [@corbob](https://github.com/corbob), the PowerShell extension has the beginnings of its own command explorer.</span></span>

<span data-ttu-id="faa56-160">В [Палитра команд] введите `PowerShell Command Explorer` и нажмите <kbd>ВВОД</kbd>.</span><span class="sxs-lookup"><span data-stu-id="faa56-160">In the [Command Palette], enter `PowerShell Command Explorer` and press <kbd>Enter</kbd>.</span></span>

> [!NOTE]
> <span data-ttu-id="faa56-161">В [режиме ISE](#ise-mode) они отображаются автоматически.</span><span class="sxs-lookup"><span data-stu-id="faa56-161">This is shown automatically in ["ISE Mode"](#ise-mode).</span></span>

## <a name="open-in-the-ise"></a><span data-ttu-id="faa56-162">Открытие в интегрированной среде сценариев</span><span class="sxs-lookup"><span data-stu-id="faa56-162">Open in the ISE</span></span>

<span data-ttu-id="faa56-163">Если вам понадобится открыть файл в интегрированной среде сценариев, то вы также можете использовать <kbd>SHIFT</kbd>+<kbd>ALT</kbd>+<kbd>P</kbd>.</span><span class="sxs-lookup"><span data-stu-id="faa56-163">If you end up wanting to open a file in the ISE anyway, you can use <kbd>Shift</kbd>+<kbd>Alt</kbd>+<kbd>P</kbd>.</span></span>

## <a name="other-resources"></a><span data-ttu-id="faa56-164">Другие ресурсы</span><span class="sxs-lookup"><span data-stu-id="faa56-164">Other resources</span></span>

- <span data-ttu-id="faa56-165">На веб-сайте 4sysops можно найти [замечательную статью](https://4sysops.com/archives/make-visual-studio-code-look-and-behave-like-powershell-ise/) о настройках VSCode, которые приблизят ее к интегрированной среде сценариев.</span><span class="sxs-lookup"><span data-stu-id="faa56-165">4sysops has [a great article](https://4sysops.com/archives/make-visual-studio-code-look-and-behave-like-powershell-ise/) on configuring VSCode to be more like the ISE.</span></span>
- <span data-ttu-id="faa56-166">Также Майк Ф. Роббинс (Mike F Robbins) написал [отличную статью](https://mikefrobbins.com/2017/08/24/how-to-install-visual-studio-code-and-configure-it-as-a-replacement-for-the-powershell-ise/) о настройке VSCode.</span><span class="sxs-lookup"><span data-stu-id="faa56-166">Mike F Robbins has [a great post](https://mikefrobbins.com/2017/08/24/how-to-install-visual-studio-code-and-configure-it-as-a-replacement-for-the-powershell-ise/) on setting up VSCode.</span></span>
- <span data-ttu-id="faa56-167">Во время изучения PowerShell можно ознакомится с [информативной статьей](https://www.learnpwsh.com/setup-vs-code-for-powershell/) о настройке VSCode для работы с PowerShell.</span><span class="sxs-lookup"><span data-stu-id="faa56-167">Learn PowerShell has [an excellent write up](https://www.learnpwsh.com/setup-vs-code-for-powershell/) on getting VSCode setup for PowerShell.</span></span>

## <a name="more-settings"></a><span data-ttu-id="faa56-168">Дополнительные параметры</span><span class="sxs-lookup"><span data-stu-id="faa56-168">More settings</span></span>

<span data-ttu-id="faa56-169">Если вам известны дополнительные способы сделать VSCode более удобным для пользователей интегрированной среды разработки, внесите их в этот документ. Если существует конфигурация совместимости, которую вы не можете включить, не медлите и [создайте запрос](https://github.com/PowerShell/vscode-powershell/issues/new/choose).</span><span class="sxs-lookup"><span data-stu-id="faa56-169">If you know of more ways to make VSCode feel more familiar for ISE users, contribute to this doc. If there's a compatibility configuration you're looking for, but you can't find any way to enable it, [open an issue](https://github.com/PowerShell/vscode-powershell/issues/new/choose) and ask away!</span></span>

<span data-ttu-id="faa56-170">Мы всегда рады содействию и запросам на включение внесенных изменений.</span><span class="sxs-lookup"><span data-stu-id="faa56-170">We're always happy to accept PRs and contributions as well!</span></span>

## <a name="vscode-tips"></a><span data-ttu-id="faa56-171">Советы по работе в VSCode</span><span class="sxs-lookup"><span data-stu-id="faa56-171">VSCode Tips</span></span>

### <a name="command-palette"></a><span data-ttu-id="faa56-172">Палитра команд</span><span class="sxs-lookup"><span data-stu-id="faa56-172">Command Palette</span></span>

<span data-ttu-id="faa56-173"><kbd>F1</kbd> или <kbd>CTRL</kbd>+<kbd>SHIFT</kbd>+<kbd>P</kbd> (<kbd>Cmd</kbd>+<kbd>SHIFT</kbd>+<kbd>P</kbd> на macOS)</span><span class="sxs-lookup"><span data-stu-id="faa56-173"><kbd>F1</kbd> OR <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> (<kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> on macOS)</span></span>

<span data-ttu-id="faa56-174">Удобный способ выполнения команд в VSCode.</span><span class="sxs-lookup"><span data-stu-id="faa56-174">A handy way of executing commands in VSCode.</span></span>
<span data-ttu-id="faa56-175">Дополнительные сведения см. в [документации по VSCode](https://code.visualstudio.com/docs/getstarted/userinterface#_command-palette).</span><span class="sxs-lookup"><span data-stu-id="faa56-175">For more information, see [the VSCode docs](https://code.visualstudio.com/docs/getstarted/userinterface#_command-palette).</span></span>

[Палитра команд]: #command-palette
[Command Palette]: #command-palette
