---
ms.date: 09/06/2019
keywords: powershell,командлет
title: Новые возможности интегрированной среды сценариев PowerShell 5.0
ms.openlocfilehash: 8f15e99c5a6ae33aeae9bd33eb0cf58fb27e3b90
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "74416648"
---
# <a name="whats-new-in-the-windows-powershell-50-ise"></a><span data-ttu-id="71445-103">Новые возможности интегрированной среды сценариев Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="71445-103">What's New in the Windows PowerShell 5.0 ISE</span></span>

<span data-ttu-id="71445-104">В этой статье описаны новые и обновленные функции, представленные в версии 5.0 интегрированной среды сценариев (ISE) Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="71445-104">This topic explains the new and updated features that have been introduced in version 5.0 of the Windows PowerShell Integrated Scripting Environment (ISE).</span></span>

> [!NOTE]
> <span data-ttu-id="71445-105">Функции для ISE PowerShell больше не разрабатываются.</span><span class="sxs-lookup"><span data-stu-id="71445-105">The PowerShell ISE is no longer in active feature development.</span></span> <span data-ttu-id="71445-106">Как компонент доставки Windows эта среда по-прежнему официально поддерживается для внесения наиболее важных исправлений, связанных с безопасностью и обслуживанием.</span><span class="sxs-lookup"><span data-stu-id="71445-106">As a shipping component of Windows, it continues to be officially supported for security and high-priority servicing fixes.</span></span>
> <span data-ttu-id="71445-107">Пока что мы не планируем удалять ISE из Windows.</span><span class="sxs-lookup"><span data-stu-id="71445-107">We currently have no plans to remove the ISE from Windows.</span></span>
>
> <span data-ttu-id="71445-108">ISE не поддерживается в PowerShell версии 6 и более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="71445-108">There is no support for the ISE in PowerShell v6 and beyond.</span></span> <span data-ttu-id="71445-109">Пользователям, которые ищут замену ISE, следует использовать [Visual Studio Code](https://code.visualstudio.com/) с расширением [PowerShell](https://marketplace.visualstudio.com/items?itemName=ms-vscode.PowerShell).</span><span class="sxs-lookup"><span data-stu-id="71445-109">Users looking for replacement for the ISE should use [Visual Studio Code](https://code.visualstudio.com/) with the [PowerShell Extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode.PowerShell).</span></span>

## <a name="feature-description"></a><span data-ttu-id="71445-110">Описание компонента</span><span class="sxs-lookup"><span data-stu-id="71445-110">Feature description</span></span>

<span data-ttu-id="71445-111">Интегрированная среда сценариев Windows PowerShell — это ведущее приложение, позволяющее писать, выполнять и тестировать сценарии и модули в удобной среде с графическим интерфейсом.</span><span class="sxs-lookup"><span data-stu-id="71445-111">The Windows PowerShell ISE is a host application that enables you to write, run, and test scripts and modules in a graphical and intuitive environment.</span></span> <span data-ttu-id="71445-112">Такие важные возможности, как цветовая разметка синтаксиса, автозаполнение по нажатию клавиши TAB, визуальная отладка, совместимость с Юникодом и контекстная справка делают работу со сценариями более удобной.</span><span class="sxs-lookup"><span data-stu-id="71445-112">Key features such as syntax-coloring, tab completion, visual debugging, Unicode compliance, and context-sensitive Help provide a rich scripting experience.</span></span>

<span data-ttu-id="71445-113">Дополнительные сведения см. в обзорной статье об [интегрированной среде сценариев Windows PowerShell](../components/ise/Introducing-the-Windows-PowerShell-ISE.md).</span><span class="sxs-lookup"><span data-stu-id="71445-113">For more information, see [Introducing the Windows PowerShell ISE](../components/ise/Introducing-the-Windows-PowerShell-ISE.md).</span></span>

<span data-ttu-id="71445-114">Следующая таблица содержит новые и измененные функции для этого выпуска интегрированной среды сценариев Windows PowerShell в Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="71445-114">The following table lists the new and changed features for this release of Windows PowerShell ISE in Windows PowerShell.</span></span>

## <a name="intellisense"></a><span data-ttu-id="71445-115">технология IntelliSense</span><span class="sxs-lookup"><span data-stu-id="71445-115">IntelliSense</span></span>

> <span data-ttu-id="71445-116">Добавлен в интегрированной среде сценариев 3.0</span><span class="sxs-lookup"><span data-stu-id="71445-116">Added in ISE 3.0</span></span>

<span data-ttu-id="71445-117">IntelliSense — это средство для автоматического дополнения, являющееся частью интегрированной среды сценариев Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="71445-117">IntelliSense is an automatic-completion assistance feature that is part of Windows PowerShell ISE.</span></span>
<span data-ttu-id="71445-118">По мере набора IntelliSense отображает активные меню с подходящими командлетами, параметрами, значениями параметров, файлами и папками.</span><span class="sxs-lookup"><span data-stu-id="71445-118">IntelliSense displays clickable menus of potentially matching cmdlets, parameters, parameter values, files, or folders as you type.</span></span>

<span data-ttu-id="71445-119">**Какой эффект дает это изменение?**</span><span class="sxs-lookup"><span data-stu-id="71445-119">**What value does this change add?**</span></span>

<span data-ttu-id="71445-120">С появлением IntelliSense в интегрированной среде сценариев Windows PowerShell стало удобнее находить командлеты и проверять синтаксис при создании скриптов.</span><span class="sxs-lookup"><span data-stu-id="71445-120">With the addition of IntelliSense, it's easier to discover cmdlets and syntax when you use Windows PowerShell ISE to create scripts.</span></span> <span data-ttu-id="71445-121">Интегрированная среда сценариев Windows PowerShell позволяет также изучать Windows PowerShell при создании новых сценариев.</span><span class="sxs-lookup"><span data-stu-id="71445-121">You can also use Windows PowerShell ISE to learn Windows PowerShell while you create new scripts.</span></span>

<span data-ttu-id="71445-122">**Что работает иначе?**</span><span class="sxs-lookup"><span data-stu-id="71445-122">**What works differently?**</span></span>

<span data-ttu-id="71445-123">При вводе командлетов в интегрированной среде сценариев Windows PowerShell отображается прокручиваемое и активное меню, позволяющее просматривать и выбирать соответствующие команды.</span><span class="sxs-lookup"><span data-stu-id="71445-123">When you type cmdlets in the Windows PowerShell ISE, a scrollable and clickable menu displays, allowing you to browse and select the appropriate commands.</span></span>

## <a name="snippets"></a><span data-ttu-id="71445-124">Фрагменты кода</span><span class="sxs-lookup"><span data-stu-id="71445-124">Snippets</span></span>

> <span data-ttu-id="71445-125">Добавлен в интегрированной среде сценариев 3.0</span><span class="sxs-lookup"><span data-stu-id="71445-125">Added in ISE 3.0</span></span>

<span data-ttu-id="71445-126">*Фрагменты* — это короткие участки кода Windows PowerShell, которые можно легко вставить в сценарии, создаваемые в интегрированной среде сценариев Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="71445-126">*Snippets* are short sections of Windows PowerShell code that you can insert into the scripts you create in Windows PowerShell ISE.</span></span> <span data-ttu-id="71445-127">Интегрированная среда сценариев Windows PowerShell включает стандартный набор фрагментов.</span><span class="sxs-lookup"><span data-stu-id="71445-127">Windows PowerShell ISE comes with a default set of snippets.</span></span> <span data-ttu-id="71445-128">При работе в интегрированной среде сценариев Windows PowerShell можно добавлять фрагменты кода с помощью командлета `New-Snippet`.</span><span class="sxs-lookup"><span data-stu-id="71445-128">You can add snippets by using the `New-Snippet` cmdlet while working in Windows PowerShell ISE.</span></span>

<span data-ttu-id="71445-129">**Какой эффект дает это изменение?**</span><span class="sxs-lookup"><span data-stu-id="71445-129">**What value does this change add?**</span></span>

<span data-ttu-id="71445-130">С помощью фрагментов можно быстро составлять и создавать сценарии для автоматизации среды.</span><span class="sxs-lookup"><span data-stu-id="71445-130">By using snippets, you can quickly assemble and create scripts to automate your environment.</span></span>

<span data-ttu-id="71445-131">**Что работает иначе?**</span><span class="sxs-lookup"><span data-stu-id="71445-131">**What works differently?**</span></span>

<span data-ttu-id="71445-132">Чтобы использовать фрагменты кода в Windows PowerShell версии 3.0 и выше, щелкните **Запустить фрагменты** в меню **Правка** или нажмите клавиши <kbd>CTRL</kbd>+<kbd>J</kbd>.</span><span class="sxs-lookup"><span data-stu-id="71445-132">To use snippets in Windows PowerShell 3.0 or later, on the **Edit** menu, click **Start Snippets**, or press <kbd>Ctrl</kbd>+<kbd>J</kbd>.</span></span>

## <a name="add-on-tools"></a><span data-ttu-id="71445-133">Дополнительные средства</span><span class="sxs-lookup"><span data-stu-id="71445-133">Add-on tools</span></span>

> <span data-ttu-id="71445-134">Добавлено в PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="71445-134">Added in PowerShell 3.0</span></span>

<span data-ttu-id="71445-135">Интегрированная среда сценариев Windows PowerShell теперь поддерживает надстройки с использованием объектной модели.</span><span class="sxs-lookup"><span data-stu-id="71445-135">Windows PowerShell ISE now supports add-on tools using the object model.</span></span> <span data-ttu-id="71445-136">Эти надстройки являются элементами управления Windows Presentation Foundation (WPF), отображаемыми в консоли виде вертикальной или горизонтальной панели.</span><span class="sxs-lookup"><span data-stu-id="71445-136">These add-ons are Windows Presentation Foundation (WPF) controls that are displayed as a vertical or horizontal pane in the console.</span></span> <span data-ttu-id="71445-137">Если область содержит несколько дополнительных средств, они отображаются на вкладках.</span><span class="sxs-lookup"><span data-stu-id="71445-137">Multiple add-on tools in a pane are displayed as a tabbed control.</span></span> <span data-ttu-id="71445-138">Можно также добавлять и удалять дополнительные средства сторонних производителей.</span><span class="sxs-lookup"><span data-stu-id="71445-138">You can also add or remove add-on tools that are produced by non-Microsoft parties.</span></span> <span data-ttu-id="71445-139">Дополнительные сведения см. в статье о [предназначении объектной модели интегрированной среды сценариев Windows PowerShell](../components/ise/object-model/Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md).</span><span class="sxs-lookup"><span data-stu-id="71445-139">For more information, see [The Purpose of the Windows PowerShell ISE Scripting Object Model](../components/ise/object-model/Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md).</span></span>

<span data-ttu-id="71445-140">**Какой эффект дает это изменение?**</span><span class="sxs-lookup"><span data-stu-id="71445-140">**What value does this change add?**</span></span>

<span data-ttu-id="71445-141">Дополнительные компоненты позволяют расширить и настроить интегрированную среду сценариев Windows PowerShell с помощью средств для оптимизации работы со скриптами.</span><span class="sxs-lookup"><span data-stu-id="71445-141">Add-ons allow you to extend and customize Windows PowerShell ISE with tools that add functionality and enhance your scripting experience.</span></span>

<span data-ttu-id="71445-142">**Что работает иначе?**</span><span class="sxs-lookup"><span data-stu-id="71445-142">**What works differently?**</span></span>

<span data-ttu-id="71445-143">Интегрированная среда сценариев Windows PowerShell 3.0 и более поздних версий содержит дополнительный компонент **Команды**.</span><span class="sxs-lookup"><span data-stu-id="71445-143">Windows PowerShell ISE 3.0 and later come with the **Commands** add-on.</span></span> <span data-ttu-id="71445-144">Компонент **Команды** позволяет параллельно просматривать командлеты и справку для них в областях **Сценарий** и **Консоль**.</span><span class="sxs-lookup"><span data-stu-id="71445-144">The **Commands** add-on allows you to browse cmdlets, and access help about the cmdlets side-by-side with the **Script** and **Console** Panes.</span></span>

<span data-ttu-id="71445-145">Другие дополнительные средства можно найти с помощью команды **Перейти на сайт дополнительных компонентов** в меню **Дополнительные компоненты**.</span><span class="sxs-lookup"><span data-stu-id="71445-145">Additional add-ons can be found by using the **Open Add-on Tools Website** command on the **Add-ons** menu.</span></span>

## <a name="restart-manager-and-auto-save"></a><span data-ttu-id="71445-146">Перезапуск диспетчера и автосохранение</span><span class="sxs-lookup"><span data-stu-id="71445-146">Restart manager and auto-save</span></span>

> <span data-ttu-id="71445-147">Добавлено в PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="71445-147">Added in PowerShell 3.0</span></span>

<span data-ttu-id="71445-148">Интегрированная среда сценариев Windows PowerShell теперь автоматически сохраняет открытые сценарии в отдельном расположении каждые две минуты.</span><span class="sxs-lookup"><span data-stu-id="71445-148">Windows PowerShell ISE now automatically saves your open scripts every two minutes, in a separate location.</span></span> <span data-ttu-id="71445-149">При перезагрузке или перезапуске интегрированной среды сценариев Windows PowerShell после аварийного завершения работы скрипты, которые были открыты в предыдущем сеансе, восстанавливаются, даже если они не были сохранены.</span><span class="sxs-lookup"><span data-stu-id="71445-149">When Windows PowerShell ISE restarts after an unexpected crash or reboot, it recovers scripts that were open in the last session, even if the scripts weren't saved.</span></span>

<span data-ttu-id="71445-150">Чтобы изменить интервал автоматического сохранения, в консоли выполните команду `$psise.Options.AutoSaveMinuteInterval`.</span><span class="sxs-lookup"><span data-stu-id="71445-150">To change the automatic saving interval, run the following command in the Console pane: `$psise.Options.AutoSaveMinuteInterval`.</span></span>

<span data-ttu-id="71445-151">**Какой эффект дает это изменение?**</span><span class="sxs-lookup"><span data-stu-id="71445-151">**What value does this change add?**</span></span>

<span data-ttu-id="71445-152">Теперь в интегрированной среде сценариев Windows PowerShell можно работать, зная, что открытые скрипты сохраняются автоматически.</span><span class="sxs-lookup"><span data-stu-id="71445-152">You can now work within Windows PowerShell ISE knowing that your open scripts are automatically saved.</span></span>

<span data-ttu-id="71445-153">**Что работает иначе?**</span><span class="sxs-lookup"><span data-stu-id="71445-153">**What works differently?**</span></span>

<span data-ttu-id="71445-154">В интегрированной среде сценариев Windows PowerShell 2.0 скрипты не сохраняются автоматически.</span><span class="sxs-lookup"><span data-stu-id="71445-154">Windows PowerShell ISE 2.0 doesn't save the scripts automatically.</span></span>

## <a name="most-recently-used-list"></a><span data-ttu-id="71445-155">Список недавно использовавшихся элементов</span><span class="sxs-lookup"><span data-stu-id="71445-155">Most-recently used list</span></span>

> <span data-ttu-id="71445-156">Добавлено в PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="71445-156">Added in PowerShell 3.0</span></span>

<span data-ttu-id="71445-157">Интегрированная среда сценариев Windows PowerShell теперь содержит список недавно использовавшихся файлов.</span><span class="sxs-lookup"><span data-stu-id="71445-157">Windows PowerShell ISE now has a most-recently used list for files.</span></span> <span data-ttu-id="71445-158">При открытии файла в интегрированной среде сценариев Windows PowerShell он добавляется в список недавно использованных элементов в меню **Файл**.</span><span class="sxs-lookup"><span data-stu-id="71445-158">When you open a file in Windows PowerShell ISE, the file is added to the most-recently used list on the **File** menu.</span></span>

<span data-ttu-id="71445-159">Чтобы изменить число файлов в списке недавно использованных элементов, в консоли выполните команду `$psise.Options.MruCount`.</span><span class="sxs-lookup"><span data-stu-id="71445-159">To change the default number of files in the most-recently used list, run the following command in the Console Pane: `$psise.Options.MruCount`.</span></span>

<span data-ttu-id="71445-160">**Какой эффект дает это изменение?**</span><span class="sxs-lookup"><span data-stu-id="71445-160">**What value does this change add?**</span></span>

<span data-ttu-id="71445-161">Список недавно использованных элементов упрощает доступ к файлам.</span><span class="sxs-lookup"><span data-stu-id="71445-161">You can now use the most-recently used list to easily access your frequently used files.</span></span>

<span data-ttu-id="71445-162">**Что работает иначе?**</span><span class="sxs-lookup"><span data-stu-id="71445-162">**What works differently?**</span></span>

<span data-ttu-id="71445-163">В интегрированной среде сценариев Windows PowerShell 2.0 нет списка недавно использованных элементов.</span><span class="sxs-lookup"><span data-stu-id="71445-163">Windows PowerShell ISE 2.0 doesn't have a most-recently used list.</span></span>

## <a name="console-pane"></a><span data-ttu-id="71445-164">Область консоли</span><span class="sxs-lookup"><span data-stu-id="71445-164">Console Pane</span></span>

> <span data-ttu-id="71445-165">Добавлено в PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="71445-165">Added in PowerShell 3.0</span></span>

<span data-ttu-id="71445-166">Области команд и вывода, которые были разделены в первом выпуске интегрированной среды сценариев Windows PowerShell, объединены теперь в одну область консоли.</span><span class="sxs-lookup"><span data-stu-id="71445-166">The separate Command and Output Panes that were available in the first release of Windows PowerShell ISE have been combined into a single Console Pane.</span></span> <span data-ttu-id="71445-167">Область консоли аналогична по функциональности и внешнему виду стандартной консоли Windows PowerShell, но отличается рядом усовершенствований, которые перечислены ниже.</span><span class="sxs-lookup"><span data-stu-id="71445-167">The Console Pane is similar in function and appearance to a typical Windows PowerShell console, but it includes the following enhancements:</span></span>

- <span data-ttu-id="71445-168">Цветовая разметка синтаксиса вводимого текста (но не выводимого текста), включая синтаксис XML</span><span class="sxs-lookup"><span data-stu-id="71445-168">Syntax coloring for input text (not output text), including XML syntax</span></span>
- <span data-ttu-id="71445-169">технология IntelliSense</span><span class="sxs-lookup"><span data-stu-id="71445-169">IntelliSense</span></span>
- <span data-ttu-id="71445-170">Соответствие скобок</span><span class="sxs-lookup"><span data-stu-id="71445-170">Brace matching</span></span>
- <span data-ttu-id="71445-171">Индикация ошибок</span><span class="sxs-lookup"><span data-stu-id="71445-171">Error indication</span></span>
- <span data-ttu-id="71445-172">Полная поддержка Юникода</span><span class="sxs-lookup"><span data-stu-id="71445-172">Full Unicode support</span></span>
- <span data-ttu-id="71445-173">Контекстная справка по нажатию клавиши <kbd>F1</kbd></span><span class="sxs-lookup"><span data-stu-id="71445-173"><kbd>F1</kbd> context-sensitive help</span></span>
- <span data-ttu-id="71445-174">Контекстно-зависимая справка командлета Show-Command, вызываемая с помощью клавиш <kbd>CTRL</kbd>+<kbd>F1</kbd>.</span><span class="sxs-lookup"><span data-stu-id="71445-174"><kbd>Ctrl</kbd>+<kbd>F1</kbd> context-sensitive Show-Command</span></span>
- <span data-ttu-id="71445-175">Поддержка наборов сложных знаков и написания справа налево</span><span class="sxs-lookup"><span data-stu-id="71445-175">Complex script and right-to-left support</span></span>
- <span data-ttu-id="71445-176">Поддержка шрифтов</span><span class="sxs-lookup"><span data-stu-id="71445-176">Font support</span></span>
- <span data-ttu-id="71445-177">Zoom</span><span class="sxs-lookup"><span data-stu-id="71445-177">Zoom</span></span>
- <span data-ttu-id="71445-178">Режимы выделения строки и блока</span><span class="sxs-lookup"><span data-stu-id="71445-178">Line-select and block-select modes</span></span>
- <span data-ttu-id="71445-179">Сохранение введенного содержимого в командной строке с помощью клавиши <kbd>СТРЕЛКА ВВЕРХ</kbd> для просмотра истории в консоли.</span><span class="sxs-lookup"><span data-stu-id="71445-179">Preservation of typed content at the command line when you press the <kbd>UpArrow</kbd> to view history in the console</span></span>

<span data-ttu-id="71445-180">**Какой эффект дает это изменение?**</span><span class="sxs-lookup"><span data-stu-id="71445-180">**What value does this change add?**</span></span>

<span data-ttu-id="71445-181">Эти изменения в области консоли делают работу со сценариями более согласованной с интерфейсом консоли.</span><span class="sxs-lookup"><span data-stu-id="71445-181">The addition of these Console Pane changes provides a scripting experience that is more consistent with the console interface.</span></span>

<span data-ttu-id="71445-182">**Что работает иначе?**</span><span class="sxs-lookup"><span data-stu-id="71445-182">**What works differently?**</span></span>

<span data-ttu-id="71445-183">Интегрированная среда сценариев Windows PowerShell 2.0 имеет отдельные области команд и вывода.</span><span class="sxs-lookup"><span data-stu-id="71445-183">Windows PowerShell ISE 2.0 has separate Command and Output Panes.</span></span>

## <a name="command-line-switches"></a><span data-ttu-id="71445-184">Параметры командной строки</span><span class="sxs-lookup"><span data-stu-id="71445-184">Command-line switches</span></span>

> <span data-ttu-id="71445-185">Добавлено в PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="71445-185">Added in PowerShell 3.0</span></span>

<span data-ttu-id="71445-186">При запуске интегрированной среды сценариев Windows PowerShell из командной строки (для этого введите **powershell_ise.exe** в командной строке) можно указывать следующие новые параметры.</span><span class="sxs-lookup"><span data-stu-id="71445-186">If you start Windows PowerShell ISE from the command line (by typing **powershell_ise.exe**), you can add the following new command-line switches.</span></span>

- <span data-ttu-id="71445-187">`-NoProfile`: запускает интегрированную среду сценариев Windows PowerShell без выполнения `$profile`.</span><span class="sxs-lookup"><span data-stu-id="71445-187">`-NoProfile`: Starts Windows PowerShell ISE without running `$profile`</span></span>
- <span data-ttu-id="71445-188">`-Help`: отображает окно справки.</span><span class="sxs-lookup"><span data-stu-id="71445-188">`-Help`: Displays a Help window</span></span>
- <span data-ttu-id="71445-189">`-mta`: интегрированная среда сценариев Windows PowerShell запускается в режиме многопотокового подразделения.</span><span class="sxs-lookup"><span data-stu-id="71445-189">`-mta`: Starts Windows PowerShell ISE in multithreaded apartment mode.</span></span> <span data-ttu-id="71445-190">По умолчанию для интегрированной среды сценариев Windows PowerShell используется режим однопоточного подразделения (он задается с помощью параметра `-sta`).</span><span class="sxs-lookup"><span data-stu-id="71445-190">The default operation mode for Windows PowerShell ISE is single-threaded apartment mode, or `-sta`.</span></span>

<span data-ttu-id="71445-191">**Какой эффект дает это изменение?**</span><span class="sxs-lookup"><span data-stu-id="71445-191">**What value does this change add?**</span></span>

<span data-ttu-id="71445-192">Добавление этих параметров командной строки позволяет управлять средой, в которой выполняется интегрированная среда сценариев Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="71445-192">The addition of these command-line switches allows you to control the environment in which the Windows PowerShell ISE runs.</span></span>

<span data-ttu-id="71445-193">**Что работает иначе?**</span><span class="sxs-lookup"><span data-stu-id="71445-193">**What works differently?**</span></span>

<span data-ttu-id="71445-194">Интегрированная среда сценариев Windows PowerShell 2.0 не распознает эти параметры командной строки.</span><span class="sxs-lookup"><span data-stu-id="71445-194">Windows PowerShell ISE 2.0 doesn't recognize these command-line switches.</span></span>

## <a name="new-editor-features"></a><span data-ttu-id="71445-195">Новые возможности редактора</span><span class="sxs-lookup"><span data-stu-id="71445-195">New editor features</span></span>

> <span data-ttu-id="71445-196">Добавлено в PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="71445-196">Added in PowerShell 3.0</span></span>

<span data-ttu-id="71445-197">Другие возможности редактирования в интегрированной среде сценариев Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="71445-197">Other Windows PowerShell ISE editing features include:</span></span>

- <span data-ttu-id="71445-198">**Цветовая разметка синтаксиса XML**. Теперь в интегрированной среде сценариев Windows PowerShell синтаксис XML выделяется цветами, как в Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="71445-198">**XML syntax coloring** - Windows PowerShell ISE now colors XML syntax in the same way as it colors Windows PowerShell syntax.</span></span>
- <span data-ttu-id="71445-199">**Парные фигурные скобки**. В интегрированной среде сценариев Windows PowerShell реализованы контроль соответствия и подсветка скобок (например, команда **Перейти к совпадению** или клавиши <kbd>CTRL</kbd>+<kbd>]</kbd> позволяют найти закрывающую скобку, если выделена открывающая скобка).</span><span class="sxs-lookup"><span data-stu-id="71445-199">**Brace matching** - Windows PowerShell ISE includes brace matching and highlighting, and can be used in the following ways: (for example, using the **Go to Match** command or <kbd>Ctrl</kbd>+<kbd>]</kbd> locates the closing brace, if you have an opening brace selected).</span></span>
- <span data-ttu-id="71445-200">**Режим структуры**. Область сценариев теперь поддерживает режим структуры, который позволяет сворачивать и разворачивать фрагменты кода, щелкая знаки "минус" или "плюс" на левом поле.</span><span class="sxs-lookup"><span data-stu-id="71445-200">**Outline view** The Script Pane supports outlining, which allows collapsing or expanding sections of code by clicking plus or minus signs in the left margin.</span></span> <span data-ttu-id="71445-201">Обозначить начало и конец сворачиваемого фрагмента кода можно с помощью скобок или тегов `#region` и `#endregion`.</span><span class="sxs-lookup"><span data-stu-id="71445-201">You can use braces or the `#region` and `#endregion` tags to mark the beginning or end of a collapsible section.</span></span> <span data-ttu-id="71445-202">Чтобы развернуть или свернуть все области, нажмите клавиши <kbd>CTRL</kbd>+<kbd>M</kbd>.</span><span class="sxs-lookup"><span data-stu-id="71445-202">To expand or collapse all regions, press <kbd>Ctrl</kbd>+<kbd>M</kbd>.</span></span>
- <span data-ttu-id="71445-203">**Перетаскивание текста при правке**. Теперь интегрированная среда сценариев Windows PowerShell поддерживает перетаскивание текста при правке.</span><span class="sxs-lookup"><span data-stu-id="71445-203">**Drag and drop text editing** - Windows PowerShell ISE now supports drag and drop text editing.</span></span> <span data-ttu-id="71445-204">Можно выбрать любой блок текста и перетащить его в другое место в редакторе или консоли.</span><span class="sxs-lookup"><span data-stu-id="71445-204">You can select any block of text and drag that text to another location in the editor or the console to move the text.</span></span> <span data-ttu-id="71445-205">Если при перетаскивании удерживать нажатой клавишу <kbd>CTRL</kbd>, текст копируется в новое расположение.</span><span class="sxs-lookup"><span data-stu-id="71445-205">If you hold down the <kbd>Ctrl</kbd> key while you drag the selected text, when you release the mouse button the text is copied to the new location.</span></span> <span data-ttu-id="71445-206">В этой версии интегрированной среды сценариев Windows PowerShell при перетаскивании файла в интегрированную среду сценариев Windows PowerShell этот файл открывается.</span><span class="sxs-lookup"><span data-stu-id="71445-206">In this version of Windows PowerShell ISE, when you drag and drop files onto Windows PowerShell ISE, Windows PowerShell ISE opens the file.</span></span>
- <span data-ttu-id="71445-207">**Отображение ошибок анализа**. Ошибки анализа подчеркиваются красным цветом.</span><span class="sxs-lookup"><span data-stu-id="71445-207">**Parse error display** - Parse errors are indicated with red underlines.</span></span> <span data-ttu-id="71445-208">При наведении указателя мыши на подчеркнутую ошибку отображается подсказка, поясняющая суть обнаруженной проблемы.</span><span class="sxs-lookup"><span data-stu-id="71445-208">When you hover over an indicated error, tooltip text displays the problem that was found in the code.</span></span>
- <span data-ttu-id="71445-209">**Масштаб**. Устанавливать масштаб отображения содержимого консоли в процентах можно с помощью соответствующего ползунка (в правом нижнем углу окна интегрированной среды сценариев Windows PowerShell) или команды `$psise.options.Zoom` в области консоли.</span><span class="sxs-lookup"><span data-stu-id="71445-209">**Zoom** - The zoom percentage of the console's content can be set by using the zoom slider (in the lower right corner of Windows PowerShell ISE window), or by entering the command `$psise.options.Zoom` in the Console Pane.</span></span>
- <span data-ttu-id="71445-210">**Копирование и вставка форматированного текста**. Теперь при копировании в буфер обмена интегрированной среды сценариев Windows PowerShell сохраняется исходное начертание, размер и цвет шрифта выделенного текста.</span><span class="sxs-lookup"><span data-stu-id="71445-210">**Rich text copy and paste** - Copying to the clipboard in Windows PowerShell ISE preserves the font, size, and color information of the original selection.</span></span>
- <span data-ttu-id="71445-211">**Выделение блока**. Можно выделить блок текста, удерживая клавишу <kbd>ALT</kbd> при выделении текста мышью в области сценариев или нажимая клавиши <kbd>ALT</kbd>+<kbd>SHIFT</kbd>+<kbd>СТРЕЛКА</kbd>.</span><span class="sxs-lookup"><span data-stu-id="71445-211">**Block selection** - You can select a block of text by holding down the <kbd>ALT</kbd> key while selecting text in the Script Pane with your mouse, or by pressing <kbd>Alt</kbd>+<kbd>Shift</kbd>+<kbd>Arrow</kbd>.</span></span>

