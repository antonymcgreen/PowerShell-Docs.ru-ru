---
description: Описание способов получения и выполнения команд в журнале команд.
keywords: powershell,командлет
Locale: en-US
ms.date: 05/13/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_history?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_History
ms.openlocfilehash: 64a8fac4f25ac60be58aca8549748b9e4dde6c3b
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93232393"
---
# <a name="about-history"></a><span data-ttu-id="f2818-104">Сведения о журнале</span><span class="sxs-lookup"><span data-stu-id="f2818-104">About History</span></span>

## <a name="short-description"></a><span data-ttu-id="f2818-105">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="f2818-105">Short Description</span></span>
<span data-ttu-id="f2818-106">Описание способов получения и выполнения команд в журнале команд.</span><span class="sxs-lookup"><span data-stu-id="f2818-106">Describes how to get and run commands in the command history.</span></span>

## <a name="long-description"></a><span data-ttu-id="f2818-107">Полное описание</span><span class="sxs-lookup"><span data-stu-id="f2818-107">Long Description</span></span>

<span data-ttu-id="f2818-108">При вводе команды в командной строке PowerShell сохраняет команду в журнале команд.</span><span class="sxs-lookup"><span data-stu-id="f2818-108">When you enter a command at the command prompt, PowerShell saves the command in the command history.</span></span> <span data-ttu-id="f2818-109">Вы можете использовать команды в журнале в качестве записи своей работы.</span><span class="sxs-lookup"><span data-stu-id="f2818-109">You can use the commands in the history as a record of your work.</span></span> <span data-ttu-id="f2818-110">Вы также можете отозвать и выполнить команды из журнала команд.</span><span class="sxs-lookup"><span data-stu-id="f2818-110">And, you can recall and run the commands from the command history.</span></span>

<span data-ttu-id="f2818-111">PowerShell имеет два разных регистратора: Встроенный журнал и журнал, которыми управляет модуль **PSReadLine** .</span><span class="sxs-lookup"><span data-stu-id="f2818-111">PowerShell has two different history providers: the built-in history and the history managed by the **PSReadLine** module.</span></span> <span data-ttu-id="f2818-112">Журналы управляются отдельно, но оба журнала доступны в сеансах, где **PSReadLine** загружается.</span><span class="sxs-lookup"><span data-stu-id="f2818-112">The histories are managed separately, but both histories are available in sessions where **PSReadLine** is loaded.</span></span>

## <a name="using-the-psreadline-history"></a><span data-ttu-id="f2818-113">Использование журнала PSReadLine</span><span class="sxs-lookup"><span data-stu-id="f2818-113">Using the PSReadLine history</span></span>

<span data-ttu-id="f2818-114">Журнал PSReadLine отслеживает команды, используемые во всех сеансах PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f2818-114">The PSReadLine history tracks the commands used in all PowerShell sessions.</span></span>
<span data-ttu-id="f2818-115">Журнал записывается в центральный файл на узле.</span><span class="sxs-lookup"><span data-stu-id="f2818-115">The history is written to a central file per host.</span></span> <span data-ttu-id="f2818-116">Этот файл журнала доступен для всех сеансов и содержит весь журнал за прошлый период.</span><span class="sxs-lookup"><span data-stu-id="f2818-116">That history file is available to all sessions and contains all past history.</span></span> <span data-ttu-id="f2818-117">Журнал не удаляется по завершении сеанса.</span><span class="sxs-lookup"><span data-stu-id="f2818-117">The history is not deleted when the session ends.</span></span> <span data-ttu-id="f2818-118">Кроме того, этот журнал не может управляться `*-History` командлетами.</span><span class="sxs-lookup"><span data-stu-id="f2818-118">Also, that history cannot be managed by the `*-History` cmdlets.</span></span> <span data-ttu-id="f2818-119">Дополнительные сведения см. в разделе [about_PSReadLine](../../PSReadLine/About/about_PSReadLine.md).</span><span class="sxs-lookup"><span data-stu-id="f2818-119">For more information, see [about_PSReadLine](../../PSReadLine/About/about_PSReadLine.md).</span></span>

