---
title: Использование Visual Studio Code для разработки в PowerShell
description: Использование Visual Studio Code для разработки в PowerShell
ms.date: 11/07/2019
ms.openlocfilehash: 8a4ceb3da669716915449af2d211aaf2ae61bb4f
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2020
ms.locfileid: "94390300"
---
# <a name="using-visual-studio-code-for-powershell-development"></a><span data-ttu-id="d1aee-103">Использование Visual Studio Code для разработки в PowerShell</span><span class="sxs-lookup"><span data-stu-id="d1aee-103">Using Visual Studio Code for PowerShell Development</span></span>

<span data-ttu-id="d1aee-104">[Visual Studio Code][vscode] — это кросс-платформенный редактор скриптов, созданный корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="d1aee-104">[Visual Studio Code][vscode] is a cross-platform script editor by Microsoft.</span></span> <span data-ttu-id="d1aee-105">Наряду с [расширением PowerShell][psext] он предоставляет широкие интерактивные возможности редактирования скриптов, упрощая написание надежных скриптов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d1aee-105">Together with the [PowerShell extension][psext], it provides a rich and interactive script editing experience, making it easier to write reliable PowerShell scripts.</span></span> <span data-ttu-id="d1aee-106">Редактор Visual Studio Code с расширением PowerShell рекомендуется использовать для написания сценариев PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d1aee-106">Visual Studio Code with the PowerShell extension is the recommended editor for writing PowerShell scripts.</span></span>

<span data-ttu-id="d1aee-107">Он поддерживает следующие версии PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d1aee-107">It supports the following PowerShell versions:</span></span>

- <span data-ttu-id="d1aee-108">PowerShell 7 и последующие версии (Windows, macOS и Linux);</span><span class="sxs-lookup"><span data-stu-id="d1aee-108">PowerShell 7 and up (Windows, macOS, and Linux)</span></span>
- <span data-ttu-id="d1aee-109">PowerShell Core 6 (Windows, macOS и Linux);</span><span class="sxs-lookup"><span data-stu-id="d1aee-109">PowerShell Core 6 (Windows, macOS, and Linux)</span></span>
- <span data-ttu-id="d1aee-110">Windows PowerShell 5.1 (только для Windows).</span><span class="sxs-lookup"><span data-stu-id="d1aee-110">Windows PowerShell 5.1 (Windows-only)</span></span>

> [!NOTE]
> <span data-ttu-id="d1aee-111">Visual Studio Code отличается от [Visual Studio][].</span><span class="sxs-lookup"><span data-stu-id="d1aee-111">Visual Studio Code is not the same as [Visual Studio][].</span></span>

## <a name="getting-started"></a><span data-ttu-id="d1aee-112">Начало работы</span><span class="sxs-lookup"><span data-stu-id="d1aee-112">Getting started</span></span>

<span data-ttu-id="d1aee-113">Перед запуском убедитесь, что оболочка PowerShell установлена в системе.</span><span class="sxs-lookup"><span data-stu-id="d1aee-113">Before you begin, make sure PowerShell exists on your system.</span></span> <span data-ttu-id="d1aee-114">Сведения о современных рабочих нагрузках для Windows, macOS и Linux см. по следующим ссылкам:</span><span class="sxs-lookup"><span data-stu-id="d1aee-114">For modern workloads on Windows, macOS, and Linux, see the following links:</span></span>

- <span data-ttu-id="d1aee-115">[Установка PowerShell в Linux][install-pscore-linux]</span><span class="sxs-lookup"><span data-stu-id="d1aee-115">[Installing PowerShell on Linux][install-pscore-linux]</span></span>
- <span data-ttu-id="d1aee-116">[Установка PowerShell в macOS][install-pscore-macos]</span><span class="sxs-lookup"><span data-stu-id="d1aee-116">[Installing PowerShell on macOS][install-pscore-macos]</span></span>
- <span data-ttu-id="d1aee-117">[Установка PowerShell в Windows][install-pscore-windows]</span><span class="sxs-lookup"><span data-stu-id="d1aee-117">[Installing PowerShell on Windows][install-pscore-windows]</span></span>

<span data-ttu-id="d1aee-118">Сведения о традиционных рабочих нагрузках Windows PowerShell см. в разделе [Установка Windows PowerShell][install-winps].</span><span class="sxs-lookup"><span data-stu-id="d1aee-118">For traditional Windows PowerShell workloads, see [Installing Windows PowerShell][install-winps].</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d1aee-119">[Интегрированная среда сценариев Windows PowerShell][ise] по-прежнему доступна для Windows,</span><span class="sxs-lookup"><span data-stu-id="d1aee-119">The [Windows PowerShell ISE][ise] is still available for Windows.</span></span> <span data-ttu-id="d1aee-120">но функции для нее больше не разрабатываются.</span><span class="sxs-lookup"><span data-stu-id="d1aee-120">However, it is no longer in active feature development.</span></span> <span data-ttu-id="d1aee-121">Интегрированная среда сценариев не работает с PowerShell 6 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="d1aee-121">The ISE does not work with PowerShell 6 and higher.</span></span> <span data-ttu-id="d1aee-122">Как компонент Windows эта среда по-прежнему официально поддерживается для внесения критически важных исправлений, связанных с безопасностью и обслуживанием.</span><span class="sxs-lookup"><span data-stu-id="d1aee-122">As a component of Windows, it continues to be officially supported for security and high-priority servicing fixes.</span></span>
> <span data-ttu-id="d1aee-123">Пока что мы не планируем удалять ее из Windows.</span><span class="sxs-lookup"><span data-stu-id="d1aee-123">We have no plans to remove the ISE from Windows.</span></span>

## <a name="editing-with-visual-studio-code"></a><span data-ttu-id="d1aee-124">Редактирование с помощью Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="d1aee-124">Editing with Visual Studio Code</span></span>