<span data-ttu-id="71445-212">**Какой эффект дает это изменение?**</span><span class="sxs-lookup"><span data-stu-id="71445-212">**What value does this change add?**</span></span>

<span data-ttu-id="71445-213">Дополнительные возможности редактирования помогают получить более согласованную и эффективную среду редактирования.</span><span class="sxs-lookup"><span data-stu-id="71445-213">The additional editing features provide a more consistent and powerful editing environment.</span></span>

<span data-ttu-id="71445-214">**Что работает иначе?**</span><span class="sxs-lookup"><span data-stu-id="71445-214">**What works differently?**</span></span>

<span data-ttu-id="71445-215">Эти усовершенствования редактирования отсутствовали в интегрированной среде сценариев Windows PowerShell 2.0.</span><span class="sxs-lookup"><span data-stu-id="71445-215">These editing enhancements weren't present in Windows PowerShell ISE 2.0.</span></span>

## <a name="new-help-viewer-window"></a><span data-ttu-id="71445-216">Новое окно справки</span><span class="sxs-lookup"><span data-stu-id="71445-216">New Help viewer window</span></span>

> <span data-ttu-id="71445-217">Добавлено в PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="71445-217">Added in PowerShell 3.0</span></span>

<span data-ttu-id="71445-218">Если нажать клавишу <kbd>F1</kbd>, когда курсор находится внутри командлета или выделена часть командлета, в новом окне справки откроется контекстная справка по выделенному командлету.</span><span class="sxs-lookup"><span data-stu-id="71445-218">If you press <kbd>F1</kbd> when your cursor is in a cmdlet, or you have part of a cmdlet highlighted, the new Help viewer opens context-sensitive Help about the highlighted cmdlet.</span></span> <span data-ttu-id="71445-219">Чтобы вывести раздел справки **О программе** в Windows PowerShell, введите команду `operators` в области консоли, а затем нажмите клавишу <kbd>F1</kbd>.</span><span class="sxs-lookup"><span data-stu-id="71445-219">To display Windows PowerShell **About** help, type `operators` in the console pane, and then press <kbd>F1</kbd>.</span></span>