## <a name="using-the-built-in-session-history"></a><span data-ttu-id="f2818-120">Использование встроенного журнала сеанса</span><span class="sxs-lookup"><span data-stu-id="f2818-120">Using the built-in session history</span></span>

<span data-ttu-id="f2818-121">Встроенная История отслеживает только команды, используемые в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="f2818-121">The built-in history only tracks the commands used in the current session.</span></span> <span data-ttu-id="f2818-122">Журнал недоступен для других сеансов и удаляется по завершении сеанса.</span><span class="sxs-lookup"><span data-stu-id="f2818-122">The history is not available to other sessions and is deleted when the session ends.</span></span>

### <a name="history-cmdlets"></a><span data-ttu-id="f2818-123">Командлеты журнала</span><span class="sxs-lookup"><span data-stu-id="f2818-123">History Cmdlets</span></span>

<span data-ttu-id="f2818-124">PowerShell имеет набор командлетов для управления журналом команд.</span><span class="sxs-lookup"><span data-stu-id="f2818-124">PowerShell has a set of cmdlets that manage the command history.</span></span>

| <span data-ttu-id="f2818-125">Командлет</span><span class="sxs-lookup"><span data-stu-id="f2818-125">Cmdlet</span></span>           | <span data-ttu-id="f2818-126">Псевдоним</span><span class="sxs-lookup"><span data-stu-id="f2818-126">Alias</span></span>  | <span data-ttu-id="f2818-127">Описание</span><span class="sxs-lookup"><span data-stu-id="f2818-127">Description</span></span>                                |
| ---------------- | ------ | ------------------------------------------ |
| `Get-History`    | `h`    | <span data-ttu-id="f2818-128">Возвращает журнал команд.</span><span class="sxs-lookup"><span data-stu-id="f2818-128">Gets the command history.</span></span>                  |
| `Invoke-History` | `r`    | <span data-ttu-id="f2818-129">Выполняет команду в журнале команд.</span><span class="sxs-lookup"><span data-stu-id="f2818-129">Runs a command in the command history.</span></span>     |
| `Add-History`    |        | <span data-ttu-id="f2818-130">Добавляет команду в журнал команд.</span><span class="sxs-lookup"><span data-stu-id="f2818-130">Adds a command to the command history.</span></span>     |
| `Clear-History`  | `clhy` | <span data-ttu-id="f2818-131">Удаляет команды из журнала команд.</span><span class="sxs-lookup"><span data-stu-id="f2818-131">Deletes commands from the command history.</span></span> |

### <a name="keyboard-shortcuts-for-managing-history"></a><span data-ttu-id="f2818-132">Сочетания клавиш для управления журналом</span><span class="sxs-lookup"><span data-stu-id="f2818-132">Keyboard Shortcuts for Managing History</span></span>

<span data-ttu-id="f2818-133">В консоли PowerShell для управления журналом команд можно использовать следующие сочетания клавиш.</span><span class="sxs-lookup"><span data-stu-id="f2818-133">In the PowerShell console, you can use the following shortcuts to manage the command history.</span></span>