1. <span data-ttu-id="d1aee-125">Установите Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="d1aee-125">Install Visual Studio Code.</span></span> <span data-ttu-id="d1aee-126">Дополнительные сведения см. в статье [Setting up Visual Studio Code][vsc-setup] (Настройка Visual Studio Code).</span><span class="sxs-lookup"><span data-stu-id="d1aee-126">For more information, see the overview [Setting up Visual Studio Code][vsc-setup].</span></span>

   <span data-ttu-id="d1aee-127">Доступны инструкции по установке на каждой платформе:</span><span class="sxs-lookup"><span data-stu-id="d1aee-127">There are installation instructions for each platform:</span></span>

   - <span data-ttu-id="d1aee-128">**Windows**: следуйте инструкциям по установке на странице [Запуск Visual Studio Code в Windows][vsc-setup-win].</span><span class="sxs-lookup"><span data-stu-id="d1aee-128">**Windows**: follow the installation instructions on the [Running Visual Studio Code on Windows][vsc-setup-win] page.</span></span>
   - <span data-ttu-id="d1aee-129">**macOS**: следуйте инструкциям по установке на странице [Запуск Visual Studio Code в macOS][vsc-setup-macOS].</span><span class="sxs-lookup"><span data-stu-id="d1aee-129">**macOS**: follow the installation instructions on the [Running Visual Studio Code on macOS][vsc-setup-macOS] page.</span></span>
   - <span data-ttu-id="d1aee-130">**Linux**: следуйте инструкциям по установке на странице [Запуск Visual Studio Code в Linux][vsc-setup-linux].</span><span class="sxs-lookup"><span data-stu-id="d1aee-130">**Linux**: follow the installation instructions on the [Running Visual Studio Code on Linux][vsc-setup-linux] page.</span></span>

1. <span data-ttu-id="d1aee-131">Установите расширение PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d1aee-131">Install the PowerShell Extension.</span></span>

   1. <span data-ttu-id="d1aee-132">Запустите приложение Visual Studio Code, введя `code` в консоли или `code-insiders`, если вы установили Visual Studio Code Insiders.</span><span class="sxs-lookup"><span data-stu-id="d1aee-132">Launch the Visual Studio Code app by typing `code` in a console or `code-insiders` if you installed Visual Studio Code Insiders.</span></span>
   1. <span data-ttu-id="d1aee-133">Запустите **Quick Open** в Windows или Linux, нажав клавиши <kbd>CTRL</kbd>+<kbd>P</kbd>.</span><span class="sxs-lookup"><span data-stu-id="d1aee-133">Launch **Quick Open** on Windows or Linux by pressing <kbd>Ctrl</kbd>+<kbd>P</kbd>.</span></span> <span data-ttu-id="d1aee-134">В macOS нажмите клавиши <kbd>CMD</kbd>+<kbd>P</kbd>.</span><span class="sxs-lookup"><span data-stu-id="d1aee-134">On macOS, press <kbd>Cmd</kbd>+<kbd>P</kbd>.</span></span>
   1. <span data-ttu-id="d1aee-135">В Quick Open введите `ext install powershell` и нажмите клавишу **ВВОД**.</span><span class="sxs-lookup"><span data-stu-id="d1aee-135">In Quick Open, type `ext install powershell` and press **Enter**.</span></span>
   1. <span data-ttu-id="d1aee-136">На боковой панели открывается представление **Расширения**.</span><span class="sxs-lookup"><span data-stu-id="d1aee-136">The **Extensions** view opens on the Side Bar.</span></span> <span data-ttu-id="d1aee-137">Выберите расширение PowerShell корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="d1aee-137">Select the PowerShell extension from Microsoft.</span></span>
      <span data-ttu-id="d1aee-138">Откроется примерно следующий экран Visual Studio Code:</span><span class="sxs-lookup"><span data-stu-id="d1aee-138">You should see a Visual Studio Code screen similar to the following image:</span></span>

      ![Visual Studio Code — обзор расширения PowerShell](media/using-vscode/vscode.png)

   1. <span data-ttu-id="d1aee-140">Нажмите кнопку **Установить** для расширения PowerShell корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="d1aee-140">Click the **Install** button on the PowerShell extension from Microsoft.</span></span>
   1. <span data-ttu-id="d1aee-141">После установки кнопка **Установить** изменяется на **Reload** (Перезагрузить). Нажмите кнопку **Reload** (Перезагрузить).</span><span class="sxs-lookup"><span data-stu-id="d1aee-141">After the install, if you see the **Install** button turn into **Reload**, Click on **Reload**.</span></span>
   1. <span data-ttu-id="d1aee-142">После перезагрузки Visual Studio Code можно приступать к редактированию.</span><span class="sxs-lookup"><span data-stu-id="d1aee-142">After Visual Studio Code has reloaded, you're ready for editing.</span></span>

<span data-ttu-id="d1aee-143">Например, чтобы создать файл, выберите **Файл > Создать**.</span><span class="sxs-lookup"><span data-stu-id="d1aee-143">For example, to create a new file, click **File > New**.</span></span> <span data-ttu-id="d1aee-144">Чтобы сохранить его, выберите **Файл > Сохранить** и укажите имя файла, например `HelloWorld.ps1`.</span><span class="sxs-lookup"><span data-stu-id="d1aee-144">To save it, click **File > Save** and then provide a file name, such as `HelloWorld.ps1`.</span></span> <span data-ttu-id="d1aee-145">Чтобы закрыть файл, щелкните `X` рядом с его именем.</span><span class="sxs-lookup"><span data-stu-id="d1aee-145">To close the file, click the `X` next to the file name.</span></span> <span data-ttu-id="d1aee-146">Чтобы завершить работу с Visual Studio Code, выберите элементы **Файл > Выйти**.</span><span class="sxs-lookup"><span data-stu-id="d1aee-146">To exit Visual Studio Code, **File > Exit**.</span></span>

### <a name="installing-the-powershell-extension-on-restricted-systems"></a><span data-ttu-id="d1aee-147">Установка расширения PowerShell в системах с ограниченным доступом</span><span class="sxs-lookup"><span data-stu-id="d1aee-147">Installing the PowerShell Extension on Restricted Systems</span></span>