<span data-ttu-id="71445-220">Прежде чем пользоваться этой функцией, загрузите последнюю версию разделов справки Windows PowerShell с веб-сайта Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="71445-220">Before you use this feature, download the most current version of Windows PowerShell Help topics from the Microsoft website.</span></span> <span data-ttu-id="71445-221">Разделы справки проще всего скачать, выполнив командлет `Update-Help` в области консоли при запуске интегрированной среды сценариев Windows PowerShell от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="71445-221">The simplest method for downloading the Help topics is to run the `Update-Help` cmdlet in the Console Pane when running Windows PowerShell ISE as administrator.</span></span>

<span data-ttu-id="71445-222">Где указать, откуда именно берется справка, вызываемая клавишей <kbd>F1</kbd>.</span><span class="sxs-lookup"><span data-stu-id="71445-222">You can alter where the <kbd>F1</kbd> key looks for Help.</span></span> <span data-ttu-id="71445-223">В разделе **Другие параметры** на вкладке **Общие параметры** в меню **Сервис**/**Параметры** можно установить или снять флажок **Использовать локальную справку вместо справки в Интернете**.</span><span class="sxs-lookup"><span data-stu-id="71445-223">In the **Tools**/**Options** menu, on the **General Settings** tab, under **Other Settings**, you can set or clear the checkbox **Use local help content instead of online content**.</span></span> <span data-ttu-id="71445-224">Если этот флажок установлен, клиент ищет справку по командлету в скачанных файлах, находящихся в папке модулей.</span><span class="sxs-lookup"><span data-stu-id="71445-224">When checked, the client looks for the cmdlet Help in the downloaded Help found in the modules folder.</span></span> <span data-ttu-id="71445-225">Если флажок не установлен, клиент ищет справку в Интернете.</span><span class="sxs-lookup"><span data-stu-id="71445-225">If the checkbox is cleared, the client looks for help online.</span></span>

