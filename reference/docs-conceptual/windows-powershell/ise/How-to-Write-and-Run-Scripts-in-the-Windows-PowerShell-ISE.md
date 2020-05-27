---
ms.date: 01/02/2020
keywords: powershell,командлет
title: Написание и запуск сценариев в интегрированной среде сценариев Windows PowerShell
ms.openlocfilehash: 2e3122a3b436ba878d2c5f9d72d4f9e024d4d031
ms.sourcegitcommit: 2aec310ad0c0b048400cb56f6fa64c1e554c812a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/23/2020
ms.locfileid: "83808760"
---
# <a name="how-to-write-and-run-scripts-in-the-windows-powershell-ise"></a><span data-ttu-id="ccca7-103">Написание и запуск сценариев в интегрированной среде сценариев Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ccca7-103">How to Write and Run Scripts in the Windows PowerShell ISE</span></span>

<span data-ttu-id="ccca7-104">В этой статье описано как создавать, редактировать, выполнять и сохранять скрипты в области скриптов.</span><span class="sxs-lookup"><span data-stu-id="ccca7-104">This article describes how to create, edit, run, and save scripts in the Script Pane.</span></span>

## <a name="how-to-create-and-run-scripts"></a><span data-ttu-id="ccca7-105">Создание и выполнение сценариев</span><span class="sxs-lookup"><span data-stu-id="ccca7-105">How to create and run scripts</span></span>

<span data-ttu-id="ccca7-106">В области скриптов можно открывать и редактировать файлы Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ccca7-106">You can open and edit Windows PowerShell files in the Script Pane.</span></span> <span data-ttu-id="ccca7-107">Сейчас нас интересуют следующие типы файлов Windows PowerShell: файлы скриптов (`.ps1`), файлы данных скриптов (`.psd1`) и файлы модулей скриптов (`.psm1`).</span><span class="sxs-lookup"><span data-stu-id="ccca7-107">Specific file types of interest in Windows PowerShell are script files (`.ps1`), script data files (`.psd1`), and script module files (`.psm1`).</span></span> <span data-ttu-id="ccca7-108">Эти типы файлов имеют цветовую подсветку синтаксиса в редакторе области сценариев.</span><span class="sxs-lookup"><span data-stu-id="ccca7-108">These file types are syntax colored in the Script Pane editor.</span></span> <span data-ttu-id="ccca7-109">Другие стандартные файлы, которые можно открыть в области сценариев, — это файлы конфигурации (`.ps1xml`), XML-файлы и текстовые файлы.</span><span class="sxs-lookup"><span data-stu-id="ccca7-109">Other common file types you may open in the Script Pane are configuration files (`.ps1xml`), XML files, and text files.</span></span>

> [!NOTE]
> <span data-ttu-id="ccca7-110">Политика выполнения Windows PowerShell определяет, можно ли выполнять сценарии, загружать профили Windows PowerShell и файлы конфигурации.</span><span class="sxs-lookup"><span data-stu-id="ccca7-110">The Windows PowerShell execution policy determines whether you can run scripts and load Windows PowerShell profiles and configuration files.</span></span> <span data-ttu-id="ccca7-111">Политика выполнения по умолчанию, Restricted, запрещает выполнение сценариев и блокирует загрузку профилей.</span><span class="sxs-lookup"><span data-stu-id="ccca7-111">The default execution policy, Restricted, prevents all scripts from running, and prevents loading profiles.</span></span> <span data-ttu-id="ccca7-112">Чтобы изменить эту политику выполнения и разрешить загрузку и использование профилей, см. описание [Set-ExecutionPolicy](/powershell/module/microsoft.powershell.security/set-executionpolicy) и [about_Signing](/powershell/module/microsoft.powershell.core/about/about_signing).</span><span class="sxs-lookup"><span data-stu-id="ccca7-112">To change the execution policy to allow profiles to load and be used, see [Set-ExecutionPolicy](/powershell/module/microsoft.powershell.security/set-executionpolicy) and [about_Signing](/powershell/module/microsoft.powershell.core/about/about_signing).</span></span>

