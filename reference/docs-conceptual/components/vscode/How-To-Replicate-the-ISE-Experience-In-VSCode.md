---
title: Репликация функций интегрированной среды скриптов в Visual Studio Code
description: Репликация функций интегрированной среды скриптов в Visual Studio Code
ms.date: 08/06/2018
ms.openlocfilehash: d5542e9a3a48b1ae64356309be669418edf6c79e
ms.sourcegitcommit: a6e54a305fdeb6482321c77da8066d2f991c93e1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2019
ms.locfileid: "74117472"
---
# <a name="how-to-replicate-the-ise-experience-in-visual-studio-code"></a><span data-ttu-id="05962-103">Репликация функций интегрированной среды скриптов в Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="05962-103">How to replicate the ISE experience in Visual Studio Code</span></span>

<span data-ttu-id="05962-104">В то время, как расширение PowerShell для VSCode не совсем совместимо с интегрированной средой сценариев PowerShell, существуют функции, использование которых позволит пользователям интегрированной среды сценариев почувствовать себя более свободно в VSCode.</span><span class="sxs-lookup"><span data-stu-id="05962-104">While the PowerShell extension for VSCode doesn't seek complete feature parity with the PowerShell ISE, there are features in place to make the VSCode experience more natural for users of the ISE.</span></span>

<span data-ttu-id="05962-105">В этой статье приведен список параметров, настраиваемых в VSCode, которые смогут облегчить ее использование для пользователей интегрированной среды сценариев.</span><span class="sxs-lookup"><span data-stu-id="05962-105">This document tries to list settings you can configure in VSCode to make the user experience a bit more familiar compared to the ISE.</span></span>

## <a name="key-bindings"></a><span data-ttu-id="05962-106">Сочетания клавиш</span><span class="sxs-lookup"><span data-stu-id="05962-106">Key bindings</span></span>

| <span data-ttu-id="05962-107">Функция</span><span class="sxs-lookup"><span data-stu-id="05962-107">Function</span></span>                              | <span data-ttu-id="05962-108">Привязка интегрированной среды сценариев</span><span class="sxs-lookup"><span data-stu-id="05962-108">ISE Binding</span></span>                  | <span data-ttu-id="05962-109">Привязка VSCode</span><span class="sxs-lookup"><span data-stu-id="05962-109">VSCode Binding</span></span>                              |
| ----------------                      | -----------                  | --------------                              |
| <span data-ttu-id="05962-110">Прерывание и остановка отладчика</span><span class="sxs-lookup"><span data-stu-id="05962-110">Interrupt and break debugger</span></span>          | <span data-ttu-id="05962-111"><kbd>CTRL</kbd>+<kbd>B</kbd></span><span class="sxs-lookup"><span data-stu-id="05962-111"><kbd>Ctrl</kbd>+<kbd>B</kbd></span></span> | <span data-ttu-id="05962-112"><kbd>F6</kbd></span><span class="sxs-lookup"><span data-stu-id="05962-112"><kbd>F6</kbd></span></span>                               |
| <span data-ttu-id="05962-113">Выполнение текущей строки / выделение текста</span><span class="sxs-lookup"><span data-stu-id="05962-113">Execute current line/highlighted text</span></span> | <span data-ttu-id="05962-114"><kbd>F8</kbd></span><span class="sxs-lookup"><span data-stu-id="05962-114"><kbd>F8</kbd></span></span>                | <span data-ttu-id="05962-115"><kbd>F8</kbd></span><span class="sxs-lookup"><span data-stu-id="05962-115"><kbd>F8</kbd></span></span>                               |
| <span data-ttu-id="05962-116">Список доступных фрагментов</span><span class="sxs-lookup"><span data-stu-id="05962-116">List available snippets</span></span>               | <span data-ttu-id="05962-117"><kbd>CTRL</kbd>+<kbd>J</kbd></span><span class="sxs-lookup"><span data-stu-id="05962-117"><kbd>Ctrl</kbd>+<kbd>J</kbd></span></span> | <span data-ttu-id="05962-118"><kbd>CTRL</kbd>+<kbd>ALT</kbd>+<kbd>J</kbd></span><span class="sxs-lookup"><span data-stu-id="05962-118"><kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>J</kbd></span></span> |

### <a name="custom-key-bindings"></a><span data-ttu-id="05962-119">Сочетания клавиш, настраиваемые пользователем</span><span class="sxs-lookup"><span data-stu-id="05962-119">Custom Key bindings</span></span>