- <span data-ttu-id="f2818-134"><kbd>Стрелка вверх</kbd> — Отображает предыдущую команду.</span><span class="sxs-lookup"><span data-stu-id="f2818-134"><kbd>UpArrow</kbd> - Displays the previous command.</span></span>
- <span data-ttu-id="f2818-135"><kbd>Стрелка вниз</kbd> — отображает следующую команду.</span><span class="sxs-lookup"><span data-stu-id="f2818-135"><kbd>DownArrow</kbd> - Displays the next command.</span></span>
- <span data-ttu-id="f2818-136"><kbd>F7</kbd> — отображает журнал команд.</span><span class="sxs-lookup"><span data-stu-id="f2818-136"><kbd>F7</kbd> - Displays the command history.</span></span>
- <span data-ttu-id="f2818-137"><kbd>ESC</kbd> — скрытие журнала.</span><span class="sxs-lookup"><span data-stu-id="f2818-137"><kbd>ESC</kbd> - To hide the history.</span></span>
- <span data-ttu-id="f2818-138"><kbd>F8</kbd> — находит команду.</span><span class="sxs-lookup"><span data-stu-id="f2818-138"><kbd>F8</kbd> - Finds a command.</span></span> <span data-ttu-id="f2818-139">Введите один или несколько символов и нажмите клавишу <kbd>F8</kbd>.</span><span class="sxs-lookup"><span data-stu-id="f2818-139">Type one or more characters then press <kbd>F8</kbd>.</span></span> <span data-ttu-id="f2818-140">Снова нажмите клавишу <kbd>F8</kbd> для следующего экземпляра.</span><span class="sxs-lookup"><span data-stu-id="f2818-140">Press <kbd>F8</kbd> again the next instance.</span></span>
- <span data-ttu-id="f2818-141"><kbd>F9</kbd> — Поиск команды по идентификатору журнала.</span><span class="sxs-lookup"><span data-stu-id="f2818-141"><kbd>F9</kbd> - Find a command by history ID.</span></span> <span data-ttu-id="f2818-142">Введите идентификатор журнала, а затем нажмите клавишу <kbd>F9</kbd>.</span><span class="sxs-lookup"><span data-stu-id="f2818-142">Type the history ID then press <kbd>F9</kbd>.</span></span> <span data-ttu-id="f2818-143">Нажмите клавишу <kbd>F7</kbd> , чтобы найти идентификатор.</span><span class="sxs-lookup"><span data-stu-id="f2818-143">Press <kbd>F7</kbd> to find the ID.</span></span>
- <span data-ttu-id="f2818-144"><kbd>#</kbd>`<string>`</kbd><kbd>Tab</kbd> — Поиск по журналу `*<string>*` и возврат последнего совпадения.</span><span class="sxs-lookup"><span data-stu-id="f2818-144"><kbd>#</kbd>`<string>`</kbd><kbd>Tab</kbd> - Search the history for `*<string>*` and returns the most recent match.</span></span> <span data-ttu-id="f2818-145">При многократном нажатии клавиши <kbd>Tab</kbd> выполняется циклический перебор соответствующих элементов в журнале.</span><span class="sxs-lookup"><span data-stu-id="f2818-145">If you press <kbd>Tab</kbd> repeatedly, it cycles through the matching items in your history.</span></span>

> [!NOTE]
> <span data-ttu-id="f2818-146">Эти сочетания клавиш реализуются ведущим приложением консоли.</span><span class="sxs-lookup"><span data-stu-id="f2818-146">These key bindings are implemented by the console host application.</span></span> <span data-ttu-id="f2818-147">Другие приложения, такие как Visual Studio Code или Windows Terminal, могут иметь различные сочетания клавиш.</span><span class="sxs-lookup"><span data-stu-id="f2818-147">Other applications, such as Visual Studio Code or Windows Terminal, can have different key bindings.</span></span> <span data-ttu-id="f2818-148">Привязки могут быть переопределены модулем PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="f2818-148">The bindings can be overridden by the PSReadLine module.</span></span> <span data-ttu-id="f2818-149">PSReadLine загружается автоматически при запуске сеанса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f2818-149">PSReadLine loads automatically when you start a PowerShell session.</span></span>
> <span data-ttu-id="f2818-150">При загрузке PSReadLine <kbd>F7</kbd> и <kbd>F9</kbd> не привязаны к какой бы то ни было функции.</span><span class="sxs-lookup"><span data-stu-id="f2818-150">With PSReadLine loaded, <kbd>F7</kbd> and <kbd>F9</kbd> are not bound to any function.</span></span> <span data-ttu-id="f2818-151">PSReadLine не предоставляет эквивалентной функциональности.</span><span class="sxs-lookup"><span data-stu-id="f2818-151">PSReadLine does not provide equivalent functionality.</span></span> <span data-ttu-id="f2818-152">Дополнительные сведения см. в разделе [about_PSReadLine](../../PSReadLine/About/about_PSReadLine.md).</span><span class="sxs-lookup"><span data-stu-id="f2818-152">For more information, see [about_PSReadLine](../../PSReadLine/About/about_PSReadLine.md).</span></span>

### <a name="maximumhistorycount"></a><span data-ttu-id="f2818-153">максимумхисторикаунт</span><span class="sxs-lookup"><span data-stu-id="f2818-153">MaximumHistoryCount</span></span>