### <a name="to-create-a-new-script-file"></a><span data-ttu-id="ccca7-113">Создание файла сценария</span><span class="sxs-lookup"><span data-stu-id="ccca7-113">To create a new script file</span></span>

<span data-ttu-id="ccca7-114">Нажмите кнопку **Создать** на панели инструментов или откройте меню **Файл** и выберите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="ccca7-114">On the toolbar, click **New**, or on the **File** menu, click **New**.</span></span> <span data-ttu-id="ccca7-115">Созданный файл появится в новой вкладке, расположенной под текущей вкладкой PowerShell. Помните, что вкладки PowerShell отображаются, только если их несколько.</span><span class="sxs-lookup"><span data-stu-id="ccca7-115">The created file appears in a new file tab under the current PowerShell tab. Remember that the PowerShell tabs are only visible when there are more than one.</span></span> <span data-ttu-id="ccca7-116">По умолчанию создается файл сценария (`.ps1`), но его можно сохранить с новым именем и расширением.</span><span class="sxs-lookup"><span data-stu-id="ccca7-116">By default a file of type script (`.ps1`) is created, but it can be saved with a new name and extension.</span></span> <span data-ttu-id="ccca7-117">На одной вкладке PowerShell может быть создано несколько файлов сценариев.</span><span class="sxs-lookup"><span data-stu-id="ccca7-117">Multiple script files can be created in the same PowerShell tab.</span></span>

### <a name="to-open-an-existing-script"></a><span data-ttu-id="ccca7-118">Открытие существующего сценария</span><span class="sxs-lookup"><span data-stu-id="ccca7-118">To open an existing script</span></span>

<span data-ttu-id="ccca7-119">Нажмите кнопку **Открыть...** на панели инструментов или откройте меню **Файл** и выберите пункт **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="ccca7-119">On the toolbar, click **Open**, or on the **File** menu, click **Open**.</span></span> <span data-ttu-id="ccca7-120">В диалоговом окне **Открыть** выберите файл, который требуется открыть.</span><span class="sxs-lookup"><span data-stu-id="ccca7-120">In the **Open** dialog box, select the file you want to open.</span></span> <span data-ttu-id="ccca7-121">Открытый файл появится в новой вкладке.</span><span class="sxs-lookup"><span data-stu-id="ccca7-121">The opened file appears in a new tab.</span></span>

### <a name="to-close-a-script-tab"></a><span data-ttu-id="ccca7-122">Закрытие вкладки сценария</span><span class="sxs-lookup"><span data-stu-id="ccca7-122">To close a script tab</span></span>

<span data-ttu-id="ccca7-123">На вкладке файла, которую нужно закрыть, щелкните значок **закрытия** (**X**) или откройте меню **File** (Файл) и выберите **Close** (Закрыть).</span><span class="sxs-lookup"><span data-stu-id="ccca7-123">Click the **Close** icon (**X**) of the file tab you want to close or select the **File** menu and click **Close**.</span></span>

<span data-ttu-id="ccca7-124">Если файл был изменен с момента последнего сохранения, будет предложено сохранить или отменить изменения.</span><span class="sxs-lookup"><span data-stu-id="ccca7-124">If the file has been altered since it was last saved, you're prompted to save or discard it.</span></span>

### <a name="to-display-the-file-path"></a><span data-ttu-id="ccca7-125">Отображение пути к файлу</span><span class="sxs-lookup"><span data-stu-id="ccca7-125">To display the file path</span></span>

<span data-ttu-id="ccca7-126">На вкладке файла наведите курсор на его имя.</span><span class="sxs-lookup"><span data-stu-id="ccca7-126">On the file tab, point to the file name.</span></span> <span data-ttu-id="ccca7-127">Появится подсказка с полным путем к файлу сценария.</span><span class="sxs-lookup"><span data-stu-id="ccca7-127">The fully qualified path to the script file appears in a tooltip.</span></span>

### <a name="to-run-a-script"></a><span data-ttu-id="ccca7-128">Запуск сценария</span><span class="sxs-lookup"><span data-stu-id="ccca7-128">To run a script</span></span>

