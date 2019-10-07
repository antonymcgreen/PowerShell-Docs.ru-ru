---
title: Использование Visual Studio Code для разработки в PowerShell
description: Использование Visual Studio Code для разработки в PowerShell
ms.date: 08/06/2018
ms.openlocfilehash: 0e082b74f99d214749f10224fb5aaf41e2ef8951
ms.sourcegitcommit: 4a2cf30351620a58ba95ff5d76b247e601907589
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/27/2019
ms.locfileid: "71325231"
---
# <a name="using-visual-studio-code-for-powershell-development"></a><span data-ttu-id="631bd-103">Использование Visual Studio Code для разработки в PowerShell</span><span class="sxs-lookup"><span data-stu-id="631bd-103">Using Visual Studio Code for PowerShell Development</span></span>

<span data-ttu-id="631bd-104">В дополнение к [интегрированной среде сценариев PowerShell][ise] продукт PowerShell также хорошо поддерживается в Visual Studio Code (VSCode).</span><span class="sxs-lookup"><span data-stu-id="631bd-104">In addition to the [PowerShell ISE][ise], PowerShell is also well-supported in Visual Studio Code (VSCode).</span></span> <span data-ttu-id="631bd-105">Кроме того, интегрированная среда сценариев не поддерживается в PowerShell Core, хотя VSCode поддерживается для PowerShell Core на всех платформах (Windows, macOS и Linux).</span><span class="sxs-lookup"><span data-stu-id="631bd-105">Furthermore, the ISE is not supported with PowerShell Core, while VSCode is supported for PowerShell Core on all platforms (Windows, macOS, and Linux)</span></span>