<span data-ttu-id="f2818-154">`$MaximumHistoryCount`Переменная предпочтения определяет максимальное количество команд, сохраняемых PowerShell в журнале команд.</span><span class="sxs-lookup"><span data-stu-id="f2818-154">The `$MaximumHistoryCount` preference variable determines the maximum number of commands that PowerShell saves in the command history.</span></span> <span data-ttu-id="f2818-155">Значение по умолчанию —</span><span class="sxs-lookup"><span data-stu-id="f2818-155">The default value is</span></span>
4096.

<span data-ttu-id="f2818-156">Например, следующая команда `$MaximumHistoryCount` позволяет сократить до 100 команд:</span><span class="sxs-lookup"><span data-stu-id="f2818-156">For example, the following command lowers the `$MaximumHistoryCount` to 100 commands:</span></span>

```powershell
$MaximumHistoryCount = 100
```

<span data-ttu-id="f2818-157">Чтобы применить этот параметр, перезапустите PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f2818-157">To apply the setting, restart PowerShell.</span></span>

<span data-ttu-id="f2818-158">Чтобы сохранить новое значение переменной для всех сеансов PowerShell, добавьте инструкцию назначения в профиль PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f2818-158">To save the new variable value for all your PowerShell sessions, add the assignment statement to a PowerShell profile.</span></span> <span data-ttu-id="f2818-159">Дополнительные сведения о профилях см. в разделе [about_Profiles](about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="f2818-159">For more information about profiles, see [about_Profiles](about_Profiles.md).</span></span>

<span data-ttu-id="f2818-160">Дополнительные сведения о `$MaximumHistoryCount` переменной предпочтений см. в разделе [about_Preference_Variables](about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="f2818-160">For more information about the `$MaximumHistoryCount` preference variable, see [about_Preference_Variables](about_Preference_Variables.md).</span></span>

### <a name="order-of-commands-in-the-history"></a><span data-ttu-id="f2818-161">Порядок команд в журнале</span><span class="sxs-lookup"><span data-stu-id="f2818-161">Order of Commands in the History</span></span>

<span data-ttu-id="f2818-162">Команды добавляются в журнал, когда команда завершает выполнение, а не при введении команды.</span><span class="sxs-lookup"><span data-stu-id="f2818-162">Commands are added to the history when the command finishes executing, not when the command is entered.</span></span> <span data-ttu-id="f2818-163">Если выполнение команд занимает некоторое время или команды выполняются во вложенной командной строке, команды могут выглядеть неупорядоченными в журнале.</span><span class="sxs-lookup"><span data-stu-id="f2818-163">If commands take some time to be completed, or if the commands are executing in a nested prompt, the commands might appear to be out of order in the history.</span></span> <span data-ttu-id="f2818-164">Команды, выполняемые во вложенном запросе, выполняются только при выходе из уровня запроса.</span><span class="sxs-lookup"><span data-stu-id="f2818-164">Commands that are executing in a nested prompt are completed only when you exit the prompt level.</span></span>

## <a name="see-also"></a><span data-ttu-id="f2818-165">См. также:</span><span class="sxs-lookup"><span data-stu-id="f2818-165">See Also</span></span>

- [<span data-ttu-id="f2818-166">about_Line_Editing</span><span class="sxs-lookup"><span data-stu-id="f2818-166">about_Line_Editing</span></span>](about_Line_Editing.md)
- [<span data-ttu-id="f2818-167">about_Preference_Variables</span><span class="sxs-lookup"><span data-stu-id="f2818-167">about_Preference_Variables</span></span>](about_Preference_Variables.md)
- [<span data-ttu-id="f2818-168">about_Profiles</span><span class="sxs-lookup"><span data-stu-id="f2818-168">about_Profiles</span></span>](about_Profiles.md)
- [<span data-ttu-id="f2818-169">about_Variables</span><span class="sxs-lookup"><span data-stu-id="f2818-169">about_Variables</span></span>](about_Variables.md)
- [<span data-ttu-id="f2818-170">about_PSReadLine</span><span class="sxs-lookup"><span data-stu-id="f2818-170">about_PSReadLine</span></span>](../../PSReadLine/About/about_PSReadLine.md)