<span data-ttu-id="ccca7-129">Нажмите кнопку **Выполнить сценарий** на панели инструментов или откройте меню **Файл** и выберите пункт **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="ccca7-129">On the toolbar, click **Run Script**, or on the **File** menu, click **Run**.</span></span>

### <a name="to-run-a-portion-of-a-script"></a><span data-ttu-id="ccca7-130">Выполнение части сценария</span><span class="sxs-lookup"><span data-stu-id="ccca7-130">To run a portion of a script</span></span>

1. <span data-ttu-id="ccca7-131">Выберите часть сценария в области сценариев.</span><span class="sxs-lookup"><span data-stu-id="ccca7-131">In the Script Pane, select a portion of a script.</span></span>
2. <span data-ttu-id="ccca7-132">Нажмите кнопку **Выполнить выделенный фрагмент** на панели инструментов или откройте меню **Файл** и выберите пункт **Выполнить выделенный фрагмент**.</span><span class="sxs-lookup"><span data-stu-id="ccca7-132">On the **File** menu, click **Run Selection**, or on the toolbar, click **Run Selection**.</span></span>

### <a name="to-stop-a-running-script"></a><span data-ttu-id="ccca7-133">Остановка выполняемого сценария</span><span class="sxs-lookup"><span data-stu-id="ccca7-133">To stop a running script</span></span>

<span data-ttu-id="ccca7-134">Есть несколько способов остановить выполняемый скрипт.</span><span class="sxs-lookup"><span data-stu-id="ccca7-134">There are several ways to stop a running script.</span></span>

- <span data-ttu-id="ccca7-135">На панели инструментов щелкните **Остановить операцию**.</span><span class="sxs-lookup"><span data-stu-id="ccca7-135">Click **Stop Operation** on the toolbar</span></span>
- <span data-ttu-id="ccca7-136">Нажмите <kbd>CTRL</kbd>+<kbd>BREAK</kbd>.</span><span class="sxs-lookup"><span data-stu-id="ccca7-136">Press <kbd>CTRL</kbd>+<kbd>BREAK</kbd></span></span>
- <span data-ttu-id="ccca7-137">В меню **Файл** выберите **Остановить операцию**.</span><span class="sxs-lookup"><span data-stu-id="ccca7-137">Select the **File** menu and click **Stop Operation**.</span></span>

<span data-ttu-id="ccca7-138">Нажатие клавиш <kbd>CTRL</kbd>+<kbd>C</kbd> также сработает, если нет выделенного текста. В противном случае нажатие клавиш <kbd>CTRL</kbd>+<kbd>C</kbd> приведет к копированию выделенного текста.</span><span class="sxs-lookup"><span data-stu-id="ccca7-138">Pressing <kbd>CTRL</kbd>+<kbd>C</kbd> also works unless some text is currently selected, in which case <kbd>CTRL</kbd>+<kbd>C</kbd> maps to the copy function for the selected text.</span></span>

## <a name="how-to-write-and-edit-text-in-the-script-pane"></a><span data-ttu-id="ccca7-139">Написание и редактирование текста в области сценариев</span><span class="sxs-lookup"><span data-stu-id="ccca7-139">How to write and edit text in the Script Pane</span></span>

<span data-ttu-id="ccca7-140">В области скриптов текст можно копировать, вырезать, вставлять, искать и заменять.</span><span class="sxs-lookup"><span data-stu-id="ccca7-140">You can copy, cut, paste, find, and replace text in the Script Pane.</span></span> <span data-ttu-id="ccca7-141">Также можно отменить и повторить последнее выполненное действие.</span><span class="sxs-lookup"><span data-stu-id="ccca7-141">You can also undo and redo the last action you just performed.</span></span> <span data-ttu-id="ccca7-142">Для этого используются те же клавиши, как и во всех других приложениях Windows.</span><span class="sxs-lookup"><span data-stu-id="ccca7-142">The keyboard shortcuts for these actions are the same shortcuts used for all Windows applications.</span></span>

### <a name="to-enter-text-in-the-script-pane"></a><span data-ttu-id="ccca7-143">Ввод текста в области сценариев</span><span class="sxs-lookup"><span data-stu-id="ccca7-143">To enter text in the Script Pane</span></span>