<span data-ttu-id="d1aee-148">Некоторые системы настроены так, что требуют проверки всех подписей кода.</span><span class="sxs-lookup"><span data-stu-id="d1aee-148">Some systems are set up to require validation of all code signatures.</span></span> <span data-ttu-id="d1aee-149">Может появиться следующее сообщение об ошибке:</span><span class="sxs-lookup"><span data-stu-id="d1aee-149">You may receive the following error:</span></span>

```
Language server startup failed.
```

<span data-ttu-id="d1aee-150">Эта проблема может возникать, когда политика выполнения PowerShell задается групповой политикой Windows.</span><span class="sxs-lookup"><span data-stu-id="d1aee-150">This problem can occur when PowerShell's execution policy is set by Windows Group Policy.</span></span> <span data-ttu-id="d1aee-151">Чтобы вручную утвердить службы редактора PowerShell и, следовательно, расширение PowerShell для Visual Studio Code, откройте командную строку PowerShell и выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="d1aee-151">To manually approve PowerShell Editor Services and the PowerShell extension for Visual Studio Code, open a PowerShell prompt and run the following command:</span></span>

```powershell
Import-Module $HOME\.vscode\extensions\ms-vscode.powershell*\modules\PowerShellEditorServices\PowerShellEditorServices.psd1
```

<span data-ttu-id="d1aee-152">Вы увидите подсказку **Не удается проверить издателя. Вы действительно хотите запустить эту программу?**</span><span class="sxs-lookup"><span data-stu-id="d1aee-152">You're prompted with **Do you want to run software from this untrusted publisher?**</span></span> <span data-ttu-id="d1aee-153">Введите `A` для запуска файла.</span><span class="sxs-lookup"><span data-stu-id="d1aee-153">Type `A` to run the file.</span></span> <span data-ttu-id="d1aee-154">Затем откройте Visual Studio Code и убедитесь, что расширение PowerShell работает правильно.</span><span class="sxs-lookup"><span data-stu-id="d1aee-154">Then, open Visual Studio Code and check that the PowerShell extension is functioning properly.</span></span> <span data-ttu-id="d1aee-155">Если у вас все еще есть проблемы с началом работы, сообщите нам об этом на [Раздел с описанием проблем на GitHub][].</span><span class="sxs-lookup"><span data-stu-id="d1aee-155">If you still have problems getting started, let us know on [GitHub issues][].</span></span>