<span data-ttu-id="71445-226">**Какой эффект дает это изменение?**</span><span class="sxs-lookup"><span data-stu-id="71445-226">**What value does this change add?**</span></span>

<span data-ttu-id="71445-227">Получение контекстной справки без выхода из командлета или скрипта делает обучение более удобным.</span><span class="sxs-lookup"><span data-stu-id="71445-227">Context-sensitive Help without leaving your current cmdlet or script provides an integrated learning experience.</span></span>

<span data-ttu-id="71445-228">**Что работает иначе?**</span><span class="sxs-lookup"><span data-stu-id="71445-228">**What works differently?**</span></span>

<span data-ttu-id="71445-229">При нажатии клавиши <kbd>F1</kbd> в предыдущих версиях интегрированной среды сценариев Windows PowerShell открывался файл справки с локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="71445-229">Pressing <kbd>F1</kbd> in previous versions of Windows PowerShell ISE opened the help file on the local computer.</span></span> <span data-ttu-id="71445-230">В интегрированной среде сценариев Windows PowerShell 3.0 и более поздних версий открывшееся окно содержит справку, поддерживающую поиск и настройку.</span><span class="sxs-lookup"><span data-stu-id="71445-230">In Windows PowerShell ISE 3.0 and later, a window opens that contains the help for the cmdlet that is searchable and configurable.</span></span> <span data-ttu-id="71445-231">Это новая справка по интегрированной среде сценариев Windows PowerShell ISE 3.0, в Windows PowerShell 3.0 появилась обновленная справка.</span><span class="sxs-lookup"><span data-stu-id="71445-231">This Help experience is new for Windows PowerShell ISE 3.0, and Updatable Help is new for Windows PowerShell 3.0.</span></span>

