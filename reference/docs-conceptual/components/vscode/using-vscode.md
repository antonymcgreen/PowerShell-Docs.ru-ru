---
title: Использование Visual Studio Code для разработки в PowerShell
description: Использование Visual Studio Code для разработки в PowerShell
ms.date: 11/07/2019
ms.openlocfilehash: b083388174dbae4a50da73156d2fce41412613a7
ms.sourcegitcommit: 14b50e5446f69729f72231f5dc6f536cdd1084c3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73933884"
---
# <a name="using-visual-studio-code-for-powershell-development"></a><span data-ttu-id="4c1f6-103">Использование Visual Studio Code для разработки в PowerShell</span><span class="sxs-lookup"><span data-stu-id="4c1f6-103">Using Visual Studio Code for PowerShell Development</span></span>

<span data-ttu-id="4c1f6-104">В дополнение к [интегрированной среде сценариев PowerShell][ise] продукт PowerShell также хорошо поддерживается в Visual Studio Code (VSCode).</span><span class="sxs-lookup"><span data-stu-id="4c1f6-104">In addition to the [PowerShell ISE][ise], PowerShell is also well-supported in Visual Studio Code (VSCode).</span></span> <span data-ttu-id="4c1f6-105">Кроме того, интегрированная среда сценариев не поддерживается в PowerShell Core, хотя VSCode поддерживается для PowerShell Core на всех платформах: Windows, macOS и Linux.</span><span class="sxs-lookup"><span data-stu-id="4c1f6-105">The ISE isn't supported with PowerShell Core, but VSCode is supported for PowerShell Core on all platforms: Windows, macOS, and Linux.</span></span>

<span data-ttu-id="4c1f6-106">Вы можете использовать VSCode для Windows вместе с PowerShell версии 5 в Windows 10 или установить Windows Management Framework 5.1 для более низких версий Windows, например Windows 8.1.</span><span class="sxs-lookup"><span data-stu-id="4c1f6-106">You can use VSCode on Windows with PowerShell version 5 by using Windows 10 or by installing Windows Management Framework 5.1 for down-level Windows OSs such as Windows 8.1.</span></span> <span data-ttu-id="4c1f6-107">Дополнительные сведения см. в статье [Установка и настройка WMF 5.1](/powershell/scripting/wmf/setup/install-configure).</span><span class="sxs-lookup"><span data-stu-id="4c1f6-107">For more information, see [Install and Configure WMF 5.1](/powershell/scripting/wmf/setup/install-configure).</span></span>

<span data-ttu-id="4c1f6-108">Перед запуском убедитесь, что оболочка PowerShell установлена в системе.</span><span class="sxs-lookup"><span data-stu-id="4c1f6-108">Before you begin, make sure PowerShell exists on your system.</span></span> <span data-ttu-id="4c1f6-109">Сведения о современных рабочих нагрузках для Windows, macOS и Linux см. по следующим ссылкам:</span><span class="sxs-lookup"><span data-stu-id="4c1f6-109">For modern workloads on Windows, macOS, and Linux, see the following links:</span></span>

- <span data-ttu-id="4c1f6-110">[Установка PowerShell Core в Linux][install-pscore-linux]</span><span class="sxs-lookup"><span data-stu-id="4c1f6-110">[Installing PowerShell Core on Linux][install-pscore-linux]</span></span>
- <span data-ttu-id="4c1f6-111">[Установка PowerShell Core в macOS][install-pscore-macos]</span><span class="sxs-lookup"><span data-stu-id="4c1f6-111">[Installing PowerShell Core on macOS][install-pscore-macos]</span></span>
- <span data-ttu-id="4c1f6-112">[Установка PowerShell Core в Windows][install-pscore-windows]</span><span class="sxs-lookup"><span data-stu-id="4c1f6-112">[Installing PowerShell Core on Windows][install-pscore-windows]</span></span>

<span data-ttu-id="4c1f6-113">Сведения о традиционных рабочих нагрузках Windows PowerShell см. в разделе [Установка Windows PowerShell][install-winps].</span><span class="sxs-lookup"><span data-stu-id="4c1f6-113">For traditional Windows PowerShell workloads, see [Installing Windows PowerShell][install-winps].</span></span>

## <a name="editing-with-vscode"></a><span data-ttu-id="4c1f6-114">Редактирование с помощью VSCode</span><span class="sxs-lookup"><span data-stu-id="4c1f6-114">Editing with VSCode</span></span>