> [!NOTE]
> <span data-ttu-id="d1aee-156">Расширение PowerShell для Visual Studio Code не поддерживает запуск в ограниченном языковом режиме.</span><span class="sxs-lookup"><span data-stu-id="d1aee-156">The PowerShell extension for Visual Studio Code does not support running in constrained language mode.</span></span> <span data-ttu-id="d1aee-157">Дополнительные сведения см. в [описании ошибки № 606 на GitHub][i606].</span><span class="sxs-lookup"><span data-stu-id="d1aee-157">For more information, see [GitHub issue #606][i606].</span></span>

### <a name="choosing-a-version-of-powershell-to-use-with-the-extension"></a><span data-ttu-id="d1aee-158">Выбор версии PowerShell для использования с расширением</span><span class="sxs-lookup"><span data-stu-id="d1aee-158">Choosing a version of PowerShell to use with the extension</span></span>

<span data-ttu-id="d1aee-159">Благодаря одновременной установке PowerShell Core и Windows PowerShell теперь можно использовать определенную версию PowerShell с расширением PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d1aee-159">With PowerShell Core installing side-by-side with Windows PowerShell, it's now possible to use a specific version of PowerShell with the PowerShell extension.</span></span> <span data-ttu-id="d1aee-160">Этот компонент проверяет несколько известных расположений в разных операционных системах, чтобы найти установки PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d1aee-160">This feature looks at a few well-known paths on different operating systems to discover installations of PowerShell.</span></span>

<span data-ttu-id="d1aee-161">Выберите версию, сделав следующее:</span><span class="sxs-lookup"><span data-stu-id="d1aee-161">Use the following steps to choose the version:</span></span>

1. <span data-ttu-id="d1aee-162">Откройте **палитру команд** в Windows и Linux (<kbd>CTRL</kbd>+<kbd>SHIFT</kbd>+<kbd>P</kbd>).</span><span class="sxs-lookup"><span data-stu-id="d1aee-162">Open the **Command Palette** on Windows or Linux with <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd>.</span></span> <span data-ttu-id="d1aee-163">В macOS нажмите клавиши <kbd>CMD</kbd>+<kbd>SHIFT</kbd>+<kbd>P</kbd>.</span><span class="sxs-lookup"><span data-stu-id="d1aee-163">On macOS, use <kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd>.</span></span>
1. <span data-ttu-id="d1aee-164">Выполните поиск по слову **Сеанс**.</span><span class="sxs-lookup"><span data-stu-id="d1aee-164">Search for **Session**.</span></span>
1. <span data-ttu-id="d1aee-165">Щелкните **PowerShell: Show Session Menu** (PowerShell: показать меню сеансов).</span><span class="sxs-lookup"><span data-stu-id="d1aee-165">Click on **PowerShell: Show Session Menu**.</span></span>
1. <span data-ttu-id="d1aee-166">Выберите версию PowerShell, которую хотите использовать, из списка, например **PowerShell Core**.</span><span class="sxs-lookup"><span data-stu-id="d1aee-166">Choose the version of PowerShell you want to use from the list, for example: **PowerShell Core**.</span></span>

<span data-ttu-id="d1aee-167">Если вы установили PowerShell в нетипичном расположении, оно может первоначально не отобразиться в меню сеансов.</span><span class="sxs-lookup"><span data-stu-id="d1aee-167">If you installed PowerShell to a non-typical location, it might not show up initially in the Session Menu.</span></span> <span data-ttu-id="d1aee-168">Вы можете расширить меню сеансов, [добавив собственные пользовательские пути](#adding-your-own-powershell-paths-to-the-session-menu), как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="d1aee-168">You can extend the session menu by [adding your own custom paths](#adding-your-own-powershell-paths-to-the-session-menu) as described below.</span></span>

> [!NOTE]
> <span data-ttu-id="d1aee-169">Меню сеансов PowerShell также можно открыть, щелкнув номер версии,</span><span class="sxs-lookup"><span data-stu-id="d1aee-169">The PowerShell session menu can also be accessed from the green version number in the bottom right corner of status bar.</span></span> <span data-ttu-id="d1aee-170">который показан зеленым шрифтом в правом нижнем углу строки состояния.</span><span class="sxs-lookup"><span data-stu-id="d1aee-170">Clicking this version number opens the session menu.</span></span>

## <a name="configuration-settings-for-visual-studio-code"></a><span data-ttu-id="d1aee-171">Параметры конфигурации для Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="d1aee-171">Configuration settings for Visual Studio Code</span></span>

<span data-ttu-id="d1aee-172">Прежде всего, если вы не знаете, как изменить параметры в Visual Studio Code, мы рекомендуем ознакомиться с [документацией по параметрам Visual Studio Code][vsc-settings].</span><span class="sxs-lookup"><span data-stu-id="d1aee-172">First, if you're not familiar with how to change settings in Visual Studio Code, we recommend reading [Visual Studio Code's settings][vsc-settings] documentation.</span></span>

<span data-ttu-id="d1aee-173">После этого вы сможете добавить параметры конфигурации в `settings.json`.</span><span class="sxs-lookup"><span data-stu-id="d1aee-173">After reading the documentation, you can add configuration settings in `settings.json`.</span></span>

```json
{
    "editor.renderWhitespace": "all",
    "editor.renderControlCharacters": true,
    "files.trimTrailingWhitespace": true,
    "files.encoding": "utf8bom",
    "files.autoGuessEncoding": true
}
```

<span data-ttu-id="d1aee-174">Если вы не хотите, чтобы эти параметры влияли на файлы всех типов, Visual Studio Code также позволяет задавать конфигурации для каждого языка отдельно.</span><span class="sxs-lookup"><span data-stu-id="d1aee-174">If you don't want these settings to affect all files types, Visual Studio Code also allows per-language configurations.</span></span> <span data-ttu-id="d1aee-175">Создать параметр для конкретного языка можно, поместив параметры в поле `[<language-name>]`.</span><span class="sxs-lookup"><span data-stu-id="d1aee-175">Create a language-specific setting by putting settings in a `[<language-name>]` field.</span></span> <span data-ttu-id="d1aee-176">Пример:</span><span class="sxs-lookup"><span data-stu-id="d1aee-176">For example:</span></span>

```json
{
    "[powershell]": {
        "files.encoding": "utf8bom",
        "files.autoGuessEncoding": true
    }
}
```

> [!TIP]
> <span data-ttu-id="d1aee-177">Дополнительные сведения о кодировке файлов в Visual Studio Code см. в статье [Основные сведения о кодировке файлов в VSCode и PowerShell][file-encoding].</span><span class="sxs-lookup"><span data-stu-id="d1aee-177">For more information about file encoding in Visual Studio Code, see [Understanding file encoding][file-encoding].</span></span>
>
> <span data-ttu-id="d1aee-178">Также ознакомьтесь со статьей [Репликация функций интегрированной среды скриптов в Visual Studio Code][vsc-ise], в которой даны рекомендации по настройке Visual Studio Code для редактирования в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d1aee-178">Also, check out [How to replicate the ISE experience in Visual Studio Code][vsc-ise] for other tips on how to configure Visual Studio Code for PowerShell editing.</span></span>

### <a name="adding-your-own-powershell-paths-to-the-session-menu"></a><span data-ttu-id="d1aee-179">Добавление собственных путей PowerShell в меню сеансов</span><span class="sxs-lookup"><span data-stu-id="d1aee-179">Adding your own PowerShell paths to the session menu</span></span>

<span data-ttu-id="d1aee-180">В меню сеанса можно добавить другие пути к исполнимому файлу PowerShell с помощью [параметра Visual Studio Code](https://code.visualstudio.com/docs/getstarted/settings): `powershell.powerShellAdditionalExePaths`.</span><span class="sxs-lookup"><span data-stu-id="d1aee-180">You can add other PowerShell executable paths to the session menu through the [Visual Studio Code setting](https://code.visualstudio.com/docs/getstarted/settings): `powershell.powerShellAdditionalExePaths`.</span></span>

<span data-ttu-id="d1aee-181">Добавьте элемент в список `powershell.powerShellAdditionalExePaths` или создайте список, если его нет в `settings.json`:</span><span class="sxs-lookup"><span data-stu-id="d1aee-181">Add an item to the list `powershell.powerShellAdditionalExePaths` or create the list if it doesn't exist in your `settings.json`:</span></span>

```json
{
    // other settings...

    "powershell.powerShellAdditionalExePaths": [
        {
            "exePath": "C:\\Users\\tyler\\Downloads\\PowerShell\\pwsh.exe",
            "versionName": "Downloaded PowerShell"
        }
    ],

    // other settings...
}
```

<span data-ttu-id="d1aee-182">Каждый элемент должен иметь следующее:</span><span class="sxs-lookup"><span data-stu-id="d1aee-182">Each item must have:</span></span>

- <span data-ttu-id="d1aee-183">`exePath`: Путь к исполняемому файлу `pwsh` или `powershell`.</span><span class="sxs-lookup"><span data-stu-id="d1aee-183">`exePath`: The path to the `pwsh` or `powershell` executable.</span></span>
- <span data-ttu-id="d1aee-184">`versionName`: Текст, который будет отображаться в меню сеансов.</span><span class="sxs-lookup"><span data-stu-id="d1aee-184">`versionName`: The text that will show up in the session menu.</span></span>

<span data-ttu-id="d1aee-185">Вы можете задать используемую версию PowerShell по умолчанию, задав параметр `powershell.powerShellDefaultVersion` для текста, отображаемого в меню сеансов (`versionName` в последнем параметре):</span><span class="sxs-lookup"><span data-stu-id="d1aee-185">To set the default PowerShell version, set the value `powershell.powerShellDefaultVersion` to the text displayed in the session menu (also known as the `versionName`):</span></span>

```json
{
    // other settings...

    "powershell.powerShellAdditionalExePaths": [
        {
            "exePath": "C:\\Users\\tyler\\Downloads\\PowerShell\\pwsh.exe",
            "versionName": "Downloaded PowerShell"
        }
    ],

    "powershell.powerShellDefaultVersion": "Downloaded PowerShell",

    // other settings...
}
```

<span data-ttu-id="d1aee-186">Задав этот параметр, перезапустите Visual Studio Code или перезагрузите текущее окно Visual Studio Code через **Палитру команд**, введя **Разработчик: Reload Window** (Разработчик: перезагрузить окно).</span><span class="sxs-lookup"><span data-stu-id="d1aee-186">After you've configured this setting, restart Visual Studio Code or to reload the current Visual Studio Code window from the **Command Palette**, type **Developer: Reload Window**.</span></span>

<span data-ttu-id="d1aee-187">Открыв меню сеансов, вы увидите дополнительные версии PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d1aee-187">If you open the session menu, you now see your additional PowerShell versions!</span></span>

> [!NOTE]
> <span data-ttu-id="d1aee-188">Если вы создаете PowerShell из исходного кода, это отличный способ протестировать локальную сборку PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d1aee-188">If you build PowerShell from source, this is a great way to test out your local build of PowerShell.</span></span>

### <a name="using-an-older-version-of-the-powershell-extension-for-windows-powershell-v3-and-v4"></a><span data-ttu-id="d1aee-189">Использование более ранней версии расширения PowerShell для Windows PowerShell версий 3 и 4</span><span class="sxs-lookup"><span data-stu-id="d1aee-189">Using an older version of the PowerShell Extension for Windows PowerShell v3 and v4</span></span>

<span data-ttu-id="d1aee-190">Хотя текущее расширение PowerShell не поддерживает работу с [PowerShell версии 3 и 4][i1310],</span><span class="sxs-lookup"><span data-stu-id="d1aee-190">The current PowerShell extension doesn't support [PowerShell v3 and v4][i1310].</span></span> <span data-ttu-id="d1aee-191">вы можете использовать последнюю версию расширения, которая поддерживает работу с третьей и четвертой версией.</span><span class="sxs-lookup"><span data-stu-id="d1aee-191">However, you can use the last version of the extension that supports PowerShell v3 and v4.</span></span>

> [!CAUTION]
> <span data-ttu-id="d1aee-192">Дополнительные исправления для этой старой версии расширения не будут внесены.</span><span class="sxs-lookup"><span data-stu-id="d1aee-192">There will be no additional fixes to this older version of the extension.</span></span> <span data-ttu-id="d1aee-193">Она предоставляется без изменений, но доступна для вас, если вы все еще используете Windows PowerShell версии 3 или 4.</span><span class="sxs-lookup"><span data-stu-id="d1aee-193">It's provided "AS IS" but is available for you if you are still using Windows PowerShell v3 and Windows PowerShell v4.</span></span>

<span data-ttu-id="d1aee-194">Сначала откройте панель расширений и найдите `PowerShell`.</span><span class="sxs-lookup"><span data-stu-id="d1aee-194">First, open the Extension pane and search for `PowerShell`.</span></span> <span data-ttu-id="d1aee-195">Затем щелкните значок шестеренки и выберите команду **Install another version...** (Установить другую версию...).</span><span class="sxs-lookup"><span data-stu-id="d1aee-195">Then click the gear and select **Install another version...**.</span></span>

![Пункт меню — "Установить другую версию..."](media/using-vscode/install-another-version.png)

<span data-ttu-id="d1aee-197">Затем выберите версию **2020.1.0**.</span><span class="sxs-lookup"><span data-stu-id="d1aee-197">Then select the **2020.1.0** version.</span></span> <span data-ttu-id="d1aee-198">Эта версия расширения — последняя версия, которую поддерживает Windows PowerShell версий 3 и 4.</span><span class="sxs-lookup"><span data-stu-id="d1aee-198">This version of the extension was the last version to support v3 and v4.</span></span> <span data-ttu-id="d1aee-199">Обязательно добавьте следующий параметр, чтобы версия расширения не обновлялась автоматически:</span><span class="sxs-lookup"><span data-stu-id="d1aee-199">Be sure to add the following setting so that your extension version doesn't update automatically:</span></span>

```json
{
    "extensions.autoUpdate": false
}
```

<span data-ttu-id="d1aee-200">Версия **2020.1.0** будет актуальной в ближайшем будущем,</span><span class="sxs-lookup"><span data-stu-id="d1aee-200">Version **2020.1.0** will work for the foreseeable future.</span></span> <span data-ttu-id="d1aee-201">но в Visual Studio Code может появиться изменение, которое приведет к прекращению поддержки этой версии расширения.</span><span class="sxs-lookup"><span data-stu-id="d1aee-201">However, Visual Studio Code could implement a change that breaks this version of the extension.</span></span> <span data-ttu-id="d1aee-202">Учитывая это, а также отсутствие поддержки, мы рекомендуем:</span><span class="sxs-lookup"><span data-stu-id="d1aee-202">Because of this, and lack of support, we recommend:</span></span>

- <span data-ttu-id="d1aee-203">выполнить обновление до Windows PowerShell 5.1.</span><span class="sxs-lookup"><span data-stu-id="d1aee-203">Upgrading to Windows PowerShell 5.1</span></span>
- <span data-ttu-id="d1aee-204">установить среду PowerShell 7, которая доступна для параллельной установки с другими версиями Windows PowerShell и наилучшим образом подходит для расширения PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d1aee-204">Install PowerShell 7, which is a side-by-side install to Windows PowerShell and works the best with the PowerShell extension</span></span>

## <a name="debugging-with-visual-studio-code"></a><span data-ttu-id="d1aee-205">Отладка с помощью Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="d1aee-205">Debugging with Visual Studio Code</span></span>

### <a name="no-workspace-debugging"></a><span data-ttu-id="d1aee-206">Отладка без рабочей области</span><span class="sxs-lookup"><span data-stu-id="d1aee-206">No-workspace debugging</span></span>

<span data-ttu-id="d1aee-207">Начиная с версии Visual Studio Code 1.9, вы можете отлаживать скрипты PowerShell, не открывая папку со скриптом PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d1aee-207">In Visual Studio Code version 1.9 (or higher), you can debug PowerShell scripts without opening the folder that contains the PowerShell script.</span></span>

1. <span data-ttu-id="d1aee-208">Откройте файл скрипта PowerShell с помощью команды **Файл > Открыть файл**.</span><span class="sxs-lookup"><span data-stu-id="d1aee-208">Open the PowerShell script file with **File > Open File...**</span></span>
1. <span data-ttu-id="d1aee-209">Установите точку останова на строке и нажмите клавишу <kbd>F9</kbd>.</span><span class="sxs-lookup"><span data-stu-id="d1aee-209">Set a breakpoint - select a line then press <kbd>F9</kbd></span></span>
1. <span data-ttu-id="d1aee-210">Нажмите клавишу <kbd>F5</kbd>, чтобы запустить отладку.</span><span class="sxs-lookup"><span data-stu-id="d1aee-210">Press <kbd>F5</kbd> to start debugging</span></span>

<span data-ttu-id="d1aee-211">Откроется панель действий отладки, позволяющая прервать работу отладчика, возобновить отладку, выполнить ее пошагово или остановить.</span><span class="sxs-lookup"><span data-stu-id="d1aee-211">You should see the Debug actions pane appear which allows you to break into the debugger, step, resume, and stop debugging.</span></span>

### <a name="workspace-debugging"></a><span data-ttu-id="d1aee-212">Отладка с рабочей областью</span><span class="sxs-lookup"><span data-stu-id="d1aee-212">Workspace debugging</span></span>

<span data-ttu-id="d1aee-213">Отладка с рабочей областью обозначает отладку в контексте папки, которую вы открыли с помощью команды **Открыть папку** из меню **Файл**. Открытая папка обычно является папкой проекта PowerShell или корнем репозитория Git.</span><span class="sxs-lookup"><span data-stu-id="d1aee-213">Workspace debugging refers to debugging in the context of a folder that you've opened from the **File** menu using **Open Folder...**. The folder you open is typically your PowerShell project folder or the root of your Git repository.</span></span> <span data-ttu-id="d1aee-214">Отладка с рабочей областью позволяет задать несколько конфигураций отладки, а не просто выполнить отладку открытого файла.</span><span class="sxs-lookup"><span data-stu-id="d1aee-214">Workspace debugging allows you to define multiple debug configurations other than just debugging the currently open file.</span></span>

<span data-ttu-id="d1aee-215">Выполните следующие действия, чтобы создать файл конфигурации отладки:</span><span class="sxs-lookup"><span data-stu-id="d1aee-215">Follow these steps to create a debug configuration file:</span></span>

1. <span data-ttu-id="d1aee-216">Откройте представление **Отладка** в Windows или Linux (<kbd>CTRL</kbd>+<kbd>SHIFT</kbd>+<kbd>D</kbd>).</span><span class="sxs-lookup"><span data-stu-id="d1aee-216">Open the **Debug** view on Windows or Linux by pressing <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>D</kbd>.</span></span> <span data-ttu-id="d1aee-217">В macOS нажмите клавиши <kbd>CMD</kbd>+<kbd>SHIFT</kbd>+<kbd>D</kbd>.</span><span class="sxs-lookup"><span data-stu-id="d1aee-217">On macOS, press <kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>D</kbd>.</span></span>
1. <span data-ttu-id="d1aee-218">Щелкните ссылку **create a launch.json file** (Создать файл launch.json).</span><span class="sxs-lookup"><span data-stu-id="d1aee-218">Click the **create a launch.json file** link.</span></span>
1. <span data-ttu-id="d1aee-219">В окне запроса **Select Environment** (Выбор среды) выберите **PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="d1aee-219">From the **Select Environment** prompt, choose **PowerShell**.</span></span>
1. <span data-ttu-id="d1aee-220">Выберите тип отладки, который хотите использовать:</span><span class="sxs-lookup"><span data-stu-id="d1aee-220">Choose the type of debugging you'd like to use:</span></span>

   - <span data-ttu-id="d1aee-221">**Launch Current File** (Запуск текущего файла) — запуск и отладка файла в текущем активном окне редактора.</span><span class="sxs-lookup"><span data-stu-id="d1aee-221">**Launch Current File** - Launch and debug the file in the currently active editor window</span></span>
   - <span data-ttu-id="d1aee-222">**Launch Script** (Запуск скрипта) — запуск и отладка указанного файла или команды.</span><span class="sxs-lookup"><span data-stu-id="d1aee-222">**Launch Script** - Launch and debug the specified file or command</span></span>
   - <span data-ttu-id="d1aee-223">**Interactive Session** (Интерактивный сеанс) — команды отладки, выполняемые из интегрированной консоли.</span><span class="sxs-lookup"><span data-stu-id="d1aee-223">**Interactive Session** - Debug commands executed from the Integrated Console</span></span>
   - <span data-ttu-id="d1aee-224">**Attach (Подключение)**  — подключение отладчика к выполняемому хост-процессу PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d1aee-224">**Attach** - Attach the debugger to a running PowerShell Host Process</span></span>

<span data-ttu-id="d1aee-225">Visual Studio Code создаст каталог и файл `.vscode\launch.json` в корневой папке рабочей области, где будет храниться конфигурация отладки.</span><span class="sxs-lookup"><span data-stu-id="d1aee-225">Visual Studio Code creates a directory and a file `.vscode\launch.json` in the root of your workspace folder to store the debug configuration.</span></span> <span data-ttu-id="d1aee-226">Если ваши файлы хранятся в репозитории Git, скорее всего, вы захотите зафиксировать файл `launch.json`.</span><span class="sxs-lookup"><span data-stu-id="d1aee-226">If your files are in a Git repository, you typically want to commit the `launch.json` file.</span></span> <span data-ttu-id="d1aee-227">Содержимое файла `launch.json`:</span><span class="sxs-lookup"><span data-stu-id="d1aee-227">The contents of the `launch.json` file are:</span></span>

```json
{
  "version": "0.2.0",
  "configurations": [
      {
          "type": "PowerShell",
          "request": "launch",
          "name": "PowerShell Launch (current file)",
          "script": "${file}",
          "args": [],
          "cwd": "${file}"
      },
      {
          "type": "PowerShell",
          "request": "attach",
          "name": "PowerShell Attach to Host Process",
          "processId": "${command.PickPSHostProcess}",
          "runspaceId": 1
      },
      {
          "type": "PowerShell",
          "request": "launch",
          "name": "PowerShell Interactive Session",
          "cwd": "${workspaceRoot}"
      }
  ]
}
```

<span data-ttu-id="d1aee-228">Этот файл представляет типичные сценарии отладки.</span><span class="sxs-lookup"><span data-stu-id="d1aee-228">This file represents the common debug scenarios.</span></span> <span data-ttu-id="d1aee-229">При открытии его в редакторе отображается кнопка **Добавить конфигурацию...**</span><span class="sxs-lookup"><span data-stu-id="d1aee-229">When you open this file in the editor, you see an **Add Configuration...** button.</span></span> <span data-ttu-id="d1aee-230">Можете нажать ее, чтобы добавить дополнительные конфигурации отладки PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d1aee-230">You can click this button to add more PowerShell debug configurations.</span></span> <span data-ttu-id="d1aee-231">Одной из полезных конфигураций является **PowerShell: Launch Script** (Запустить сценарий).</span><span class="sxs-lookup"><span data-stu-id="d1aee-231">One useful configuration to add is **PowerShell: Launch Script**.</span></span> <span data-ttu-id="d1aee-232">С помощью этой конфигурации можно указать файл с дополнительными аргументами, которые используются при каждом нажатии клавиши <kbd>F5</kbd>, независимо от того, какой файл активен в редакторе.</span><span class="sxs-lookup"><span data-stu-id="d1aee-232">With this configuration, you can specify a file containing optional arguments that are used whenever you press <kbd>F5</kbd> no matter which file is active in the editor.</span></span>

<span data-ttu-id="d1aee-233">После задания конфигурации отладки вы можете указать конфигурацию, используемую во время сеанса отладки,</span><span class="sxs-lookup"><span data-stu-id="d1aee-233">After the debug configuration is established, you can select which configuration you want to use during a debug session.</span></span> <span data-ttu-id="d1aee-234">выбрав ее в раскрывающемся списке конфигураций отладки на панели инструментов представления **Отладка**.</span><span class="sxs-lookup"><span data-stu-id="d1aee-234">Select a configuration from the debug configuration drop-down in the **Debug** view's toolbar.</span></span>

## <a name="troubleshooting-the-powershell-extension-for-visual-studio-code"></a><span data-ttu-id="d1aee-235">Устранение проблем с расширением PowerShell для Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="d1aee-235">Troubleshooting the PowerShell extension for Visual Studio Code</span></span>

<span data-ttu-id="d1aee-236">Если у вас возникли проблемы с использованием Visual Studio Code для разработки скриптов PowerShell, ознакомьтесь с [руководством по устранению неполадок][troubleshooting] на сайте GitHub.</span><span class="sxs-lookup"><span data-stu-id="d1aee-236">If you experience any issues using Visual Studio Code for PowerShell script development, see the [troubleshooting guide][troubleshooting] on GitHub.</span></span>

## <a name="useful-resources"></a><span data-ttu-id="d1aee-237">Полезные ресурсы</span><span class="sxs-lookup"><span data-stu-id="d1aee-237">Useful resources</span></span>

<span data-ttu-id="d1aee-238">Существует несколько видео и записей блогов, которые могут оказаться полезными при начале работы с расширением PowerShell для Visual Studio Code:</span><span class="sxs-lookup"><span data-stu-id="d1aee-238">There are a few videos and blog posts that may be helpful to get you started using the PowerShell extension for Visual Studio Code:</span></span>

### <a name="videos"></a><span data-ttu-id="d1aee-239">Видео</span><span class="sxs-lookup"><span data-stu-id="d1aee-239">Videos</span></span>

- [<span data-ttu-id="d1aee-240">Использование Visual Studio Code в качестве редактора PowerShell по умолчанию</span><span class="sxs-lookup"><span data-stu-id="d1aee-240">Using Visual Studio Code as Your Default PowerShell Editor</span></span>](https://youtu.be/bGn45vIeAMM)
- [<span data-ttu-id="d1aee-241">Visual Studio Code: подробный обзор отладки сценариев PowerShell</span><span class="sxs-lookup"><span data-stu-id="d1aee-241">Visual Studio Code: deep dive into debugging your PowerShell scripts</span></span>](https://youtu.be/cSbIXmlkr8o)

### <a name="blog-posts"></a><span data-ttu-id="d1aee-242">Записи блога</span><span class="sxs-lookup"><span data-stu-id="d1aee-242">Blog posts</span></span>

- <span data-ttu-id="d1aee-243">[Расширение PowerShell][pscdn]</span><span class="sxs-lookup"><span data-stu-id="d1aee-243">[PowerShell Extension][pscdn]</span></span>
- <span data-ttu-id="d1aee-244">[Написание и отладка в сценариев PowerShell в Visual Studio Code][debug]</span><span class="sxs-lookup"><span data-stu-id="d1aee-244">[Write and debug PowerShell scripts in Visual Studio Code][debug]</span></span>
- <span data-ttu-id="d1aee-245">[Руководство по отладке Visual Studio Code][psdbgblog]</span><span class="sxs-lookup"><span data-stu-id="d1aee-245">[Debugging Visual Studio Code Guidance][psdbgblog]</span></span>
- <span data-ttu-id="d1aee-246">[Отладка PowerShell в Visual Studio Code][psdbg-gh]</span><span class="sxs-lookup"><span data-stu-id="d1aee-246">[Debugging PowerShell in Visual Studio Code][psdbg-gh]</span></span>
- <span data-ttu-id="d1aee-247">[Приступая к разработке PowerShell в Visual Studio Code][getting-started]</span><span class="sxs-lookup"><span data-stu-id="d1aee-247">[Get started with PowerShell development in Visual Studio Code][getting-started]</span></span>
- <span data-ttu-id="d1aee-248">[Функции редактирования Visual Studio Code для разработки PowerShell. Часть 1][editing-part1]</span><span class="sxs-lookup"><span data-stu-id="d1aee-248">[Visual Studio Code editing features for PowerShell development – Part 1][editing-part1]</span></span>
- <span data-ttu-id="d1aee-249">[Функции редактирования Visual Studio Code для разработки PowerShell. Часть 2][editing-part2]</span><span class="sxs-lookup"><span data-stu-id="d1aee-249">[Visual Studio Code editing features for PowerShell development – Part 2][editing-part2]</span></span>
- <span data-ttu-id="d1aee-250">[Отладка сценария PowerShell в Visual Studio Code. Часть 1][debugging-part1]</span><span class="sxs-lookup"><span data-stu-id="d1aee-250">[Debugging PowerShell script in Visual Studio Code – Part 1][debugging-part1]</span></span>
- <span data-ttu-id="d1aee-251">[Отладка сценария PowerShell в Visual Studio Code. Часть 2][debugging-part2]</span><span class="sxs-lookup"><span data-stu-id="d1aee-251">[Debugging PowerShell script in Visual Studio Code – Part 2][debugging-part2]</span></span>

## <a name="powershell-extension-project-source-code"></a><span data-ttu-id="d1aee-252">Исходный код проекта расширения PowerShell</span><span class="sxs-lookup"><span data-stu-id="d1aee-252">PowerShell extension project source code</span></span>

<span data-ttu-id="d1aee-253">Исходный код расширения PowerShell доступен на [GitHub][psext-src].</span><span class="sxs-lookup"><span data-stu-id="d1aee-253">The PowerShell extension's source code can be found on [GitHub][psext-src].</span></span>

<span data-ttu-id="d1aee-254">Если вы хотите принять участие в проекте в качестве разработчика, отправьте запрос на вытягивание.</span><span class="sxs-lookup"><span data-stu-id="d1aee-254">If you're interested in contributing, Pull Requests are greatly appreciated.</span></span> <span data-ttu-id="d1aee-255">Чтобы приступить к работе, следуйте указаниям из [документации для разработчиков][dev-docs] на сайте GitHub.</span><span class="sxs-lookup"><span data-stu-id="d1aee-255">Follow along with the [developer documentation][dev-docs] on GitHub to get started.</span></span>

<!-- related articles -->
[ise]:                    ../../windows-powershell/ise/Introducing-the-Windows-PowerShell-ISE.md
[install-pscore-linux]:   ../../install/Installing-PowerShell-Core-on-Linux.md
[install-pscore-macos]:   ../../install/Installing-PowerShell-Core-on-macOS.md
[install-pscore-windows]: ../../install/Installing-PowerShell-Core-on-Windows.md
[install-winps]:          ../../install/Installing-Windows-PowerShell.md
[file-encoding]:          understanding-file-encoding.md
[vsc-ise]:                How-To-Replicate-the-ISE-Experience-In-VSCode.md

<!-- blogs -->
[debug]:                  https://devblogs.microsoft.com/powershell/announcing-powershell-language-support-for-visual-studio-code-and-more/
[debugging-part1]:        https://devblogs.microsoft.com/scripting/debugging-powershell-script-in-visual-studio-code-part-1/
[debugging-part2]:        https://devblogs.microsoft.com/scripting/debugging-powershell-script-in-visual-studio-code-part-2/
[editing-part1]:          https://devblogs.microsoft.com/scripting/visual-studio-code-editing-features-for-powershell-development-part-1/
[editing-part2]:          https://devblogs.microsoft.com/scripting/visual-studio-code-editing-features-for-powershell-development-part-2/
[getting-started]:        https://devblogs.microsoft.com/scripting/get-started-with-powershell-development-in-visual-studio-code/
[psdbgblog]:              https://johnpapa.net/debugging-with-visual-studio-code/
[psdbg-gh]:               https://github.com/PowerShell/vscode-powershell/tree/master/examples
[pscdn]:                  https://docs.microsoft.com/archive/blogs/cdndevs/visual-studio-code-powershell-extension

<!-- issues -->
[Раздел с описанием проблем на GitHub]:          https://github.com/PowerShell/vscode-powershell/issues
[GitHub issues]:          https://github.com/PowerShell/vscode-powershell/issues
[i1310]:                  https://github.com/PowerShell/vscode-powershell/issues/1310
[i606]:                   https://github.com/PowerShell/vscode-powershell/issues/606

<!-- product links -->
[Visual Studio]:          https://visualstudio.microsoft.com/
[vscode]:                 https://code.visualstudio.com/
[psext]:                  https://marketplace.visualstudio.com/items?itemName=ms-vscode.PowerShell
[vsc-settings]:           https://code.visualstudio.com/docs/getstarted/settings
[vsc-setup]:              https://code.visualstudio.com/Docs/setup/setup-overview
[vsc-setup-win]:          https://code.visualstudio.com/docs/setup/windows
[vsc-setup-macos]:        https://code.visualstudio.com/docs/setup/mac
[vsc-setup-linux]:        https://code.visualstudio.com/docs/setup/linux
[psext-src]:              https://github.com/PowerShell/vscode-powershell
[troubleshooting]:        https://github.com/PowerShell/vscode-powershell/blob/master/docs/troubleshooting.md
[dev-docs]:               https://github.com/PowerShell/vscode-powershell/blob/master/docs/development.md