<span data-ttu-id="631bd-106">Вы можете использовать VSCode для Windows вместе с PowerShell версии 5 в Windows 10 или установить [Windows Management Framework 5.0 RTM](https://devblogs.microsoft.com/powershell/windows-management-framework-wmf-5-0-rtm-is-now-available-via-the-microsoft-update-catalog/) для более низких версий Windows (например, Windows 8.1 и т. д.).</span><span class="sxs-lookup"><span data-stu-id="631bd-106">You can use VSCode on Windows with PowerShell version 5 by using Windows 10 or by installing [Windows Management Framework 5.0 RTM](https://devblogs.microsoft.com/powershell/windows-management-framework-wmf-5-0-rtm-is-now-available-via-the-microsoft-update-catalog/) for down-level Windows OSs (e.g. Windows 8.1, etc.).</span></span>

<span data-ttu-id="631bd-107">Перед запуском убедитесь, что PowerShell установлен в системе.</span><span class="sxs-lookup"><span data-stu-id="631bd-107">Before starting it, please make sure PowerShell exists on your system.</span></span> <span data-ttu-id="631bd-108">Сведения о современных рабочих нагрузках для Windows, macOS и Linux см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="631bd-108">For modern workloads on Windows, macOS, and Linux, see:</span></span>

- <span data-ttu-id="631bd-109">[Установка PowerShell Core в Linux][install-pscore-linux]</span><span class="sxs-lookup"><span data-stu-id="631bd-109">[Installing PowerShell Core on Linux][install-pscore-linux]</span></span>
- <span data-ttu-id="631bd-110">[Установка PowerShell Core в macOS][install-pscore-macos]</span><span class="sxs-lookup"><span data-stu-id="631bd-110">[Installing PowerShell Core on macOS][install-pscore-macos]</span></span>
- <span data-ttu-id="631bd-111">[Установка PowerShell Core в Windows][install-pscore-windows]</span><span class="sxs-lookup"><span data-stu-id="631bd-111">[Installing PowerShell Core on Windows][install-pscore-windows]</span></span>

<span data-ttu-id="631bd-112">Сведения о традиционных рабочих нагрузках Windows PowerShell см. в разделе [Установка Windows PowerShell][install-winps].</span><span class="sxs-lookup"><span data-stu-id="631bd-112">For traditional Windows PowerShell workloads, see [Installing Windows PowerShell][install-winps].</span></span>

## <a name="editing-with-vscode"></a><span data-ttu-id="631bd-113">Редактирование с помощью VSCode</span><span class="sxs-lookup"><span data-stu-id="631bd-113">Editing with VSCode</span></span>

1. [<span data-ttu-id="631bd-114">Установка VSCode</span><span class="sxs-lookup"><span data-stu-id="631bd-114">Installing VSCode</span></span>](https://code.visualstudio.com/Docs/setup/setup-overview)

   - <span data-ttu-id="631bd-115">**Linux**: следуйте инструкциям по установке на странице [Запуск VSCode в Linux](https://code.visualstudio.com/docs/setup/linux).</span><span class="sxs-lookup"><span data-stu-id="631bd-115">**Linux**: follow the installation instructions on the [Running VSCode on Linux](https://code.visualstudio.com/docs/setup/linux) page</span></span>
   - <span data-ttu-id="631bd-116">**macOS**: следуйте инструкциям по установке на странице [Запуск VSCode в macOS](https://code.visualstudio.com/docs/setup/mac).</span><span class="sxs-lookup"><span data-stu-id="631bd-116">**macOS**: follow the installation instructions on the [Running VSCode on macOS](https://code.visualstudio.com/docs/setup/mac) page</span></span>

     > [!IMPORTANT]
     > <span data-ttu-id="631bd-117">В macOS нужно установить OpenSSL для правильной работы расширения PowerShell.</span><span class="sxs-lookup"><span data-stu-id="631bd-117">On macOS, you must install OpenSSL for the PowerShell extension to work correctly.</span></span> <span data-ttu-id="631bd-118">Для этого проще всего установить [Homebrew](https://brew.sh/), а затем запустить `brew install openssl`.</span><span class="sxs-lookup"><span data-stu-id="631bd-118">The easiest way to accomplish this is to install [Homebrew](https://brew.sh/) and then run `brew install openssl`.</span></span> <span data-ttu-id="631bd-119">Теперь VSCode сможет загрузить расширение PowerShell правильно.</span><span class="sxs-lookup"><span data-stu-id="631bd-119">VSCode can now load the PowerShell extension successfully.</span></span>

   - <span data-ttu-id="631bd-120">**Windows**: следуйте инструкциям по установке на странице [Запуск VSCode в Windows](https://code.visualstudio.com/docs/setup/windows).</span><span class="sxs-lookup"><span data-stu-id="631bd-120">**Windows**: follow the installation instructions on the [Running VSCode on Windows](https://code.visualstudio.com/docs/setup/windows) page</span></span>

2. <span data-ttu-id="631bd-121">Установка расширения PowerShell</span><span class="sxs-lookup"><span data-stu-id="631bd-121">Installing PowerShell Extension</span></span>

   - <span data-ttu-id="631bd-122">Запустите приложение VSCode, выполнив следующие действия.</span><span class="sxs-lookup"><span data-stu-id="631bd-122">Launch the VSCode app by:</span></span>
     - <span data-ttu-id="631bd-123">**Windows**: введите `code` в сеансе PowerShell.</span><span class="sxs-lookup"><span data-stu-id="631bd-123">**Windows**: typing `code` in your PowerShell session</span></span>
     - <span data-ttu-id="631bd-124">**Linux**: введите `code` в терминале.</span><span class="sxs-lookup"><span data-stu-id="631bd-124">**Linux**: typing `code` in your terminal</span></span>
     - <span data-ttu-id="631bd-125">**macOS**: введите `code` в терминале.</span><span class="sxs-lookup"><span data-stu-id="631bd-125">**macOS**: typing `code` in your terminal</span></span>
   - <span data-ttu-id="631bd-126">Запустите **Quick Open**, нажав клавиши <kbd>CTRL</kbd>+<kbd>P</kbd> (<kbd>CMD</kbd>+<kbd>P</kbd> на Mac).</span><span class="sxs-lookup"><span data-stu-id="631bd-126">Launch **Quick Open** by pressing <kbd>Ctrl</kbd>+<kbd>P</kbd> (<kbd>Cmd</kbd>+<kbd>P</kbd> on Mac).</span></span>
   - <span data-ttu-id="631bd-127">В Quick Open введите `ext install powershell` и нажмите клавишу **ВВОД**.</span><span class="sxs-lookup"><span data-stu-id="631bd-127">In Quick Open, type `ext install powershell` and hit **Enter**.</span></span>
   - <span data-ttu-id="631bd-128">На боковой панели открывается представление **Расширения**.</span><span class="sxs-lookup"><span data-stu-id="631bd-128">The **Extensions** view opens on the Side Bar.</span></span> <span data-ttu-id="631bd-129">Выберите расширение PowerShell корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="631bd-129">Select the PowerShell extension from Microsoft.</span></span>
     <span data-ttu-id="631bd-130">Отображается примерно следующее:</span><span class="sxs-lookup"><span data-stu-id="631bd-130">You should see something like below:</span></span>

     ![VSCode](../../images/using-vscode/vscode.png)

   - <span data-ttu-id="631bd-132">Нажмите кнопку **Установить** для расширения PowerShell корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="631bd-132">Click the **Install** button on the PowerShell extension from Microsoft.</span></span>
   - <span data-ttu-id="631bd-133">После установки кнопка **Установить** изменяется на **Перезагрузить**.</span><span class="sxs-lookup"><span data-stu-id="631bd-133">After the install, you see the **Install** button turns to **Reload**.</span></span> <span data-ttu-id="631bd-134">Нажмите кнопку **Перезагрузить**.</span><span class="sxs-lookup"><span data-stu-id="631bd-134">Click on **Reload**.</span></span>
   - <span data-ttu-id="631bd-135">После перезагрузки VSCode можно приступать к редактированию.</span><span class="sxs-lookup"><span data-stu-id="631bd-135">After VSCode has reload, you are ready for editing.</span></span>

<span data-ttu-id="631bd-136">Например, чтобы создать файл, выберите **Файл -> Создать**.</span><span class="sxs-lookup"><span data-stu-id="631bd-136">For example, to create a new file, click **File->New**.</span></span> <span data-ttu-id="631bd-137">Чтобы сохранить его, выберите **Файл -> Сохранить** и укажите имя файла, например `HelloWorld.ps1`.</span><span class="sxs-lookup"><span data-stu-id="631bd-137">To save it, click **File->Save** and then provide a file name, let's say `HelloWorld.ps1`.</span></span> <span data-ttu-id="631bd-138">Чтобы закрыть файл, щелкните "x" рядом с его именем.</span><span class="sxs-lookup"><span data-stu-id="631bd-138">To close the file, click on "x" next to the file name.</span></span> <span data-ttu-id="631bd-139">Чтобы выйти из VSCode, выберите **Файл-> Выход**.</span><span class="sxs-lookup"><span data-stu-id="631bd-139">To exit VSCode, **File->Exit**.</span></span>

### <a name="installing-the-powershell-extension-on-restricted-systems"></a><span data-ttu-id="631bd-140">Установка расширения PowerShell в системах с ограниченным доступом</span><span class="sxs-lookup"><span data-stu-id="631bd-140">Installing the PowerShell Extension on Restricted Systems</span></span>

<span data-ttu-id="631bd-141">Некоторые системы настроены таким образом, что требуется проверка всех подписей кода, и, следовательно, одобрение службы редактора PowerShell вручную для запуска в системе.</span><span class="sxs-lookup"><span data-stu-id="631bd-141">Some systems are set up in a way that requires all code signatures to be checked and thus requires PowerShell Editor Services to be manually approved to run on the system.</span></span> <span data-ttu-id="631bd-142">Обновление групповой политики, которое изменяет политику выполнения, является вероятной причиной того, что после установки расширения PowerShell вы сталкиваетесь со следующей ошибкой.</span><span class="sxs-lookup"><span data-stu-id="631bd-142">A Group Policy update that changes execution policy is a likely cause if you have installed the PowerShell extension but are reaching an error like:</span></span>

```
Language server startup failed.
```

<span data-ttu-id="631bd-143">Чтобы вручную утвердить службы редактора PowerShell и, следовательно, расширение PowerShell для VSCode, откройте командную строку PowerShell и выполните следующий код.</span><span class="sxs-lookup"><span data-stu-id="631bd-143">To manually approve PowerShell Editor Services and thus the PowerShell extension for VSCode open a PowerShell prompt and run:</span></span>

```powershell
Import-Module $HOME\.vscode\extensions\ms-vscode.powershell*\modules\PowerShellEditorServices\PowerShellEditorServices.psd1
```

<span data-ttu-id="631bd-144">Вы увидите подсказку "Не удается проверить издателя. Вы действительно хотите запустить эту программу?"</span><span class="sxs-lookup"><span data-stu-id="631bd-144">You are prompted with "Do you want to run software from this untrusted publisher?"</span></span> <span data-ttu-id="631bd-145">Введите `R` для запуска файла.</span><span class="sxs-lookup"><span data-stu-id="631bd-145">Type `R` to run the file.</span></span> <span data-ttu-id="631bd-146">Затем откройте VSCode и убедитесь, что расширение PowerShell работает правильно.</span><span class="sxs-lookup"><span data-stu-id="631bd-146">Then, open VSCode and check that the PowerShell extension is functioning properly.</span></span> <span data-ttu-id="631bd-147">Если у вас все еще есть проблемы с началом работы, сообщите нам об этом на [GitHub](https://github.com/PowerShell/vscode-powershell/issues).</span><span class="sxs-lookup"><span data-stu-id="631bd-147">If you still have issues getting started, let us know on [GitHub](https://github.com/PowerShell/vscode-powershell/issues).</span></span>

#### <a name="choosing-a-version-of-powershell-to-use-with-the-extension"></a><span data-ttu-id="631bd-148">Выбор версии PowerShell для использования с расширением</span><span class="sxs-lookup"><span data-stu-id="631bd-148">Choosing a version of PowerShell to use with the extension</span></span>

<span data-ttu-id="631bd-149">Благодаря одновременной установке PowerShell Core и Windows PowerShell теперь можно использовать конкретную версию PowerShell с расширением PowerShell.</span><span class="sxs-lookup"><span data-stu-id="631bd-149">With PowerShell Core installing side-by-side with Windows PowerShell, is it now possible to use a particular version of PowerShell with the PowerShell extension.</span></span> <span data-ttu-id="631bd-150">Выберите версию, сделав следующее:</span><span class="sxs-lookup"><span data-stu-id="631bd-150">Use the following these steps to choose the version:</span></span>

1. <span data-ttu-id="631bd-151">Откройте палитру команд (<kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> в Windows и Linux, <kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> в macOS).</span><span class="sxs-lookup"><span data-stu-id="631bd-151">Open the command pallet (<kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> on Windows & Linux, <kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> on macOS).</span></span>
1. <span data-ttu-id="631bd-152">Выполните поиск по слову "Сеанс".</span><span class="sxs-lookup"><span data-stu-id="631bd-152">Search for "Session".</span></span>
1. <span data-ttu-id="631bd-153">Щелкните PowerShell: Show Session Menu (PowerShell: показать меню сеансов).</span><span class="sxs-lookup"><span data-stu-id="631bd-153">Click on "PowerShell: Show Session Menu".</span></span>
1. <span data-ttu-id="631bd-154">Выберите версию PowerShell, которую хотите использовать, в списке, например PowerShell Core.</span><span class="sxs-lookup"><span data-stu-id="631bd-154">Choose the version of PowerShell you want to use from the list - for example, "PowerShell Core".</span></span>

> [!IMPORTANT]
> <span data-ttu-id="631bd-155">Этот компонент проверяет несколько известных расположений в разных операционных системах, чтобы найти расположения установки PowerShell.</span><span class="sxs-lookup"><span data-stu-id="631bd-155">This feature looks at a few well-known paths on different operating systems to discover install locations of PowerShell.</span></span> <span data-ttu-id="631bd-156">Если вы установили PowerShell в нетипичном расположении, оно может первоначально не отобразиться в меню сеансов.</span><span class="sxs-lookup"><span data-stu-id="631bd-156">If you installed PowerShell to a non-typical location, it might not show up initially in the Session Menu.</span></span> <span data-ttu-id="631bd-157">Вы можете расширить меню сеансов, [добавив собственные пользовательские пути](#adding-your-own-powershell-paths-to-the-session-menu), как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="631bd-157">You can extend the session menu by [adding your own custom paths](#adding-your-own-powershell-paths-to-the-session-menu) as described below.</span></span>

>[!NOTE]
> <span data-ttu-id="631bd-158">Есть еще один способ перехода в меню сеансов.</span><span class="sxs-lookup"><span data-stu-id="631bd-158">There is another way to get to the session menu.</span></span> <span data-ttu-id="631bd-159">В правом нижнем углу открытого файла PowerShell в редакторе виден зеленый номер версии.</span><span class="sxs-lookup"><span data-stu-id="631bd-159">When a PowerShell file is open in your editor, you see a green version number in the bottom right.</span></span> <span data-ttu-id="631bd-160">Щелкнув его, вы перейдете в меню сеансов.</span><span class="sxs-lookup"><span data-stu-id="631bd-160">Clicking this version number will bring you to the session menu.</span></span>

##### <a name="adding-your-own-powershell-paths-to-the-session-menu"></a><span data-ttu-id="631bd-161">Добавление собственных путей PowerShell в меню сеансов</span><span class="sxs-lookup"><span data-stu-id="631bd-161">Adding your own PowerShell paths to the session menu</span></span>

<span data-ttu-id="631bd-162">В меню сеансов можно добавить другие пути к исполнимому файлу PowerShell с помощью VSCode.</span><span class="sxs-lookup"><span data-stu-id="631bd-162">You can add other PowerShell executable paths to the session menu through a VSCode setting.</span></span>

<span data-ttu-id="631bd-163">Добавьте элемент в список `powershell.powerShellAdditionalExePaths` или создайте список, если его нет в `settings.json`:</span><span class="sxs-lookup"><span data-stu-id="631bd-163">Add an item to the list `powershell.powerShellAdditionalExePaths` or create the list if it doesn't exist in your `settings.json`:</span></span>

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

<span data-ttu-id="631bd-164">Каждый элемент должен иметь следующее:</span><span class="sxs-lookup"><span data-stu-id="631bd-164">Each item must have:</span></span>

* <span data-ttu-id="631bd-165">`exePath`: Путь к исполняемому файлу `pwsh` или `powershell`.</span><span class="sxs-lookup"><span data-stu-id="631bd-165">`exePath`: The path to the `pwsh` or `powershell` executable.</span></span>
* <span data-ttu-id="631bd-166">`versionName`: Текст, который будет отображаться в меню сеансов.</span><span class="sxs-lookup"><span data-stu-id="631bd-166">`versionName`: The text that will show up in the session menu.</span></span>

<span data-ttu-id="631bd-167">Вы можете задать используемую версию PowerShell по умолчанию, задав параметр `powershell.powerShellDefaultVersion` для текста, отображаемого в меню сеансов (`versionName` в последнем параметре):</span><span class="sxs-lookup"><span data-stu-id="631bd-167">You can set the default PowerShell version to use using the `powershell.powerShellDefaultVersion` setting by setting this to the text displayed in the session menu (aka the `versionName` in the last setting):</span></span>

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

<span data-ttu-id="631bd-168">Задав этот параметр, перезапустите VSCode или используйте действие палитры команд "Developer: Reload Window" (Разработчик: перезагрузить окно) для перезагрузки текущего окна VSCode.</span><span class="sxs-lookup"><span data-stu-id="631bd-168">Once you've set this setting, restart VSCode or use the the "Developer: Reload Window" command pallet action to reload the current VSCode window.</span></span>

<span data-ttu-id="631bd-169">Открыв меню сеансов, вы увидите дополнительные версии PowerShell.</span><span class="sxs-lookup"><span data-stu-id="631bd-169">If you open the session menu, you now see your additional PowerShell versions!</span></span>

> [!NOTE]
> <span data-ttu-id="631bd-170">Если вы создаете PowerShell из исходного кода, это отличный способ протестировать локальную сборку PowerShell.</span><span class="sxs-lookup"><span data-stu-id="631bd-170">If you build PowerShell from source, this is a great way to test out your local build of PowerShell.</span></span>

#### <a name="configuration-settings-for-vscode"></a><span data-ttu-id="631bd-171">Параметры конфигурации VSCode</span><span class="sxs-lookup"><span data-stu-id="631bd-171">Configuration settings for VSCode</span></span>

<span data-ttu-id="631bd-172">Следуя инструкциям в предыдущем абзаце, вы можете добавить параметры конфигурации в `settings.json`.</span><span class="sxs-lookup"><span data-stu-id="631bd-172">By using the steps in the previous paragraph you can add configuration settings in `settings.json`.</span></span>

<span data-ttu-id="631bd-173">Мы рекомендуем использовать следующие параметры конфигурации для VSCode:</span><span class="sxs-lookup"><span data-stu-id="631bd-173">We recommend the following configuration settings for VSCode:</span></span>

```json
{
    "csharp.suppressDotnetRestoreNotification": true,
    "editor.renderWhitespace": "all",
    "editor.renderControlCharacters": true,
    "omnisharp.projectLoadTimeout": 120,
    "files.trimTrailingWhitespace": true,
    "files.encoding": "utf8bom",
    "files.autoGuessEncoding": true
}
```

<span data-ttu-id="631bd-174">Если вы не хотите, чтобы эти параметры влияли на все типы файлов, VSCode также позволяет задавать конфигурации для каждого языка отдельно.</span><span class="sxs-lookup"><span data-stu-id="631bd-174">If you don't want these settings to affect all files types, VSCode also allows per-language configurations.</span></span> <span data-ttu-id="631bd-175">Параметр для конкретного языка можно создать, поместив параметры в поле `[<language-name>]`.</span><span class="sxs-lookup"><span data-stu-id="631bd-175">Create a language specific setting by putting settings in a `[<language-name>]` field.</span></span> <span data-ttu-id="631bd-176">Например:</span><span class="sxs-lookup"><span data-stu-id="631bd-176">For example:</span></span>

```json
"[powershell]": {
    "files.encoding": "utf8bom",
    "files.autoGuessEncoding": true
}
```

<span data-ttu-id="631bd-177">Дополнительные сведения о кодировании файлов в VSCode см. в [этой статье](understanding-file-encoding.md).</span><span class="sxs-lookup"><span data-stu-id="631bd-177">For more information about file encoding in VSCode, see [Understanding file encoding](understanding-file-encoding.md).</span></span>

## <a name="debugging-with-vscode"></a><span data-ttu-id="631bd-178">Отладка с помощью VSCode</span><span class="sxs-lookup"><span data-stu-id="631bd-178">Debugging with VSCode</span></span>

### <a name="no-workspace-debugging"></a><span data-ttu-id="631bd-179">Отладка без рабочей области</span><span class="sxs-lookup"><span data-stu-id="631bd-179">No-workspace debugging</span></span>

<span data-ttu-id="631bd-180">Начиная с VSCode версии 1.9, вы можете отлаживать сценарии PowerShell, не открывая папку со сценарием PowerShell.</span><span class="sxs-lookup"><span data-stu-id="631bd-180">As of VSCode version 1.9 you can debug PowerShell scripts without having to open the folder containing the PowerShell script.</span></span> <span data-ttu-id="631bd-181">Откройте файл сценария PowerShell с помощью команды **Файл -> Открыть файл...** , установите точку останова на строке (нажав клавишу <kbd>F9</kbd>) и нажмите клавишу <kbd>F5</kbd> для запуска отладки.</span><span class="sxs-lookup"><span data-stu-id="631bd-181">Open the PowerShell script file with **File->Open File...**, set a breakpoint on a line (press <kbd>F9</kbd>) and then press <kbd>F5</kbd> to start debugging.</span></span> <span data-ttu-id="631bd-182">Отображается панель действий отладки, позволяющая прервать работу отладчика, возобновить отладку, выполнить ее пошагово или остановить.</span><span class="sxs-lookup"><span data-stu-id="631bd-182">You should see the Debug actions pane appear which allows you to break into the debugger, step, resume and stop debugging.</span></span>

### <a name="workspace-debugging"></a><span data-ttu-id="631bd-183">Отладка с рабочей областью</span><span class="sxs-lookup"><span data-stu-id="631bd-183">Workspace debugging</span></span>

<span data-ttu-id="631bd-184">Отладка с рабочей областью обозначает отладку в контексте папки, которую вы открыли в Visual Studio Code с помощью команды **Открыть папку...** из меню **Файл**.</span><span class="sxs-lookup"><span data-stu-id="631bd-184">Workspace debugging refers to debugging in the context of a folder that you have opened in Visual Studio Code using **Open Folder...** from the **File** menu.</span></span> <span data-ttu-id="631bd-185">Обычно открытая папка является папкой проекта PowerShell и (или) корнем репозитория Git.</span><span class="sxs-lookup"><span data-stu-id="631bd-185">The folder you open is typically your PowerShell project folder and/or the root of your Git repository.</span></span>

<span data-ttu-id="631bd-186">Даже в этом режиме вы можете начать отладку выбранного сценария PowerShell, просто нажав клавишу <kbd>F5</kbd>.</span><span class="sxs-lookup"><span data-stu-id="631bd-186">Even in this mode, you can start debugging the currently selected PowerShell script by simply pressing <kbd>F5</kbd>.</span></span> <span data-ttu-id="631bd-187">Однако отладка с рабочей областью позволяет задать несколько конфигураций отладки, отличных от простой отладки открытого файла.</span><span class="sxs-lookup"><span data-stu-id="631bd-187">However, workspace debugging allows you to define multiple debug configurations other than just debugging the currently open file.</span></span> <span data-ttu-id="631bd-188">Например, можно добавить конфигурации следующего характера:</span><span class="sxs-lookup"><span data-stu-id="631bd-188">For instance, you can add a configurations to:</span></span>

- <span data-ttu-id="631bd-189">Запуск тестов Pester в отладчике</span><span class="sxs-lookup"><span data-stu-id="631bd-189">Launch Pester tests in the debugger</span></span>
- <span data-ttu-id="631bd-190">Запуск определенного файла с аргументами в отладчике</span><span class="sxs-lookup"><span data-stu-id="631bd-190">Launch a specific file with arguments in the debugger</span></span>
- <span data-ttu-id="631bd-191">Запуск интерактивного сеанса в отладчике</span><span class="sxs-lookup"><span data-stu-id="631bd-191">Launch an interactive session in the debugger</span></span>
- <span data-ttu-id="631bd-192">Подключение отладчика к хост-процессу PowerShell</span><span class="sxs-lookup"><span data-stu-id="631bd-192">Attach the debugger to a PowerShell host process</span></span>

<span data-ttu-id="631bd-193">Выполните следующие действия, чтобы создать файл конфигурации отладки:</span><span class="sxs-lookup"><span data-stu-id="631bd-193">Follow these steps to create your debug configuration file:</span></span>

  1. <span data-ttu-id="631bd-194">Откройте представление **Отладка**, нажав клавиши <kbd>CTRL</kbd>+<kbd>SHIFT</kbd>+<kbd>D</kbd> (<kbd>CMD</kbd>+<kbd>SHIFT</kbd>+<kbd>D</kbd> на Mac).</span><span class="sxs-lookup"><span data-stu-id="631bd-194">Open the **Debug** view by pressing <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>D</kbd> (<kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>D</kbd> on Mac).</span></span>
  2. <span data-ttu-id="631bd-195">Щелкните значок с шестеренкой **Настройка** на панели инструментов.</span><span class="sxs-lookup"><span data-stu-id="631bd-195">Click the **Configure** gear icon in the toolbar.</span></span>
  3. <span data-ttu-id="631bd-196">VSCode предлагает вам **выбрать среду**.</span><span class="sxs-lookup"><span data-stu-id="631bd-196">VSCode prompts you to **Select Environment**.</span></span> <span data-ttu-id="631bd-197">Выберите **PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="631bd-197">Choose **PowerShell**.</span></span>

  <span data-ttu-id="631bd-198">При этом VSCode создает каталог и файл ".vscode\launch.json" в корневой папке рабочей области.</span><span class="sxs-lookup"><span data-stu-id="631bd-198">When you do this, VSCode creates a directory and a file ".vscode\launch.json" in the root of your workspace folder.</span></span> <span data-ttu-id="631bd-199">Именно там хранится ваша конфигурация отладки.</span><span class="sxs-lookup"><span data-stu-id="631bd-199">This is where your debug configuration is stored.</span></span> <span data-ttu-id="631bd-200">Если ваши файлы хранятся в репозитории Git, скорее всего, вы захотите зафиксировать файл launch.json.</span><span class="sxs-lookup"><span data-stu-id="631bd-200">If your files are in a Git repository, you typically want to commit the launch.json file.</span></span> <span data-ttu-id="631bd-201">Файла launch.json содержит следующее:</span><span class="sxs-lookup"><span data-stu-id="631bd-201">The contents of the launch.json file are:</span></span>

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

  <span data-ttu-id="631bd-202">Это представляет типичные сценарии отладки.</span><span class="sxs-lookup"><span data-stu-id="631bd-202">This represents the common debug scenarios.</span></span> <span data-ttu-id="631bd-203">Однако при открытии этого файла в редакторе отображается кнопка **Добавить конфигурацию...** .</span><span class="sxs-lookup"><span data-stu-id="631bd-203">However, when you open this file in the editor, you see an **Add Configuration...** button.</span></span> <span data-ttu-id="631bd-204">Можете нажать ее, чтобы добавить дополнительные конфигурации отладки PowerShell.</span><span class="sxs-lookup"><span data-stu-id="631bd-204">You can click this button to add more PowerShell debug configurations.</span></span> <span data-ttu-id="631bd-205">Одной из полезных конфигураций является **PowerShell: Launch Script** (Запустить сценарий).</span><span class="sxs-lookup"><span data-stu-id="631bd-205">One handy configuration to add is **PowerShell: Launch Script**.</span></span> <span data-ttu-id="631bd-206">С помощью этой конфигурации можно указать определенный файл с дополнительными аргументами, которые нужно запускать при каждом нажатии клавиши <kbd>F5</kbd>, независимо от того, какой именно файл активен в редакторе.</span><span class="sxs-lookup"><span data-stu-id="631bd-206">With this configuration, you can specify a specific file with optional arguments that should be launched whenever you press <kbd>F5</kbd> no matter which file is currently active in the editor.</span></span>

  <span data-ttu-id="631bd-207">После задания конфигурации отладки можно указать конфигурацию, используемую во время сеанса отладки, выбрав ее в раскрывающемся списке конфигураций отладки на панели инструментов представления **Отладка**.</span><span class="sxs-lookup"><span data-stu-id="631bd-207">Once the debug configuration is established, you can select which configuration you want to use during a debug session by selecting one from the debug configuration drop-down in the **Debug** view's toolbar.</span></span>

<span data-ttu-id="631bd-208">Существует несколько блогов, которые могут оказаться полезными при начале работы с расширением PowerShell для Visual Studio Code:</span><span class="sxs-lookup"><span data-stu-id="631bd-208">There are a few blogs that may be helpful to get you started using PowerShell extension for Visual Studio Code:</span></span>

- <span data-ttu-id="631bd-209">[Расширение PowerShell][ps-extension]</span><span class="sxs-lookup"><span data-stu-id="631bd-209">[PowerShell Extension][ps-extension]</span></span>
- <span data-ttu-id="631bd-210">[Написание и отладка в сценариев PowerShell в Visual Studio Code][debug]</span><span class="sxs-lookup"><span data-stu-id="631bd-210">[Write and debug PowerShell scripts in Visual Studio Code][debug]</span></span>
- <span data-ttu-id="631bd-211">[Руководство по отладке Visual Studio Code][vscode-guide]</span><span class="sxs-lookup"><span data-stu-id="631bd-211">[Debugging Visual Studio Code Guidance][vscode-guide]</span></span>
- <span data-ttu-id="631bd-212">[Отладка PowerShell в Visual Studio Code][ps-vscode]</span><span class="sxs-lookup"><span data-stu-id="631bd-212">[Debugging PowerShell in Visual Studio Code][ps-vscode]</span></span>
- <span data-ttu-id="631bd-213">[Приступая к разработке PowerShell в Visual Studio Code][getting-started]</span><span class="sxs-lookup"><span data-stu-id="631bd-213">[Get started with PowerShell development in Visual Studio Code][getting-started]</span></span>
- <span data-ttu-id="631bd-214">[Функции редактирования Visual Studio Code для разработки PowerShell. Часть 1][editing-part1]</span><span class="sxs-lookup"><span data-stu-id="631bd-214">[Visual Studio Code editing features for PowerShell development – Part 1][editing-part1]</span></span>
- <span data-ttu-id="631bd-215">[Функции редактирования Visual Studio Code для разработки PowerShell. Часть 2][editing-part2]</span><span class="sxs-lookup"><span data-stu-id="631bd-215">[Visual Studio Code editing features for PowerShell development – Part 2][editing-part2]</span></span>
- <span data-ttu-id="631bd-216">[Отладка сценария PowerShell в Visual Studio Code. Часть 1][debugging-part1]</span><span class="sxs-lookup"><span data-stu-id="631bd-216">[Debugging PowerShell script in Visual Studio Code – Part 1][debugging-part1]</span></span>
- <span data-ttu-id="631bd-217">[Отладка сценария PowerShell в Visual Studio Code. Часть 2][debugging-part2]</span><span class="sxs-lookup"><span data-stu-id="631bd-217">[Debugging PowerShell script in Visual Studio Code – Part 2][debugging-part2]</span></span>

[ise]: ../ise/Introducing-the-Windows-PowerShell-ISE.md
[install-pscore-linux]:  ../../setup/Installing-PowerShell-Core-on-Linux.md
[install-pscore-macos]:  ../../setup/Installing-PowerShell-Core-on-macOS.md
[install-pscore-windows]: ../../setup/Installing-PowerShell-Core-on-Windows.md
[install-winps]: ../../setup/Installing-Windows-PowerShell.md
[ps-extension]: https://blogs.msdn.microsoft.com/cdndevs/2015/12/11/visual-studio-code-powershell-extension/
[debug]: https://blogs.msdn.microsoft.com/powershell/2015/11/16/announcing-powershell-language-support-for-visual-studio-code-and-more/
[vscode-guide]: https://johnpapa.net/debugging-with-visual-studio-code/
[ps-vscode]: https://github.com/PowerShell/vscode-powershell/tree/master/examples
[getting-started]: https://blogs.technet.microsoft.com/heyscriptingguy/2016/12/05/get-started-with-powershell-development-in-visual-studio-code/
[editing-part1]: https://blogs.technet.microsoft.com/heyscriptingguy/2017/01/11/visual-studio-code-editing-features-for-powershell-development-part-1/
[editing-part2]: https://blogs.technet.microsoft.com/heyscriptingguy/2017/01/12/visual-studio-code-editing-features-for-powershell-development-part-2/
[debugging-part1]: https://blogs.technet.microsoft.com/heyscriptingguy/2017/02/06/debugging-powershell-script-in-visual-studio-code-part-1/
[debugging-part2]: https://blogs.technet.microsoft.com/heyscriptingguy/2017/02/13/debugging-powershell-script-in-visual-studio-code-part-2/

## <a name="powershell-extension-for-vscode"></a><span data-ttu-id="631bd-218">Расширение PowerShell для VSCode</span><span class="sxs-lookup"><span data-stu-id="631bd-218">PowerShell Extension for VSCode</span></span>

<span data-ttu-id="631bd-219">Исходный код расширения PowerShell доступен на [GitHub](https://github.com/PowerShell/vscode-powershell).</span><span class="sxs-lookup"><span data-stu-id="631bd-219">The PowerShell extension's source code can be found on [GitHub](https://github.com/PowerShell/vscode-powershell).</span></span>