1. <span data-ttu-id="4c1f6-115">Установите VSCode.</span><span class="sxs-lookup"><span data-stu-id="4c1f6-115">Install VSCode.</span></span> <span data-ttu-id="4c1f6-116">Дополнительные сведения см. в статье [Setting up Visual Studio Code](https://code.visualstudio.com/Docs/setup/setup-overview) (Настройка Visual Studio Code).</span><span class="sxs-lookup"><span data-stu-id="4c1f6-116">For more information, see the overview [Setting up Visual Studio Code](https://code.visualstudio.com/Docs/setup/setup-overview).</span></span>

   <span data-ttu-id="4c1f6-117">Доступны инструкции по установке на каждой платформе:</span><span class="sxs-lookup"><span data-stu-id="4c1f6-117">There are installation instructions for each platform:</span></span>

   - <span data-ttu-id="4c1f6-118">**Linux**: следуйте инструкциям по установке на странице [Visual Studio Code on Linux](https://code.visualstudio.com/docs/setup/linux) (Visual Studio Code в Linux).</span><span class="sxs-lookup"><span data-stu-id="4c1f6-118">**Linux**: follow the installation instructions on the [Running VSCode on Linux](https://code.visualstudio.com/docs/setup/linux) page.</span></span>
   - <span data-ttu-id="4c1f6-119">**macOS**: следуйте инструкциям по установке на странице [Visual Studio Code on macOS](https://code.visualstudio.com/docs/setup/mac) (Visual Studio Code в macOS).</span><span class="sxs-lookup"><span data-stu-id="4c1f6-119">**macOS**: follow the installation instructions on the [Running VSCode on macOS](https://code.visualstudio.com/docs/setup/mac) page.</span></span>

     > [!IMPORTANT]
     > <span data-ttu-id="4c1f6-120">В macOS нужно установить OpenSSL для правильной работы расширения PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4c1f6-120">On macOS, you must install OpenSSL for the PowerShell extension to work correctly.</span></span> <span data-ttu-id="4c1f6-121">Для этого проще всего установить [Homebrew](https://brew.sh/), а затем запустить `brew install openssl`.</span><span class="sxs-lookup"><span data-stu-id="4c1f6-121">The easiest way to accomplish this is to install [Homebrew](https://brew.sh/) and then run `brew install openssl`.</span></span> <span data-ttu-id="4c1f6-122">Теперь VSCode сможет загрузить расширение PowerShell правильно.</span><span class="sxs-lookup"><span data-stu-id="4c1f6-122">VSCode can now load the PowerShell extension successfully.</span></span>

   - <span data-ttu-id="4c1f6-123">**Windows**: следуйте инструкциям по установке на странице [Visual Studio Code on Windows](https://code.visualstudio.com/docs/setup/windows) (Visual Studio Code в Windows).</span><span class="sxs-lookup"><span data-stu-id="4c1f6-123">**Windows**: follow the installation instructions on the [Running VSCode on Windows](https://code.visualstudio.com/docs/setup/windows) page.</span></span>

1. <span data-ttu-id="4c1f6-124">Установите расширение PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4c1f6-124">Install the PowerShell Extension.</span></span>

   1. <span data-ttu-id="4c1f6-125">Запустите приложение VSCode, выполнив следующие действия.</span><span class="sxs-lookup"><span data-stu-id="4c1f6-125">Launch the VSCode app by:</span></span>
      - <span data-ttu-id="4c1f6-126">**Windows**: введите `code` в сеансе PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4c1f6-126">**Windows**: typing `code` in your PowerShell session</span></span>
      - <span data-ttu-id="4c1f6-127">**Linux**: введите `code` в терминале.</span><span class="sxs-lookup"><span data-stu-id="4c1f6-127">**Linux**: typing `code` in your terminal</span></span>
      - <span data-ttu-id="4c1f6-128">**macOS**: введите `code` в терминале.</span><span class="sxs-lookup"><span data-stu-id="4c1f6-128">**macOS**: typing `code` in your terminal</span></span>
   1. <span data-ttu-id="4c1f6-129">Запустите **Quick Open** в Windows или Linux, нажав клавиши <kbd>CTRL</kbd>+<kbd>P</kbd>.</span><span class="sxs-lookup"><span data-stu-id="4c1f6-129">Launch **Quick Open** on Windows or Linux by pressing <kbd>Ctrl</kbd>+<kbd>P</kbd>.</span></span> <span data-ttu-id="4c1f6-130">В macOS нажмите клавиши <kbd>CMD</kbd>+<kbd>P</kbd>.</span><span class="sxs-lookup"><span data-stu-id="4c1f6-130">On macOS, press <kbd>Cmd</kbd>+<kbd>P</kbd>.</span></span>
   1. <span data-ttu-id="4c1f6-131">В Quick Open введите `ext install powershell` и нажмите клавишу **ВВОД**.</span><span class="sxs-lookup"><span data-stu-id="4c1f6-131">In Quick Open, type `ext install powershell` and press **Enter**.</span></span>
   1. <span data-ttu-id="4c1f6-132">На боковой панели открывается представление **Расширения**.</span><span class="sxs-lookup"><span data-stu-id="4c1f6-132">The **Extensions** view opens on the Side Bar.</span></span> <span data-ttu-id="4c1f6-133">Выберите расширение PowerShell корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="4c1f6-133">Select the PowerShell extension from Microsoft.</span></span>
      <span data-ttu-id="4c1f6-134">Откроется примерно следующий экран VSCode:</span><span class="sxs-lookup"><span data-stu-id="4c1f6-134">You should see a VSCode screen similar to the following image:</span></span>

      ![VSCode](../../images/using-vscode/vscode.png)

   1. <span data-ttu-id="4c1f6-136">Нажмите кнопку **Установить** для расширения PowerShell корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="4c1f6-136">Click the **Install** button on the PowerShell extension from Microsoft.</span></span>
   1. <span data-ttu-id="4c1f6-137">После установки кнопка **Установить** изменяется на **Перезагрузить**.</span><span class="sxs-lookup"><span data-stu-id="4c1f6-137">After the install, you see the **Install** button turns to **Reload**.</span></span> <span data-ttu-id="4c1f6-138">Нажмите кнопку **Перезагрузить**.</span><span class="sxs-lookup"><span data-stu-id="4c1f6-138">Click on **Reload**.</span></span>
   1. <span data-ttu-id="4c1f6-139">После перезагрузки VSCode можно приступать к редактированию.</span><span class="sxs-lookup"><span data-stu-id="4c1f6-139">After VSCode has reloaded, you're ready for editing.</span></span>

<span data-ttu-id="4c1f6-140">Например, чтобы создать файл, выберите **Файл > Создать**.</span><span class="sxs-lookup"><span data-stu-id="4c1f6-140">For example, to create a new file, click **File > New**.</span></span> <span data-ttu-id="4c1f6-141">Чтобы сохранить его, выберите **Файл > Сохранить** и укажите имя файла, например `HelloWorld.ps1`.</span><span class="sxs-lookup"><span data-stu-id="4c1f6-141">To save it, click **File > Save** and then provide a file name, such as `HelloWorld.ps1`.</span></span> <span data-ttu-id="4c1f6-142">Чтобы закрыть файл, щелкните `X` рядом с его именем.</span><span class="sxs-lookup"><span data-stu-id="4c1f6-142">To close the file, click the `X` next to the file name.</span></span> <span data-ttu-id="4c1f6-143">Чтобы выйти из VSCode, выберите **Файл > Выход**.</span><span class="sxs-lookup"><span data-stu-id="4c1f6-143">To exit VSCode, **File > Exit**.</span></span>

### <a name="installing-the-powershell-extension-on-restricted-systems"></a><span data-ttu-id="4c1f6-144">Установка расширения PowerShell в системах с ограниченным доступом</span><span class="sxs-lookup"><span data-stu-id="4c1f6-144">Installing the PowerShell Extension on Restricted Systems</span></span>

<span data-ttu-id="4c1f6-145">Некоторые системы настроены таким образом, что требуется проверка всех подписей кода и, следовательно, одобрение службы редактора PowerShell вручную для запуска в системе.</span><span class="sxs-lookup"><span data-stu-id="4c1f6-145">Some systems are set up in a way that requires all code signatures to be checked and requires PowerShell Editor Services to be manually approved to run on the system.</span></span> <span data-ttu-id="4c1f6-146">Обновление групповой политики, которое изменяет политику выполнения, является вероятной причиной того, что после установки расширения PowerShell вы сталкиваетесь со следующей ошибкой:</span><span class="sxs-lookup"><span data-stu-id="4c1f6-146">A Group Policy update that changes execution policy is a likely cause if you've installed the PowerShell extension but are receiving an error such as:</span></span>

```
Language server startup failed.
```

<span data-ttu-id="4c1f6-147">Чтобы вручную утвердить службы редактора PowerShell и, следовательно, расширение PowerShell для VSCode, откройте командную строку PowerShell и выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="4c1f6-147">To manually approve PowerShell Editor Services and the PowerShell extension for VSCode, open a PowerShell prompt and run the following command:</span></span>

```powershell
Import-Module $HOME\.vscode\extensions\ms-vscode.powershell*\modules\PowerShellEditorServices\PowerShellEditorServices.psd1
```

<span data-ttu-id="4c1f6-148">Вы увидите подсказку **Не удается проверить издателя. Вы действительно хотите запустить эту программу?**</span><span class="sxs-lookup"><span data-stu-id="4c1f6-148">You're prompted with **Do you want to run software from this untrusted publisher?**</span></span> <span data-ttu-id="4c1f6-149">Введите `A` для запуска файла.</span><span class="sxs-lookup"><span data-stu-id="4c1f6-149">Type `A` to run the file.</span></span> <span data-ttu-id="4c1f6-150">Затем откройте VSCode и убедитесь, что расширение PowerShell работает правильно.</span><span class="sxs-lookup"><span data-stu-id="4c1f6-150">Then, open VSCode and check that the PowerShell extension is functioning properly.</span></span> <span data-ttu-id="4c1f6-151">Если у вас все еще есть проблемы с началом работы, сообщите нам об этом на [GitHub](https://github.com/PowerShell/vscode-powershell/issues).</span><span class="sxs-lookup"><span data-stu-id="4c1f6-151">If you still have issues getting started, let us know on [GitHub](https://github.com/PowerShell/vscode-powershell/issues).</span></span>

### <a name="choosing-a-version-of-powershell-to-use-with-the-extension"></a><span data-ttu-id="4c1f6-152">Выбор версии PowerShell для использования с расширением</span><span class="sxs-lookup"><span data-stu-id="4c1f6-152">Choosing a version of PowerShell to use with the extension</span></span>

<span data-ttu-id="4c1f6-153">Благодаря одновременной установке PowerShell Core и Windows PowerShell теперь можно использовать конкретную версию PowerShell с расширением PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4c1f6-153">With PowerShell Core installing side-by-side with Windows PowerShell, it's now possible to use a particular version of PowerShell with the PowerShell extension.</span></span> <span data-ttu-id="4c1f6-154">Выберите версию, сделав следующее:</span><span class="sxs-lookup"><span data-stu-id="4c1f6-154">Use the following steps to choose the version:</span></span>

1. <span data-ttu-id="4c1f6-155">Откройте **палитру команд** в Windows и Linux (<kbd>CTRL</kbd>+<kbd>SHIFT</kbd>+<kbd>P</kbd>).</span><span class="sxs-lookup"><span data-stu-id="4c1f6-155">Open the **Command Palette** on Windows or Linux with <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd>.</span></span> <span data-ttu-id="4c1f6-156">В macOS нажмите клавиши <kbd>CMD</kbd>+<kbd>SHIFT</kbd>+<kbd>P</kbd>.</span><span class="sxs-lookup"><span data-stu-id="4c1f6-156">On macOS, use <kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd>.</span></span>
1. <span data-ttu-id="4c1f6-157">Выполните поиск по слову **Сеанс**.</span><span class="sxs-lookup"><span data-stu-id="4c1f6-157">Search for **Session**.</span></span>
1. <span data-ttu-id="4c1f6-158">Щелкните **PowerShell: Show Session Menu** (PowerShell: показать меню сеансов).</span><span class="sxs-lookup"><span data-stu-id="4c1f6-158">Click on **PowerShell: Show Session Menu**.</span></span>
1. <span data-ttu-id="4c1f6-159">Выберите версию PowerShell, которую хотите использовать, из списка, например **PowerShell Core**.</span><span class="sxs-lookup"><span data-stu-id="4c1f6-159">Choose the version of PowerShell you want to use from the list, for example: **PowerShell Core**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4c1f6-160">Этот компонент проверяет несколько известных расположений в разных операционных системах, чтобы найти расположения установки PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4c1f6-160">This feature looks at a few well-known paths on different operating systems to discover install locations of PowerShell.</span></span> <span data-ttu-id="4c1f6-161">Если вы установили PowerShell в нетипичном расположении, оно может первоначально не отобразиться в меню сеансов.</span><span class="sxs-lookup"><span data-stu-id="4c1f6-161">If you installed PowerShell to a non-typical location, it might not show up initially in the Session Menu.</span></span> <span data-ttu-id="4c1f6-162">Вы можете расширить меню сеансов, [добавив собственные пользовательские пути](#adding-your-own-powershell-paths-to-the-session-menu), как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="4c1f6-162">You can extend the session menu by [adding your own custom paths](#adding-your-own-powershell-paths-to-the-session-menu) as described below.</span></span>

>[!NOTE]
> <span data-ttu-id="4c1f6-163">Есть еще один способ перехода в меню сеансов.</span><span class="sxs-lookup"><span data-stu-id="4c1f6-163">There's another way to get to the session menu.</span></span> <span data-ttu-id="4c1f6-164">В правом нижнем углу открытого файла PowerShell в редакторе виден зеленый номер версии.</span><span class="sxs-lookup"><span data-stu-id="4c1f6-164">When a PowerShell file is open in your editor, you see a green version number in the bottom right.</span></span> <span data-ttu-id="4c1f6-165">Щелкнув его, вы перейдете в меню сеансов.</span><span class="sxs-lookup"><span data-stu-id="4c1f6-165">Clicking this version number will bring you to the session menu.</span></span>

### <a name="adding-your-own-powershell-paths-to-the-session-menu"></a><span data-ttu-id="4c1f6-166">Добавление собственных путей PowerShell в меню сеансов</span><span class="sxs-lookup"><span data-stu-id="4c1f6-166">Adding your own PowerShell paths to the session menu</span></span>

<span data-ttu-id="4c1f6-167">В меню сеансов можно добавить другие пути к исполнимому файлу PowerShell с помощью VSCode.</span><span class="sxs-lookup"><span data-stu-id="4c1f6-167">You can add other PowerShell executable paths to the session menu through a VSCode setting.</span></span>

<span data-ttu-id="4c1f6-168">Добавьте элемент в список `powershell.powerShellAdditionalExePaths` или создайте список, если его нет в `settings.json`:</span><span class="sxs-lookup"><span data-stu-id="4c1f6-168">Add an item to the list `powershell.powerShellAdditionalExePaths` or create the list if it doesn't exist in your `settings.json`:</span></span>

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

<span data-ttu-id="4c1f6-169">Каждый элемент должен иметь следующее:</span><span class="sxs-lookup"><span data-stu-id="4c1f6-169">Each item must have:</span></span>

* <span data-ttu-id="4c1f6-170">`exePath`: Путь к исполняемому файлу `pwsh` или `powershell`.</span><span class="sxs-lookup"><span data-stu-id="4c1f6-170">`exePath`: The path to the `pwsh` or `powershell` executable.</span></span>
* <span data-ttu-id="4c1f6-171">`versionName`: Текст, который будет отображаться в меню сеансов.</span><span class="sxs-lookup"><span data-stu-id="4c1f6-171">`versionName`: The text that will show up in the session menu.</span></span>

<span data-ttu-id="4c1f6-172">Вы можете задать используемую версию PowerShell по умолчанию, задав параметр `powershell.powerShellDefaultVersion` для текста, отображаемого в меню сеансов (`versionName` в последнем параметре):</span><span class="sxs-lookup"><span data-stu-id="4c1f6-172">You can set the default PowerShell version to use the `powershell.powerShellDefaultVersion` setting by setting this to the text displayed in the session menu (also known as the `versionName` in the last setting):</span></span>

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

<span data-ttu-id="4c1f6-173">Задав этот параметр, перезапустите VSCode или перезагрузите текущее окно VSCode с помощью действия **палитры команд** **Developer: Reload Window** (Разработчик: перезагрузить окно).</span><span class="sxs-lookup"><span data-stu-id="4c1f6-173">After you've configured this setting, restart VSCode or to reload the current VSCode window from the **Command Palette**, type **Developer: Reload Window**.</span></span>

<span data-ttu-id="4c1f6-174">Открыв меню сеансов, вы увидите дополнительные версии PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4c1f6-174">If you open the session menu, you now see your additional PowerShell versions!</span></span>

> [!NOTE]
> <span data-ttu-id="4c1f6-175">Если вы создаете PowerShell из исходного кода, это отличный способ протестировать локальную сборку PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4c1f6-175">If you build PowerShell from source, this is a great way to test out your local build of PowerShell.</span></span>

### <a name="configuration-settings-for-vscode"></a><span data-ttu-id="4c1f6-176">Параметры конфигурации VSCode</span><span class="sxs-lookup"><span data-stu-id="4c1f6-176">Configuration settings for VSCode</span></span>

<span data-ttu-id="4c1f6-177">Следуя инструкциям в предыдущем абзаце, вы можете добавить параметры конфигурации в `settings.json`.</span><span class="sxs-lookup"><span data-stu-id="4c1f6-177">By using the steps in the previous paragraph, you can add configuration settings in `settings.json`.</span></span>

<span data-ttu-id="4c1f6-178">Мы рекомендуем использовать следующие параметры конфигурации для VSCode:</span><span class="sxs-lookup"><span data-stu-id="4c1f6-178">We recommend the following configuration settings for VSCode:</span></span>

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

<span data-ttu-id="4c1f6-179">Если вы не хотите, чтобы эти параметры влияли на все типы файлов, VSCode также позволяет задавать конфигурации для каждого языка отдельно.</span><span class="sxs-lookup"><span data-stu-id="4c1f6-179">If you don't want these settings to affect all files types, VSCode also allows per-language configurations.</span></span> <span data-ttu-id="4c1f6-180">Создать параметр для конкретного языка можно, поместив параметры в поле `[<language-name>]`.</span><span class="sxs-lookup"><span data-stu-id="4c1f6-180">Create a language-specific setting by putting settings in a `[<language-name>]` field.</span></span> <span data-ttu-id="4c1f6-181">Например:</span><span class="sxs-lookup"><span data-stu-id="4c1f6-181">For example:</span></span>

```json
"[powershell]": {
    "files.encoding": "utf8bom",
    "files.autoGuessEncoding": true
}
```

<span data-ttu-id="4c1f6-182">Дополнительные сведения о кодировании файлов в VSCode см. в [этой статье](understanding-file-encoding.md).</span><span class="sxs-lookup"><span data-stu-id="4c1f6-182">For more information about file encoding in VSCode, see [Understanding file encoding](understanding-file-encoding.md).</span></span>

## <a name="debugging-with-vscode"></a><span data-ttu-id="4c1f6-183">Отладка с помощью VSCode</span><span class="sxs-lookup"><span data-stu-id="4c1f6-183">Debugging with VSCode</span></span>

### <a name="no-workspace-debugging"></a><span data-ttu-id="4c1f6-184">Отладка без рабочей области</span><span class="sxs-lookup"><span data-stu-id="4c1f6-184">No-workspace debugging</span></span>

<span data-ttu-id="4c1f6-185">Начиная с VSCode версии 1.9, вы можете отлаживать сценарии PowerShell, не открывая папку со сценарием PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4c1f6-185">As of VSCode version 1.9 you can debug PowerShell scripts without opening the folder that contains the PowerShell script.</span></span> <span data-ttu-id="4c1f6-186">Откройте файл сценария PowerShell с помощью команды **Файл > Открыть файл...** , установите точку останова на строке, нажмите клавишу <kbd>F9</kbd>, а затем — клавишу <kbd>F5</kbd> для запуска отладки.</span><span class="sxs-lookup"><span data-stu-id="4c1f6-186">Open the PowerShell script file with **File > Open File...**, set a breakpoint on a line, press <kbd>F9</kbd>, and then press <kbd>F5</kbd> to start debugging.</span></span> <span data-ttu-id="4c1f6-187">Откроется панель действий отладки, позволяющая прервать работу отладчика, возобновить отладку, выполнить ее пошагово или остановить.</span><span class="sxs-lookup"><span data-stu-id="4c1f6-187">You should see the Debug actions pane appear which allows you to break into the debugger, step, resume, and stop debugging.</span></span>

### <a name="workspace-debugging"></a><span data-ttu-id="4c1f6-188">Отладка с рабочей областью</span><span class="sxs-lookup"><span data-stu-id="4c1f6-188">Workspace debugging</span></span>

<span data-ttu-id="4c1f6-189">Отладка с рабочей областью обозначает отладку в контексте папки, которую вы открыли в Visual Studio Code с помощью команды **Открыть папку...** из меню **Файл**. Обычно открытая папка является папкой проекта PowerShell и (или) корнем репозитория Git.</span><span class="sxs-lookup"><span data-stu-id="4c1f6-189">Workspace debugging refers to debugging in the context of a folder that you've opened in Visual Studio Code from the **File** menu using **Open Folder...**. The folder you open is typically your PowerShell project folder and/or the root of your Git repository.</span></span>

<span data-ttu-id="4c1f6-190">Даже в этом режиме вы можете начать отладку выбранного сценария PowerShell, нажав клавишу <kbd>F5</kbd>.</span><span class="sxs-lookup"><span data-stu-id="4c1f6-190">Even in this mode, you can start debugging the currently selected PowerShell script by pressing <kbd>F5</kbd>.</span></span> <span data-ttu-id="4c1f6-191">Однако отладка с рабочей областью позволяет задать несколько конфигураций отладки, отличных от простой отладки открытого файла.</span><span class="sxs-lookup"><span data-stu-id="4c1f6-191">However, workspace debugging allows you to define multiple debug configurations other than just debugging the currently open file.</span></span> <span data-ttu-id="4c1f6-192">Например, можно добавить конфигурацию следующего характера:</span><span class="sxs-lookup"><span data-stu-id="4c1f6-192">For instance, you can add a configuration to:</span></span>

- <span data-ttu-id="4c1f6-193">Запуск тестов Pester в отладчике.</span><span class="sxs-lookup"><span data-stu-id="4c1f6-193">Launch Pester tests in the debugger.</span></span>
- <span data-ttu-id="4c1f6-194">Запуск определенного файла с аргументами в отладчике.</span><span class="sxs-lookup"><span data-stu-id="4c1f6-194">Launch a specific file with arguments in the debugger.</span></span>
- <span data-ttu-id="4c1f6-195">Запуск интерактивного сеанса в отладчике.</span><span class="sxs-lookup"><span data-stu-id="4c1f6-195">Launch an interactive session in the debugger.</span></span>
- <span data-ttu-id="4c1f6-196">Подключение отладчика к хост-процессу PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4c1f6-196">Attach the debugger to a PowerShell host process.</span></span>

<span data-ttu-id="4c1f6-197">Выполните следующие действия, чтобы создать файл конфигурации отладки:</span><span class="sxs-lookup"><span data-stu-id="4c1f6-197">Follow these steps to create your debug configuration file:</span></span>

  1. <span data-ttu-id="4c1f6-198">Откройте представление **Отладка** в Windows или Linux (<kbd>CTRL</kbd>+<kbd>SHIFT</kbd>+<kbd>D</kbd>).</span><span class="sxs-lookup"><span data-stu-id="4c1f6-198">Open the **Debug** view on Windows or Linux by pressing <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>D</kbd>.</span></span> <span data-ttu-id="4c1f6-199">В macOS нажмите клавиши <kbd>CMD</kbd>+<kbd>SHIFT</kbd>+<kbd>D</kbd>.</span><span class="sxs-lookup"><span data-stu-id="4c1f6-199">On macOS, press <kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>D</kbd>.</span></span>
  1. <span data-ttu-id="4c1f6-200">Щелкните значок с шестеренкой **Настройка** на панели инструментов.</span><span class="sxs-lookup"><span data-stu-id="4c1f6-200">Click the **Configure** gear icon in the toolbar.</span></span>
  1. <span data-ttu-id="4c1f6-201">VSCode предлагает вам **выбрать среду**.</span><span class="sxs-lookup"><span data-stu-id="4c1f6-201">VSCode prompts you to **Select Environment**.</span></span> <span data-ttu-id="4c1f6-202">Выберите **PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="4c1f6-202">Choose **PowerShell**.</span></span>

<span data-ttu-id="4c1f6-203">В результате VSCode создает каталог и файл `.vscode\launch.json` в корневой папке рабочей области.</span><span class="sxs-lookup"><span data-stu-id="4c1f6-203">The result is that VSCode creates a directory and a file `.vscode\launch.json` in the root of your workspace folder.</span></span> <span data-ttu-id="4c1f6-204">Именно там хранится ваша конфигурация отладки.</span><span class="sxs-lookup"><span data-stu-id="4c1f6-204">This location is where your debug configuration is stored.</span></span> <span data-ttu-id="4c1f6-205">Если ваши файлы хранятся в репозитории Git, скорее всего, вы захотите зафиксировать файл `launch.json`.</span><span class="sxs-lookup"><span data-stu-id="4c1f6-205">If your files are in a Git repository, you typically want to commit the `launch.json` file.</span></span> <span data-ttu-id="4c1f6-206">Содержимое файла `launch.json`:</span><span class="sxs-lookup"><span data-stu-id="4c1f6-206">The contents of the `launch.json` file are:</span></span>

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

<span data-ttu-id="4c1f6-207">Этот файл представляет типичные сценарии отладки.</span><span class="sxs-lookup"><span data-stu-id="4c1f6-207">This file represents the common debug scenarios.</span></span> <span data-ttu-id="4c1f6-208">При открытии его в редакторе отображается кнопка **Добавить конфигурацию...**</span><span class="sxs-lookup"><span data-stu-id="4c1f6-208">When you open this file in the editor, you see an **Add Configuration...** button.</span></span> <span data-ttu-id="4c1f6-209">Можете нажать ее, чтобы добавить дополнительные конфигурации отладки PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4c1f6-209">You can click this button to add more PowerShell debug configurations.</span></span> <span data-ttu-id="4c1f6-210">Одной из полезных конфигураций является **PowerShell: Launch Script** (Запустить сценарий).</span><span class="sxs-lookup"><span data-stu-id="4c1f6-210">One useful configuration to add is **PowerShell: Launch Script**.</span></span> <span data-ttu-id="4c1f6-211">С помощью этой конфигурации можно указать файл с дополнительными аргументами, которые нужно запускать при каждом нажатии клавиши <kbd>F5</kbd>, независимо от того, какой именно файл активен в редакторе.</span><span class="sxs-lookup"><span data-stu-id="4c1f6-211">With this configuration, you can specify a file with optional arguments that should be launched whenever you press <kbd>F5</kbd> no matter which file is currently active in the editor.</span></span>

<span data-ttu-id="4c1f6-212">После задания конфигурации отладки вы можете указать конфигурацию, используемую во время сеанса отладки,</span><span class="sxs-lookup"><span data-stu-id="4c1f6-212">After the debug configuration is established, you can select which configuration you want to use during a debug session.</span></span> <span data-ttu-id="4c1f6-213">выбрав ее в раскрывающемся списке конфигураций отладки на панели инструментов представления **Отладка**.</span><span class="sxs-lookup"><span data-stu-id="4c1f6-213">Select a configuration from the debug configuration drop-down in the **Debug** view's toolbar.</span></span>

<span data-ttu-id="4c1f6-214">Существует несколько блогов, которые могут оказаться полезными при начале работы с расширением PowerShell для Visual Studio Code:</span><span class="sxs-lookup"><span data-stu-id="4c1f6-214">There are a few blogs that may be helpful to get you started using PowerShell extension for Visual Studio Code:</span></span>

- <span data-ttu-id="4c1f6-215">[Расширение PowerShell][ps-extension]</span><span class="sxs-lookup"><span data-stu-id="4c1f6-215">[PowerShell Extension][ps-extension]</span></span>
- <span data-ttu-id="4c1f6-216">[Написание и отладка в сценариев PowerShell в Visual Studio Code][debug]</span><span class="sxs-lookup"><span data-stu-id="4c1f6-216">[Write and debug PowerShell scripts in Visual Studio Code][debug]</span></span>
- <span data-ttu-id="4c1f6-217">[Руководство по отладке Visual Studio Code][vscode-guide]</span><span class="sxs-lookup"><span data-stu-id="4c1f6-217">[Debugging Visual Studio Code Guidance][vscode-guide]</span></span>
- <span data-ttu-id="4c1f6-218">[Отладка PowerShell в Visual Studio Code][ps-vscode]</span><span class="sxs-lookup"><span data-stu-id="4c1f6-218">[Debugging PowerShell in Visual Studio Code][ps-vscode]</span></span>
- <span data-ttu-id="4c1f6-219">[Приступая к разработке PowerShell в Visual Studio Code][getting-started]</span><span class="sxs-lookup"><span data-stu-id="4c1f6-219">[Get started with PowerShell development in Visual Studio Code][getting-started]</span></span>
- <span data-ttu-id="4c1f6-220">[Функции редактирования Visual Studio Code для разработки PowerShell. Часть 1][editing-part1]</span><span class="sxs-lookup"><span data-stu-id="4c1f6-220">[Visual Studio Code editing features for PowerShell development – Part 1][editing-part1]</span></span>
- <span data-ttu-id="4c1f6-221">[Функции редактирования Visual Studio Code для разработки PowerShell. Часть 2][editing-part2]</span><span class="sxs-lookup"><span data-stu-id="4c1f6-221">[Visual Studio Code editing features for PowerShell development – Part 2][editing-part2]</span></span>
- <span data-ttu-id="4c1f6-222">[Отладка сценария PowerShell в Visual Studio Code. Часть 1][debugging-part1]</span><span class="sxs-lookup"><span data-stu-id="4c1f6-222">[Debugging PowerShell script in Visual Studio Code – Part 1][debugging-part1]</span></span>
- <span data-ttu-id="4c1f6-223">[Отладка сценария PowerShell в Visual Studio Code. Часть 2][debugging-part2]</span><span class="sxs-lookup"><span data-stu-id="4c1f6-223">[Debugging PowerShell script in Visual Studio Code – Part 2][debugging-part2]</span></span>

[ise]: ../ise/Introducing-the-Windows-PowerShell-ISE.md
[install-pscore-linux]:  ../../setup/Installing-PowerShell-Core-on-Linux.md
[install-pscore-macos]:  ../../setup/Installing-PowerShell-Core-on-macOS.md
[install-pscore-windows]: ../../setup/Installing-PowerShell-Core-on-Windows.md
[install-winps]: ../../setup/Installing-Windows-PowerShell.md
[ps-extension]: https://blogs.msdn.microsoft.com/cdndevs/2015/12/11/visual-studio-code-powershell-extension/
[debug]: https://devblogs.microsoft.com/powershell/announcing-powershell-language-support-for-visual-studio-code-and-more/
[vscode-guide]: https://johnpapa.net/debugging-with-visual-studio-code/
[ps-vscode]: https://github.com/PowerShell/vscode-powershell/tree/master/examples
[getting-started]: https://devblogs.microsoft.com/scripting/get-started-with-powershell-development-in-visual-studio-code/
[editing-part1]: https://devblogs.microsoft.com/scripting/visual-studio-code-editing-features-for-powershell-development-part-1/
[editing-part2]: https://devblogs.microsoft.com/scripting/visual-studio-code-editing-features-for-powershell-development-part-2/
[debugging-part1]: https://devblogs.microsoft.com/scripting/debugging-powershell-script-in-visual-studio-code-part-1/
[debugging-part2]: https://devblogs.microsoft.com/scripting/debugging-powershell-script-in-visual-studio-code-part-2/

## <a name="powershell-extension-for-vscode"></a><span data-ttu-id="4c1f6-224">Расширение PowerShell для VSCode</span><span class="sxs-lookup"><span data-stu-id="4c1f6-224">PowerShell Extension for VSCode</span></span>

<span data-ttu-id="4c1f6-225">Исходный код расширения PowerShell доступен на [GitHub](https://github.com/PowerShell/vscode-powershell).</span><span class="sxs-lookup"><span data-stu-id="4c1f6-225">The PowerShell extension's source code can be found on [GitHub](https://github.com/PowerShell/vscode-powershell).</span></span>