## <a name="show-command-cmdlet"></a><span data-ttu-id="71445-232">Командлет Show-Command</span><span class="sxs-lookup"><span data-stu-id="71445-232">Show-Command cmdlet</span></span>

> <span data-ttu-id="71445-233">Добавлено в PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="71445-233">Added in PowerShell 3.0</span></span>

<span data-ttu-id="71445-234">Командлет `Show-Command` позволяет создать или выполнить командлет или функцию, заполнив графическую форму.</span><span class="sxs-lookup"><span data-stu-id="71445-234">The `Show-Command` cmdlet enables you to compose or run a cmdlet or function by filling in a graphical form.</span></span> <span data-ttu-id="71445-235">Эта форма дает пользователям возможность работать с Windows PowerShell в графической среде.</span><span class="sxs-lookup"><span data-stu-id="71445-235">The form lets users work with Windows PowerShell in a graphical environment.</span></span>
<span data-ttu-id="71445-236">Кроме того, командлет `Show-Command` позволяет опытным программистам быстро создавать графические интерфейсы на основе Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="71445-236">`Show-Command` also enables advanced scripters to create a quick Windows PowerShell-based GUI.</span></span>

<span data-ttu-id="71445-237">**Какой эффект дает это изменение?**</span><span class="sxs-lookup"><span data-stu-id="71445-237">**What value does this change add?**</span></span>