1. <span data-ttu-id="ccca7-144">Установите курсор в область сценариев, щелкнув кнопкой мыши любую ее часть или выбрав пункт **Перейти в область сценариев** в меню **Вид**.</span><span class="sxs-lookup"><span data-stu-id="ccca7-144">Move the cursor to the Script Pane by clicking anywhere in the Script Pane, or by clicking **Go to Script Pane** in the **View** menu.</span></span>
2. <span data-ttu-id="ccca7-145">Создайте сценарий.</span><span class="sxs-lookup"><span data-stu-id="ccca7-145">Create a script.</span></span> <span data-ttu-id="ccca7-146">Цветовая подсветка синтаксиса и заполнение нажатием клавиши TAB обеспечивают более широкие возможности для редактирования в интегрированной среде скриптов Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ccca7-146">Syntax coloring and tab completion provide a richer editing experience in Windows PowerShell ISE.</span></span>
3. <span data-ttu-id="ccca7-147">Подробную информацию о заполнении нажатием клавиши TAB, помогающем при вводе кода, см. в статье [How to Use Tab Completion in the Script Pane and Console Pane](How-to-Use-Tab-Completion-in-the-Script-Pane-and-Console-Pane.md) (Использование заполнения нажатием клавиши TAB в областях сценариев и консоли).</span><span class="sxs-lookup"><span data-stu-id="ccca7-147">See [How to Use Tab Completion in the Script Pane and Console Pane](How-to-Use-Tab-Completion-in-the-Script-Pane-and-Console-Pane.md) for details about using the tab completion feature to help in typing.</span></span>

### <a name="to-find-text-in-the-script-pane"></a><span data-ttu-id="ccca7-148">Поиск текста в области сценариев</span><span class="sxs-lookup"><span data-stu-id="ccca7-148">To find text in the Script Pane</span></span>

1. <span data-ttu-id="ccca7-149">Чтобы найти текст в любой части скрипта, нажмите клавиши <kbd>CTRL</kbd>+<kbd>F</kbd> или выберите **Find in Script** (Найти в сценарии) в меню **Edit** (Правка).</span><span class="sxs-lookup"><span data-stu-id="ccca7-149">To find text anywhere, press <kbd>CTRL</kbd>+<kbd>F</kbd> or, on the **Edit** menu, click **Find in Script**.</span></span>
2. <span data-ttu-id="ccca7-150">Чтобы найти текст после курсора, нажмите клавишу <kbd>F3</kbd> или выберите **Найти следующее в сценарии** в меню **Правка**.</span><span class="sxs-lookup"><span data-stu-id="ccca7-150">To find text after the cursor, press <kbd>F3</kbd> or, on the **Edit** menu, click **Find Next in Script**.</span></span>
3. <span data-ttu-id="ccca7-151">Чтобы найти текст до курсора, нажмите клавиши <kbd>SHIFT</kbd>+<kbd>F3</kbd> или выберите **Find Previous in Script** (Найти предыдущее в сценарии) в меню **Edit** (Правка).</span><span class="sxs-lookup"><span data-stu-id="ccca7-151">To find text before the cursor, press <kbd>SHIFT</kbd>+<kbd>F3</kbd> or, on the **Edit** menu, click **Find Previous in Script**.</span></span>

### <a name="to-find-and-replace-text-in-the-script-pane"></a><span data-ttu-id="ccca7-152">Поиск и замена текста в области сценариев</span><span class="sxs-lookup"><span data-stu-id="ccca7-152">To find and replace text in the Script Pane</span></span>

<span data-ttu-id="ccca7-153">Нажмите клавиши <kbd>CRTL</kbd>+<kbd>H</kbd> или в меню **Edit** (Правка) выберите **Replace in Script** (Заменить в сценарии).</span><span class="sxs-lookup"><span data-stu-id="ccca7-153">Press <kbd>CTRL</kbd>+<kbd>H</kbd> or, on the **Edit** menu, click **Replace in Script**.</span></span> <span data-ttu-id="ccca7-154">Введите текст, который нужно найти, и замещающий текст, затем нажмите клавишу <kbd>ВВОД</kbd>.</span><span class="sxs-lookup"><span data-stu-id="ccca7-154">Enter the text you want to find and the replacement text, then press <kbd>ENTER</kbd>.</span></span>

