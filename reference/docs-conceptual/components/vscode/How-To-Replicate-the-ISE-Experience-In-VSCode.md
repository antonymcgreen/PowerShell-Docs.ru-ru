---
title: Репликация функций интегрированной среды скриптов в Visual Studio Code
description: Репликация функций интегрированной среды скриптов в Visual Studio Code
ms.date: 08/06/2018
ms.openlocfilehash: 983da850c13d72bcdc7b2d33970c6e9e06b3d869
ms.sourcegitcommit: 9df29dfc637191b62ca591893c251c1e02d4eb4c
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 01/04/2019
ms.locfileid: "54012489"
---
# <a name="how-to-replicate-the-ise-experience-in-visual-studio-code"></a><span data-ttu-id="8d1df-103">Репликация функций интегрированной среды скриптов в Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="8d1df-103">How to replicate the ISE experience in Visual Studio Code</span></span>

<span data-ttu-id="8d1df-104">Хотя модуль PowerShell для VSCode не поиск полный функционально полностью интегрированной среде Сценариев PowerShell, позволяющие упростить процесс VSCode более естественным для пользователей интегрированной среды сценариев нет компонентов.</span><span class="sxs-lookup"><span data-stu-id="8d1df-104">While the PowerShell extension for VSCode doesn't seek complete feature parity with the PowerShell ISE, there are features in place to make the VSCode experience more natural for users of the ISE.</span></span>

<span data-ttu-id="8d1df-105">В этом документе пытается получить список параметров, которые можно настроить в Visual Studio Code для улучшить интерфейс чуть более привычной, по сравнению с в интегрированную среду сценариев пользователя.</span><span class="sxs-lookup"><span data-stu-id="8d1df-105">This document tries to list settings you can configure in VSCode to make the user experience a bit more familiar compared to the ISE.</span></span>

## <a name="key-bindings"></a><span data-ttu-id="8d1df-106">Сочетания клавиш</span><span class="sxs-lookup"><span data-stu-id="8d1df-106">Key bindings</span></span>

| <span data-ttu-id="8d1df-107">Функция</span><span class="sxs-lookup"><span data-stu-id="8d1df-107">Function</span></span>                              | <span data-ttu-id="8d1df-108">Интегрированная среда Сценариев привязки</span><span class="sxs-lookup"><span data-stu-id="8d1df-108">ISE Binding</span></span>                  | <span data-ttu-id="8d1df-109">VSCode привязки</span><span class="sxs-lookup"><span data-stu-id="8d1df-109">VSCode Binding</span></span>                              |
| ----------------                      | -----------                  | --------------                              |
| <span data-ttu-id="8d1df-110">Прерывания и прерывания отладчика</span><span class="sxs-lookup"><span data-stu-id="8d1df-110">Interrupt and break debugger</span></span>          | <span data-ttu-id="8d1df-111"><kbd>CTRL</kbd>+<kbd>B</kbd></span><span class="sxs-lookup"><span data-stu-id="8d1df-111"><kbd>Ctrl</kbd>+<kbd>B</kbd></span></span> | <span data-ttu-id="8d1df-112"><kbd>F6</kbd></span><span class="sxs-lookup"><span data-stu-id="8d1df-112"><kbd>F6</kbd></span></span>                               |
| <span data-ttu-id="8d1df-113">Выполнить текущий текст/выделенной строки</span><span class="sxs-lookup"><span data-stu-id="8d1df-113">Execute current line/highlighted text</span></span> | <span data-ttu-id="8d1df-114"><kbd>F8</kbd></span><span class="sxs-lookup"><span data-stu-id="8d1df-114"><kbd>F8</kbd></span></span>                | <span data-ttu-id="8d1df-115"><kbd>F8</kbd></span><span class="sxs-lookup"><span data-stu-id="8d1df-115"><kbd>F8</kbd></span></span>                               |
| <span data-ttu-id="8d1df-116">Список доступных фрагментов</span><span class="sxs-lookup"><span data-stu-id="8d1df-116">List available snippets</span></span>               | <span data-ttu-id="8d1df-117"><kbd>CTRL</kbd>+<kbd>J</kbd></span><span class="sxs-lookup"><span data-stu-id="8d1df-117"><kbd>Ctrl</kbd>+<kbd>J</kbd></span></span> | <span data-ttu-id="8d1df-118"><kbd>CTRL</kbd>+<kbd>Alt</kbd>+<kbd>J</kbd></span><span class="sxs-lookup"><span data-stu-id="8d1df-118"><kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>J</kbd></span></span> |