<span data-ttu-id="71445-238">Используя командлет `Show-Command` в скриптах Windows PowerShell, вы можете предоставить пользователям привычную графическую среду.</span><span class="sxs-lookup"><span data-stu-id="71445-238">By using `Show-Command` in your Windows PowerShell scripts, you can provide your users with the graphical environment with which they're familiar.</span></span> <span data-ttu-id="71445-239">Кроме того, `Show-Command` помогает новичкам осваивать Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="71445-239">`Show-Command` can also help introductory users learn Windows PowerShell.</span></span>

<span data-ttu-id="71445-240">**Что работает иначе?**</span><span class="sxs-lookup"><span data-stu-id="71445-240">**What works differently?**</span></span>

<span data-ttu-id="71445-241">Командлет `Show-Command` впервые появился в интегрированной среде сценариев Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="71445-241">`Show-Command` is new Windows PowerShell ISE 3.0.</span></span>

## <a name="see-also"></a><span data-ttu-id="71445-242">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="71445-242">See also</span></span>

<span data-ttu-id="71445-243">См. дополнительные сведения об [использовании интегрированной среды сценариев Windows PowerShell](../components/ise/exploring-the-windows-powershell-ise.md).</span><span class="sxs-lookup"><span data-stu-id="71445-243">For more information about using Windows PowerShell ISE, see [Exploring the Windows PowerShell Integrated Scripting Environment](../components/ise/exploring-the-windows-powershell-ise.md).</span></span>