### <a name="to-go-to-a-particular-line-of-text-in-the-script-pane"></a><span data-ttu-id="ccca7-155">Переход к определенной строке текста в области сценариев</span><span class="sxs-lookup"><span data-stu-id="ccca7-155">To go to a particular line of text in the Script Pane</span></span>

1. <span data-ttu-id="ccca7-156">В области сценариев нажмите клавиши <kbd>CTRL</kbd>+<kbd>G</kbd> или выберите **Go to Line** (Перейти к строке) в меню **Edit** (Правка).</span><span class="sxs-lookup"><span data-stu-id="ccca7-156">In the Script Pane, press <kbd>CTRL</kbd>+<kbd>G</kbd> or, on the **Edit** menu, click **Go to Line**.</span></span>

2. <span data-ttu-id="ccca7-157">Введите номер строки.</span><span class="sxs-lookup"><span data-stu-id="ccca7-157">Enter a line number.</span></span>

### <a name="to-copy-text-in-the-script-pane"></a><span data-ttu-id="ccca7-158">Копирование текста в области сценариев</span><span class="sxs-lookup"><span data-stu-id="ccca7-158">To copy text in the Script Pane</span></span>

1. <span data-ttu-id="ccca7-159">В области сценариев выделите текст, который требуется скопировать.</span><span class="sxs-lookup"><span data-stu-id="ccca7-159">In the Script Pane, select the text that you want to copy.</span></span>

2. <span data-ttu-id="ccca7-160">Нажмите клавиши <kbd>CTRL</kbd>+<kbd>C</kbd>, щелкните значок **Copy** (Копировать) на панели инструментов или выберите **Copy** (Копировать) в меню **Edit** (Правка).</span><span class="sxs-lookup"><span data-stu-id="ccca7-160">Press <kbd>CTRL</kbd>+<kbd>C</kbd> or, on the toolbar, click the **Copy** icon, or on the **Edit** menu, click **Copy**.</span></span>

### <a name="to-cut-text-in-the-script-pane"></a><span data-ttu-id="ccca7-161">Вырезание текста в области сценариев</span><span class="sxs-lookup"><span data-stu-id="ccca7-161">To cut text in the Script Pane</span></span>

1. <span data-ttu-id="ccca7-162">В области сценариев выделите текст, который требуется вырезать.</span><span class="sxs-lookup"><span data-stu-id="ccca7-162">In the Script Pane, select the text that you want to cut.</span></span>
2. <span data-ttu-id="ccca7-163">Нажмите клавиши <kbd>CTRL</kbd>+<kbd>X</kbd>, щелкните значок **Cut** (Вырезать) на панели инструментов или выберите **Cut** (Вырезать) в меню **Edit** (Правка).</span><span class="sxs-lookup"><span data-stu-id="ccca7-163">Press <kbd>CTRL</kbd>+<kbd>X</kbd> or, on the toolbar, click the **Cut** icon, or on the **Edit** menu, click **Cut**.</span></span>

### <a name="to-paste-text-into-the-script-pane"></a><span data-ttu-id="ccca7-164">Вставка текста в области сценариев</span><span class="sxs-lookup"><span data-stu-id="ccca7-164">To paste text into the Script Pane</span></span>

<span data-ttu-id="ccca7-165">Нажмите клавиши <kbd>CTRL</kbd>+<kbd>V</kbd>, щелкните значок **Paste** (Вставить) на панели инструментов или выберите **Paste** (Вставить) в меню **Edit** (Правка).</span><span class="sxs-lookup"><span data-stu-id="ccca7-165">Press <kbd>CTRL</kbd>+<kbd>V</kbd> or, on the toolbar, click the **Paste** icon, or on the **Edit** menu, click **Paste**.</span></span>

### <a name="to-undo-an-action-in-the-script-pane"></a><span data-ttu-id="ccca7-166">Отмена действия в области сценариев</span><span class="sxs-lookup"><span data-stu-id="ccca7-166">To undo an action in the Script Pane</span></span>