<span data-ttu-id="05962-120">Также в VSCode можно [настраивать собственные сочетания клавиш](https://code.visualstudio.com/docs/getstarted/keybindings#_custom-keybindings-for-refactorings).</span><span class="sxs-lookup"><span data-stu-id="05962-120">You can [configure your own key bindings](https://code.visualstudio.com/docs/getstarted/keybindings#_custom-keybindings-for-refactorings) in VSCode as well.</span></span>

## <a name="simplified-ise-like-ui"></a><span data-ttu-id="05962-121">Упрощенный интерфейс, как в интегрированной среде сценариев</span><span class="sxs-lookup"><span data-stu-id="05962-121">Simplified ISE-like UI</span></span>

<span data-ttu-id="05962-122">Если вы хотите упростить пользовательский интерфейс Visual Studio Code, чтобы он стал больше похож на интерфейс интегрированной среды сценариев, примените эти два параметра:</span><span class="sxs-lookup"><span data-stu-id="05962-122">If you're looking to simplify the Visual Studio Code UI to look more closely to the UI of the ISE, apply these two settings:</span></span>

```json
"workbench.activityBar.visible": false,
"debug.openDebug": "neverOpen",
```

<span data-ttu-id="05962-123">Это скроет разделы с панелью действий и боковой панелью отладки в красной области, как на изображении ниже.</span><span class="sxs-lookup"><span data-stu-id="05962-123">This will hide the "Activity Bar" and the "Debug Side Bar" sections below inside of the red box:</span></span>

![Выделенный раздел с панелью действий и боковой панелью отладки](images/How-To-Replicate-the-ISE-Experience-In-VSCode/1-highlighted-sidebar.png)

<span data-ttu-id="05962-125">В итоге представление будет выглядеть так:</span><span class="sxs-lookup"><span data-stu-id="05962-125">The end result looks like this:</span></span>

![Упрощенное представление VS Code](images/How-To-Replicate-the-ISE-Experience-In-VSCode/2-simplified-ui.png)

## <a name="tab-completion"></a><span data-ttu-id="05962-127">Заполнение нажатием клавиши TAB</span><span class="sxs-lookup"><span data-stu-id="05962-127">Tab completion</span></span>

<span data-ttu-id="05962-128">Чтобы включить заполнение нажатием клавиши TAB (похожее на интегрированную среду сценариев), добавьте следующий параметр.</span><span class="sxs-lookup"><span data-stu-id="05962-128">To enable more ISE-like tab completion, add this setting:</span></span>

```json
"editor.tabCompletion": "on",
```

> [!NOTE]
> <span data-ttu-id="05962-129">Данный параметр был добавлен в VSCode напрямую (вместо расширения).</span><span class="sxs-lookup"><span data-stu-id="05962-129">This setting was added directly to VSCode (rather than in the extension).</span></span> <span data-ttu-id="05962-130">Его поведение определяется напрямую VSCode. Его невозможно изменить с помощью расширения.</span><span class="sxs-lookup"><span data-stu-id="05962-130">Its behavior is determined by VSCode directly and cannot be changed by the extension.</span></span>

## <a name="no-focus-on-console-when-executing"></a><span data-ttu-id="05962-131">Отсутствие фокуса на консоли во время выполнения</span><span class="sxs-lookup"><span data-stu-id="05962-131">No focus on console when executing</span></span>

<span data-ttu-id="05962-132">Чтобы сохранить фокус в редакторе во время выполнения с помощью клавиши <kbd>F8</kbd>, выполните следующее.</span><span class="sxs-lookup"><span data-stu-id="05962-132">To keep the focus in the editor when you execute with <kbd>F8</kbd>:</span></span>

```json
"powershell.integratedConsole.focusConsoleOnExecute": false
```

<span data-ttu-id="05962-133">Для специальных возможностей значением по умолчанию будет `true`.</span><span class="sxs-lookup"><span data-stu-id="05962-133">The default is `true` for accessibility purposes.</span></span>

## <a name="dont-start-integrated-console-on-startup"></a><span data-ttu-id="05962-134">Интегрированную консоль не следует запускать при начальной загрузке</span><span class="sxs-lookup"><span data-stu-id="05962-134">Don't start integrated console on startup</span></span>

<span data-ttu-id="05962-135">Чтобы остановить запуск интегрированной консоли при начальной загрузке, установите следующий параметр.</span><span class="sxs-lookup"><span data-stu-id="05962-135">To stop the integrated console on startup, set:</span></span>

```json
"powershell.integratedConsole.showOnStartup": false
```

> [!NOTE]
> <span data-ttu-id="05962-136">Тем не менее фоновый процесс PowerShell все равно запустится, так как он предоставляет IntelliSense, анализ сценариев, навигацию по символам и т. д. Консоль не будет отображаться.</span><span class="sxs-lookup"><span data-stu-id="05962-136">The background PowerShell process will still start since that provides IntelliSense, script analysis, symbol navigation, etc. But the console won't be shown.</span></span>

## <a name="assume-files-are-powershell-by-default"></a><span data-ttu-id="05962-137">Предположим, что по умолчанию файлы относятся к PowerShell</span><span class="sxs-lookup"><span data-stu-id="05962-137">Assume files are PowerShell by default</span></span>

<span data-ttu-id="05962-138">Чтобы создать новые файлы без имени, по умолчанию следует зарегистрироваться в качестве PowerShell.</span><span class="sxs-lookup"><span data-stu-id="05962-138">To make new/untitled files, register as PowerShell by default:</span></span>

```json
"files.defaultLanguage": "powershell",
```

## <a name="color-scheme"></a><span data-ttu-id="05962-139">Цветовая схема</span><span class="sxs-lookup"><span data-stu-id="05962-139">Color scheme</span></span>

<span data-ttu-id="05962-140">Существует большое количество тем интегрированной среды сценариев, которые доступны для VSCode, предназначенные для того, чтобы сделать редактор более похожим на интегрированную среду сценариев.</span><span class="sxs-lookup"><span data-stu-id="05962-140">There are a number of ISE themes available for VSCode to make the editor look much more like the ISE.</span></span>

<span data-ttu-id="05962-141">В [Палитра команд] введите `theme`, чтобы получить `Preferences: Color Theme`, а затем нажмите <kbd>ВВОД</kbd>.</span><span class="sxs-lookup"><span data-stu-id="05962-141">In the [Command Palette] type `theme` to get `Preferences: Color Theme` and press <kbd>Enter</kbd>.</span></span>
<span data-ttu-id="05962-142">В раскрывающемся списке выберите `PowerShell ISE`.</span><span class="sxs-lookup"><span data-stu-id="05962-142">In the drop-down list, select `PowerShell ISE`.</span></span>

<span data-ttu-id="05962-143">Эту тему можно установить в параметрах следующим образом.</span><span class="sxs-lookup"><span data-stu-id="05962-143">You can set this theme in the settings with:</span></span>

```json
"workbench.colorTheme": "PowerShell ISE",
```

## <a name="powershell-command-explorer"></a><span data-ttu-id="05962-144">Команды обозревателя PowerShell</span><span class="sxs-lookup"><span data-stu-id="05962-144">PowerShell Command Explorer</span></span>

<span data-ttu-id="05962-145">Благодаря работе, проделанной [@corbob](https://github.com/corbob), теперь расширение PowerShell обладает начальными командами обозревателя.</span><span class="sxs-lookup"><span data-stu-id="05962-145">Thanks to the work of [@corbob](https://github.com/corbob), the PowerShell extension has the beginnings of its own command explorer.</span></span>

<span data-ttu-id="05962-146">В [Палитра команд] введите `PowerShell Command Explorer` и нажмите <kbd>ВВОД</kbd>.</span><span class="sxs-lookup"><span data-stu-id="05962-146">In the [Command Palette], enter `PowerShell Command Explorer` and press <kbd>Enter</kbd>.</span></span>

## <a name="open-in-the-ise"></a><span data-ttu-id="05962-147">Открытие в интегрированной среде сценариев</span><span class="sxs-lookup"><span data-stu-id="05962-147">Open in the ISE</span></span>

<span data-ttu-id="05962-148">Если вам понадобится открыть файл в интегрированной среде сценариев, то вы также можете использовать <kbd>SHIFT</kbd>+<kbd>ALT</kbd>+<kbd>P</kbd>.</span><span class="sxs-lookup"><span data-stu-id="05962-148">If you end up wanting to open a file in the ISE anyway, you can use <kbd>Shift</kbd>+<kbd>Alt</kbd>+<kbd>P</kbd>.</span></span>

## <a name="other-resources"></a><span data-ttu-id="05962-149">Другие ресурсы</span><span class="sxs-lookup"><span data-stu-id="05962-149">Other resources</span></span>

- <span data-ttu-id="05962-150">На веб-сайте 4sysops можно найти [замечательную статью](https://4sysops.com/archives/make-visual-studio-code-look-and-behave-like-powershell-ise/) о настройках VSCode, которые приблизят ее к интегрированной среде сценариев.</span><span class="sxs-lookup"><span data-stu-id="05962-150">4sysops has [a great article](https://4sysops.com/archives/make-visual-studio-code-look-and-behave-like-powershell-ise/) on configuring VSCode to be more like the ISE.</span></span>
- <span data-ttu-id="05962-151">Также Майк Ф. Роббинс (Mike F Robbins) написал [отличную статью](https://mikefrobbins.com/2017/08/24/how-to-install-visual-studio-code-and-configure-it-as-a-replacement-for-the-powershell-ise/) о настройке VSCode.</span><span class="sxs-lookup"><span data-stu-id="05962-151">Mike F Robbins has [a great post](https://mikefrobbins.com/2017/08/24/how-to-install-visual-studio-code-and-configure-it-as-a-replacement-for-the-powershell-ise/) on setting up VSCode.</span></span>
- <span data-ttu-id="05962-152">Во время изучения PowerShell можно ознакомится с [информативной статьей](https://www.learnpwsh.com/setup-vs-code-for-powershell/) о настройке VSCode для работы с PowerShell.</span><span class="sxs-lookup"><span data-stu-id="05962-152">Learn PowerShell has [an excellent write up](https://www.learnpwsh.com/setup-vs-code-for-powershell/) on getting VSCode setup for PowerShell.</span></span>

## <a name="more-settings"></a><span data-ttu-id="05962-153">Дополнительные параметры</span><span class="sxs-lookup"><span data-stu-id="05962-153">More settings</span></span>

<span data-ttu-id="05962-154">Если вам известны дополнительные способы сделать VSCode более удобным для пользователей интегрированной среды разработки, внесите их в этот документ. Если существует конфигурация совместимости, которую вы не можете включить, не медлите и [создайте запрос](https://github.com/PowerShell/vscode-powershell/issues/new/choose).</span><span class="sxs-lookup"><span data-stu-id="05962-154">If you know of more ways to make VSCode feel more familiar for ISE users, contribute to this doc. If there's a compatibility configuration you're looking for, but you can't find any way to enable it, [open an issue](https://github.com/PowerShell/vscode-powershell/issues/new/choose) and ask away!</span></span>

<span data-ttu-id="05962-155">Мы всегда рады содействию и запросам на включение внесенных изменений.</span><span class="sxs-lookup"><span data-stu-id="05962-155">We're always happy to accept PRs and contributions as well!</span></span>

## <a name="vscode-tips"></a><span data-ttu-id="05962-156">Советы по работе в VSCode</span><span class="sxs-lookup"><span data-stu-id="05962-156">VSCode Tips</span></span>

### <a name="command-palette"></a><span data-ttu-id="05962-157">Палитра команд</span><span class="sxs-lookup"><span data-stu-id="05962-157">Command Palette</span></span>

<span data-ttu-id="05962-158"><kbd>F1</kbd> или <kbd>CTRL</kbd>+<kbd>SHIFT</kbd>+<kbd>P</kbd> (<kbd>Cmd</kbd>+<kbd>SHIFT</kbd>+<kbd>P</kbd> на macOS)</span><span class="sxs-lookup"><span data-stu-id="05962-158"><kbd>F1</kbd> OR <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> (<kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> on macOS)</span></span>

<span data-ttu-id="05962-159">Удобный способ выполнения команд в VSCode.</span><span class="sxs-lookup"><span data-stu-id="05962-159">A handy way of executing commands in VSCode.</span></span>
<span data-ttu-id="05962-160">Дополнительные сведения см. в [документации по VSCode](https://code.visualstudio.com/docs/getstarted/userinterface#_command-palette).</span><span class="sxs-lookup"><span data-stu-id="05962-160">For more information, see [the VSCode docs](https://code.visualstudio.com/docs/getstarted/userinterface#_command-palette).</span></span>

[Палитра команд]: #command-palette
[Command Palette]: #command-palette