### <a name="custom-key-bindings"></a><span data-ttu-id="8d1df-119">Пользовательские привязки ключа</span><span class="sxs-lookup"><span data-stu-id="8d1df-119">Custom Key bindings</span></span>

<span data-ttu-id="8d1df-120">Вы можете [настроить собственные сочетания клавиш](https://code.visualstudio.com/docs/getstarted/keybindings#_custom-keybindings-for-refactorings) в VSCode также.</span><span class="sxs-lookup"><span data-stu-id="8d1df-120">You can [configure your own key bindings](https://code.visualstudio.com/docs/getstarted/keybindings#_custom-keybindings-for-refactorings) in VSCode as well.</span></span>

## <a name="tab-completion"></a><span data-ttu-id="8d1df-121">Заполнение нажатием клавиши TAB</span><span class="sxs-lookup"><span data-stu-id="8d1df-121">Tab completion</span></span>

<span data-ttu-id="8d1df-122">Чтобы включить более интегрированной среды Сценариев по принципу нажатием клавиши TAB, добавьте этот параметр:</span><span class="sxs-lookup"><span data-stu-id="8d1df-122">To enable more ISE-like tab completion, add this setting:</span></span>

```json
"editor.tabCompletion": "on"
```

> [!NOTE]
> <span data-ttu-id="8d1df-123">Этот параметр был добавлен непосредственно в VSCode (а не в расширении).</span><span class="sxs-lookup"><span data-stu-id="8d1df-123">This setting was added directly to VSCode (rather than in the extension).</span></span> <span data-ttu-id="8d1df-124">Его поведение определяется непосредственно VSCode и не может изменяться с помощью расширения.</span><span class="sxs-lookup"><span data-stu-id="8d1df-124">Its behavior is determined by VSCode directly and cannot be changed by the extension.</span></span>

## <a name="no-focus-on-console-when-executing"></a><span data-ttu-id="8d1df-125">Нет сосредоточиться на консоль при выполнении</span><span class="sxs-lookup"><span data-stu-id="8d1df-125">No focus on console when executing</span></span>

<span data-ttu-id="8d1df-126">Чтобы полностью сосредоточиться в редакторе, при выполнении с <kbd>F8</kbd>:</span><span class="sxs-lookup"><span data-stu-id="8d1df-126">To keep the focus in the editor when you execute with <kbd>F8</kbd>:</span></span>

```json
"powershell.integratedConsole.focusConsoleOnExecute": false
```

<span data-ttu-id="8d1df-127">По умолчанию используется `true` для специальных возможностей.</span><span class="sxs-lookup"><span data-stu-id="8d1df-127">The default is `true` for accessibility purposes.</span></span>

## <a name="dont-start-integrated-console-on-startup"></a><span data-ttu-id="8d1df-128">Не выполнять интегрированной консоли при запуске</span><span class="sxs-lookup"><span data-stu-id="8d1df-128">Don't start integrated console on startup</span></span>

<span data-ttu-id="8d1df-129">Чтобы остановить интегрированной консоли при запуске, установите:</span><span class="sxs-lookup"><span data-stu-id="8d1df-129">To stop the integrated console on startup, set:</span></span>

```json
"powershell.integratedConsole.showOnStartup": false
```

> [!NOTE]
> <span data-ttu-id="8d1df-130">Фоновый процесс PowerShell по-прежнему начнется с момента, предоставляющий возможности IntelliSense, анализ сценария, навигацию по символам и т. д. Однако консоль не будет отображаться.</span><span class="sxs-lookup"><span data-stu-id="8d1df-130">The background PowerShell process will still start since that provides IntelliSense, script analysis, symbol navigation, etc. But the console won't be shown.</span></span>

## <a name="assume-files-are-powershell-by-default"></a><span data-ttu-id="8d1df-131">Предположим, что файлы являются PowerShell по умолчанию</span><span class="sxs-lookup"><span data-stu-id="8d1df-131">Assume files are PowerShell by default</span></span>

<span data-ttu-id="8d1df-132">Чтобы сделать новый/без названия файлов, зарегистрируйте как PowerShell, по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="8d1df-132">To make new/untitled files, register as PowerShell by default:</span></span>

```json
"files.defaultLanguage": "powershell"
```

## <a name="color-scheme"></a><span data-ttu-id="8d1df-133">Цветовая схема</span><span class="sxs-lookup"><span data-stu-id="8d1df-133">Color scheme</span></span>

<span data-ttu-id="8d1df-134">Существует ряд темы интегрированной среды Сценариев для VSCode сделать гораздо больше похожи на интегрированную среду Скриптов редактора.</span><span class="sxs-lookup"><span data-stu-id="8d1df-134">There are a number of ISE themes available for VSCode to make the editor look much more like the ISE.</span></span>

<span data-ttu-id="8d1df-135">В [Палитра команд] тип `theme` для получения `Preferences: Color Theme` и нажмите клавишу <kbd>ввод</kbd>.</span><span class="sxs-lookup"><span data-stu-id="8d1df-135">In the [Command Palette] type `theme` to get `Preferences: Color Theme` and press <kbd>Enter</kbd>.</span></span>
<span data-ttu-id="8d1df-136">В раскрывающемся списке выберите `PowerShell ISE`.</span><span class="sxs-lookup"><span data-stu-id="8d1df-136">In the drop-down list, select `PowerShell ISE`.</span></span>

<span data-ttu-id="8d1df-137">В настройках можно задать эту тему:</span><span class="sxs-lookup"><span data-stu-id="8d1df-137">You can set this theme in the settings with:</span></span>

```json
"workbench.colorTheme": "PowerShell ISE"
```

## <a name="powershell-command-explorer"></a><span data-ttu-id="8d1df-138">Обозреватель команды PowerShell</span><span class="sxs-lookup"><span data-stu-id="8d1df-138">PowerShell Command Explorer</span></span>

<span data-ttu-id="8d1df-139">Благодаря работе [ @corbob ](https://github.com/corbob), расширения PowerShell имеет об основах explorer свои собственные команды.</span><span class="sxs-lookup"><span data-stu-id="8d1df-139">Thanks to the work of [@corbob](https://github.com/corbob), the PowerShell extension has the beginnings of its own command explorer.</span></span>

<span data-ttu-id="8d1df-140">В [Палитра команд], введите `PowerShell Command Explorer` и нажмите клавишу <kbd>ввод</kbd>.</span><span class="sxs-lookup"><span data-stu-id="8d1df-140">In the [Command Palette], enter `PowerShell Command Explorer` and press <kbd>Enter</kbd>.</span></span>

## <a name="open-in-the-ise"></a><span data-ttu-id="8d1df-141">Откройте в среде ISE</span><span class="sxs-lookup"><span data-stu-id="8d1df-141">Open in the ISE</span></span>

<span data-ttu-id="8d1df-142">Если вы в итоге нужно открыть файл в интегрированной среде Сценариев в любом случае, вы можете использовать <kbd>Shift</kbd>+<kbd>Alt</kbd>+<kbd>P</kbd>.</span><span class="sxs-lookup"><span data-stu-id="8d1df-142">If you end up wanting to open a file in the ISE anyway, you can use <kbd>Shift</kbd>+<kbd>Alt</kbd>+<kbd>P</kbd>.</span></span>

## <a name="other-resources"></a><span data-ttu-id="8d1df-143">Другие ресурсы</span><span class="sxs-lookup"><span data-stu-id="8d1df-143">Other resources</span></span>

- <span data-ttu-id="8d1df-144">имеет 4sysops [хорошая статья](https://4sysops.com/archives/make-visual-studio-code-look-and-behave-like-powershell-ise/) о настройке Visual Studio Code для быть больше похожи на интегрированную среду Сценариев.</span><span class="sxs-lookup"><span data-stu-id="8d1df-144">4sysops has [a great article](https://4sysops.com/archives/make-visual-studio-code-look-and-behave-like-powershell-ise/) on configuring VSCode to be more like the ISE.</span></span>
- <span data-ttu-id="8d1df-145">Майк Ф. Роббинс имеет [потрясающее сообщение](https://mikefrobbins.com/2017/08/24/how-to-install-visual-studio-code-and-configure-it-as-a-replacement-for-the-powershell-ise/) по настройке VSCode.</span><span class="sxs-lookup"><span data-stu-id="8d1df-145">Mike F Robbins has [a great post](https://mikefrobbins.com/2017/08/24/how-to-install-visual-studio-code-and-configure-it-as-a-replacement-for-the-powershell-ise/) on setting up VSCode.</span></span>
- <span data-ttu-id="8d1df-146">Узнать, имеет PowerShell [отличную записи](https://www.learnpwsh.com/setup-vs-code-for-powershell/) о том, как VSCode установки для PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8d1df-146">Learn PowerShell has [an excellent write up](https://www.learnpwsh.com/setup-vs-code-for-powershell/) on getting VSCode setup for PowerShell.</span></span>

## <a name="more-settings"></a><span data-ttu-id="8d1df-147">Дополнительные параметры</span><span class="sxs-lookup"><span data-stu-id="8d1df-147">More settings</span></span>

<span data-ttu-id="8d1df-148">Если вы знаете Дополнительные способы повышения VSCode показаться более знакомыми пользователям интегрированной среды Сценариев, участвуют в этом документе. Если вы ищете конфигурации совместимости, но не удается найти любым способом, чтобы включить его, [сообщите о них](https://github.com/PowerShell/vscode-powershell/issues/new/choose) и за ответами!</span><span class="sxs-lookup"><span data-stu-id="8d1df-148">If you know of more ways to make VSCode feel more familiar for ISE users, contribute to this doc. If there's a compatibility configuration you're looking for, but you can't find any way to enable it, [open an issue](https://github.com/PowerShell/vscode-powershell/issues/new/choose) and ask away!</span></span>

<span data-ttu-id="8d1df-149">Мы всегда рады принимать запросы на Вытягивание и вклад также!</span><span class="sxs-lookup"><span data-stu-id="8d1df-149">We're always happy to accept PRs and contributions as well!</span></span>

## <a name="vscode-tips"></a><span data-ttu-id="8d1df-150">Советы по VSCode</span><span class="sxs-lookup"><span data-stu-id="8d1df-150">VSCode Tips</span></span>

### <a name="command-palette"></a><span data-ttu-id="8d1df-151">Палитра команд</span><span class="sxs-lookup"><span data-stu-id="8d1df-151">Command Palette</span></span>

<span data-ttu-id="8d1df-152"><kbd>F1</kbd> или <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> (<kbd>Cmd</kbd> + <kbd> Сдвинуть</kbd>+<kbd>P</kbd> в Mac OS)</span><span class="sxs-lookup"><span data-stu-id="8d1df-152"><kbd>F1</kbd> OR <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> (<kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> on macOS)</span></span>

<span data-ttu-id="8d1df-153">Удобным способом выполнения команд в VSCode.</span><span class="sxs-lookup"><span data-stu-id="8d1df-153">A handy way of executing commands in VSCode.</span></span>
<span data-ttu-id="8d1df-154">Дополнительные сведения см. в разделе [документация VSCode](https://code.visualstudio.com/docs/getstarted/userinterface#_command-palette).</span><span class="sxs-lookup"><span data-stu-id="8d1df-154">For more information, see [the VSCode docs](https://code.visualstudio.com/docs/getstarted/userinterface#_command-palette).</span></span>

[Палитра команд]: #command-palette
[Command Palette]: #command-palette