<span data-ttu-id="ccca7-167">Нажмите клавиши <kbd>CTRL</kbd>+<kbd>Z</kbd>, щелкните значок **Undo** на панели инструментов или выберите **Отменить** в меню **Правка**.</span><span class="sxs-lookup"><span data-stu-id="ccca7-167">Press <kbd>CTRL</kbd>+<kbd>Z</kbd> or, on the toolbar, click the **Undo** icon, or on the **Edit** menu, click **Undo**.</span></span>

### <a name="to-redo-an-action-in-the-script-pane"></a><span data-ttu-id="ccca7-168">Повторное выполнение действия в области сценариев</span><span class="sxs-lookup"><span data-stu-id="ccca7-168">To redo an action in the Script Pane</span></span>

<span data-ttu-id="ccca7-169">Нажмите клавиши <kbd>CTRL</kbd>+<kbd>Y</kbd>, щелкните значок **Повторить** на панели инструментов или выберите **Повторить** в меню **Правка**.</span><span class="sxs-lookup"><span data-stu-id="ccca7-169">Press <kbd>CTRL</kbd>+<kbd>Y</kbd> or, on the toolbar, click the **Redo** icon, or on the **Edit** menu, click **Redo**.</span></span>

## <a name="how-to-save-a-script"></a><span data-ttu-id="ccca7-170">Сохранение сценария</span><span class="sxs-lookup"><span data-stu-id="ccca7-170">How to save a script</span></span>

<span data-ttu-id="ccca7-171">Звездочка рядом с именем скрипта обозначает, что файл не был сохранен после изменения.</span><span class="sxs-lookup"><span data-stu-id="ccca7-171">An asterisk appears next to the script name to mark a file that hasn't been saved since it was changed.</span></span> <span data-ttu-id="ccca7-172">После сохранения звездочка исчезает.</span><span class="sxs-lookup"><span data-stu-id="ccca7-172">The asterisk disappears when the file is saved.</span></span>

### <a name="to-save-a-script"></a><span data-ttu-id="ccca7-173">Сохранение сценария</span><span class="sxs-lookup"><span data-stu-id="ccca7-173">To save a script</span></span>

<span data-ttu-id="ccca7-174">Нажмите клавиши <kbd>CTRL</kbd>+<kbd>S</kbd>, щелкните значок **Сохранить** на панели инструментов или выберите **Сохранить** в меню **Файл**.</span><span class="sxs-lookup"><span data-stu-id="ccca7-174">Press <kbd>CTRL</kbd>+<kbd>S</kbd> or, on the toolbar, click the **Save** icon, or on the **File** menu, click **Save**.</span></span>

### <a name="to-save-and-name-a-script"></a><span data-ttu-id="ccca7-175">Сохранение сценария с определенным именем</span><span class="sxs-lookup"><span data-stu-id="ccca7-175">To save and name a script</span></span>

1. <span data-ttu-id="ccca7-176">В меню **Файл** выберите команду **Сохранить как**.</span><span class="sxs-lookup"><span data-stu-id="ccca7-176">On the **File** menu, click **Save As**.</span></span> <span data-ttu-id="ccca7-177">Появится диалоговое окно **Сохранить как**.</span><span class="sxs-lookup"><span data-stu-id="ccca7-177">The **Save As** dialog box will appear.</span></span>
2. <span data-ttu-id="ccca7-178">В поле **Имя файла** введите имя файла.</span><span class="sxs-lookup"><span data-stu-id="ccca7-178">In the **File name** box, enter a name for the file.</span></span>
3. <span data-ttu-id="ccca7-179">В поле **Тип файла** выберите тип файла.</span><span class="sxs-lookup"><span data-stu-id="ccca7-179">In the **Save as type** box, select a file type.</span></span> <span data-ttu-id="ccca7-180">Например, в поле **Тип сохраняемого файла** выберите "Скрипты PowerShell (`*.ps1`)".</span><span class="sxs-lookup"><span data-stu-id="ccca7-180">For example, in the **Save as type** box, select 'PowerShell Scripts (`*.ps1`)'.</span></span>
4. <span data-ttu-id="ccca7-181">Выберите команду **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="ccca7-181">Click **Save**.</span></span>

### <a name="to-save-a-script-in-ascii-encoding"></a><span data-ttu-id="ccca7-182">Сохранение сценария в кодировке ASCII</span><span class="sxs-lookup"><span data-stu-id="ccca7-182">To save a script in ASCII encoding</span></span>

<span data-ttu-id="ccca7-183">По умолчанию интегрированная среда сценариев Windows PowerShell сохраняет новые файлы сценариев (`.ps1`), файлы данных сценариев (`.psd1`) и файлы модулей сценариев (`.psm1`) в кодировке Юникод (BigEndianUnicode).</span><span class="sxs-lookup"><span data-stu-id="ccca7-183">By default, Windows PowerShell ISE saves new script files (`.ps1`), script data files (`.psd1`), and script module files (`.psm1`) as Unicode (BigEndianUnicode) by default.</span></span> <span data-ttu-id="ccca7-184">Чтобы сохранить сценарий в другой кодировке, например ASCII (ANSI), используйте методы **Save** или **SaveAs** объекта [$psISE.CurrentFile](object-model/the-ise-object-model-hierarchy.md).</span><span class="sxs-lookup"><span data-stu-id="ccca7-184">To save a script in another encoding, such as ASCII (ANSI), use the **Save** or **SaveAs** methods on the [$psISE.CurrentFile](object-model/the-ise-object-model-hierarchy.md) object.</span></span>

<span data-ttu-id="ccca7-185">Следующая команда сохраняет новый сценарий в кодировке ASCII и с именем MyScript.ps1:</span><span class="sxs-lookup"><span data-stu-id="ccca7-185">The following command saves a new script as MyScript.ps1 with ASCII encoding.</span></span>

```powershell
$psISE.CurrentFile.SaveAs("MyScript.ps1", [System.Text.Encoding]::ASCII)
```

<span data-ttu-id="ccca7-186">Следующая команда заменяет текущий файл сценария на файл с таким же именем, но в кодировке ASCII:</span><span class="sxs-lookup"><span data-stu-id="ccca7-186">The following command replaces the current script file with a file with the same name, but with ASCII encoding.</span></span>

```powershell
$psISE.CurrentFile.Save([System.Text.Encoding]::ASCII)
```

<span data-ttu-id="ccca7-187">Следующая команда возвращает кодировку текущего файла:</span><span class="sxs-lookup"><span data-stu-id="ccca7-187">The following command gets the encoding of the current file.</span></span>

```powershell
$psISE.CurrentFile.encoding
```

<span data-ttu-id="ccca7-188">Интегрированная среда скриптов Windows PowerShell поддерживает следующие параметры кодировки: ASCII, BigEndianUnicode, Unicode, UTF32, UTF7, UTF8 и Default.</span><span class="sxs-lookup"><span data-stu-id="ccca7-188">Windows PowerShell ISE supports the following encoding options: ASCII, BigEndianUnicode, Unicode, UTF32, UTF7, UTF8, and Default.</span></span> <span data-ttu-id="ccca7-189">Значение параметра Default зависит от системы.</span><span class="sxs-lookup"><span data-stu-id="ccca7-189">The value of the Default option varies with the system.</span></span>

<span data-ttu-id="ccca7-190">Интегрированная среда скриптов Windows PowerShell не изменяет кодировку файлов скриптов при использовании команд "Сохранить" или "Сохранить как".</span><span class="sxs-lookup"><span data-stu-id="ccca7-190">Windows PowerShell ISE doesn't change the encoding of script files when you use the Save or Save As commands.</span></span>

## <a name="see-also"></a><span data-ttu-id="ccca7-191">См. также:</span><span class="sxs-lookup"><span data-stu-id="ccca7-191">See Also</span></span>

- [<span data-ttu-id="ccca7-192">Обзор интегрированной среды скриптов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ccca7-192">Exploring the Windows PowerShell ISE</span></span>](exploring-the-windows-powershell-ise.md)
