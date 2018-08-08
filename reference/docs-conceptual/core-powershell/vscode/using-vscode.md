---
title: Использование Visual Studio Code для разработки в PowerShell
description: Использование Visual Studio Code для разработки в PowerShell
ms.date: 08/06/2018
ms.openlocfilehash: f8e1e9af257037fc7bd74549e4197c9a1695e952
ms.sourcegitcommit: 01ac77cd0b00e4e5e964504563a9212e8002e5e0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2018
ms.locfileid: "39587437"
---
# <a name="using-visual-studio-code-for-powershell-development"></a><span data-ttu-id="c4c24-103">Использование Visual Studio Code для разработки в PowerShell</span><span class="sxs-lookup"><span data-stu-id="c4c24-103">Using Visual Studio Code for PowerShell Development</span></span>

<span data-ttu-id="c4c24-104">В дополнение к [интегрированной среде сценариев PowerShell][ise] продукт PowerShell также хорошо поддерживается в Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="c4c24-104">In addition to the [PowerShell ISE][ise], PowerShell is also well-supported in Visual Studio Code.</span></span>
<span data-ttu-id="c4c24-105">Кроме того, интегрированная среда сценариев не поддерживается в PowerShell Core, хотя Visual Studio Code поддерживается для PowerShell Core на всех платформах (Windows, macOS и Linux)</span><span class="sxs-lookup"><span data-stu-id="c4c24-105">Furthermore, the ISE is not supported with PowerShell Core, while Visual Studio Code is supported for PowerShell Core on all platforms (Windows, macOS, and Linux)</span></span>

<span data-ttu-id="c4c24-106">Вы можете использовать Visual Studio Code для Windows вместе с PowerShell версии 5 в Windows 10 или установить [Windows Management Framework 5.0 RTM](https://www.microsoft.com/en-us/download/details.aspx?id=50395) для более низких версий Windows (например, Windows 8.1 и т. д.).</span><span class="sxs-lookup"><span data-stu-id="c4c24-106">You can use Visual Studio Code on Windows with PowerShell version 5 by using Windows 10 or by installing [Windows Management Framework 5.0 RTM](https://www.microsoft.com/en-us/download/details.aspx?id=50395) for down-level Windows OSs (e.g. Windows 8.1, etc.).</span></span>

<span data-ttu-id="c4c24-107">Перед запуском убедитесь, что PowerShell установлен в системе.</span><span class="sxs-lookup"><span data-stu-id="c4c24-107">Before starting it, please make sure PowerShell exists on your system.</span></span>
<span data-ttu-id="c4c24-108">Сведения о современных рабочих нагрузках для Windows, macOS и Linux см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="c4c24-108">For modern workloads on Windows, macOS, and Linux, see:</span></span>

- <span data-ttu-id="c4c24-109">[Установка PowerShell Core в Linux][install-pscore-linux]</span><span class="sxs-lookup"><span data-stu-id="c4c24-109">[Installing PowerShell Core on Linux][install-pscore-linux]</span></span>
- <span data-ttu-id="c4c24-110">[Установка PowerShell Core в macOS][install-pscore-macos]</span><span class="sxs-lookup"><span data-stu-id="c4c24-110">[Installing PowerShell Core on macOS][install-pscore-macos]</span></span>
- <span data-ttu-id="c4c24-111">[Установка PowerShell Core в Windows][install-pscore-windows]</span><span class="sxs-lookup"><span data-stu-id="c4c24-111">[Installing PowerShell Core on Windows][install-pscore-windows]</span></span>

<span data-ttu-id="c4c24-112">Сведения о традиционных рабочих нагрузках Windows PowerShell см. в разделе [Установка Windows PowerShell][install-winps].</span><span class="sxs-lookup"><span data-stu-id="c4c24-112">For traditional Windows PowerShell workloads, see [Installing Windows PowerShell][install-winps].</span></span>

## <a name="editing-with-visual-studio-code"></a><span data-ttu-id="c4c24-113">Редактирование с помощью Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="c4c24-113">Editing with Visual Studio Code</span></span>

### <a name="1-installing-visual-studio-codehttpscodevisualstudiocomdocssetupsetup-overview"></a>[<span data-ttu-id="c4c24-114">1. Установка Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="c4c24-114">1. Installing Visual Studio Code</span></span>](https://code.visualstudio.com/Docs/setup/setup-overview)

- <span data-ttu-id="c4c24-115">**Linux**: следуйте инструкциям по установке на странице [Запуск VS Code в Linux](https://code.visualstudio.com/docs/setup/linux).</span><span class="sxs-lookup"><span data-stu-id="c4c24-115">**Linux**: follow the installation instructions on the [Running VS Code on Linux](https://code.visualstudio.com/docs/setup/linux) page</span></span>

- <span data-ttu-id="c4c24-116">**macOS**: следуйте инструкциям по установке на странице [Запуск VS Code в macOS](https://code.visualstudio.com/docs/setup/mac).</span><span class="sxs-lookup"><span data-stu-id="c4c24-116">**macOS**: follow the installation instructions on the [Running VS Code on macOS](https://code.visualstudio.com/docs/setup/mac) page</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="c4c24-117">В macOS нужно установить OpenSSL для правильной работы расширения PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c4c24-117">On macOS, you must install OpenSSL for the PowerShell extension to work correctly.</span></span>
  > <span data-ttu-id="c4c24-118">Для этого проще всего установить [Homebrew](http://brew.sh/), а затем запустить `brew install openssl`.</span><span class="sxs-lookup"><span data-stu-id="c4c24-118">The easiest way to accomplish this is to install [Homebrew](http://brew.sh/) and then run `brew install openssl`.</span></span>
  > <span data-ttu-id="c4c24-119">Теперь Visual Studio Code может загрузить расширение PowerShell правильно.</span><span class="sxs-lookup"><span data-stu-id="c4c24-119">VS Code can now load the the PowerShell extension successfully.</span></span>

- <span data-ttu-id="c4c24-120">**Windows**: следуйте инструкциям по установке на странице [Запуск VS Code в Windows](https://code.visualstudio.com/docs/setup/windows).</span><span class="sxs-lookup"><span data-stu-id="c4c24-120">**Windows**: follow the installation instructions on the [Running VS Code on Windows](https://code.visualstudio.com/docs/setup/windows) page</span></span>

### <a name="2-installing-powershell-extension"></a><span data-ttu-id="c4c24-121">2. Установка расширения PowerShell</span><span class="sxs-lookup"><span data-stu-id="c4c24-121">2. Installing PowerShell Extension</span></span>

- <span data-ttu-id="c4c24-122">Запустите Visual Studio Code следующим образом:</span><span class="sxs-lookup"><span data-stu-id="c4c24-122">Launch the Visual Studio Code app by:</span></span>
  - <span data-ttu-id="c4c24-123">**Windows**: введите `code` в сеансе PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c4c24-123">**Windows**: typing `code` in your PowerShell session</span></span>
  - <span data-ttu-id="c4c24-124">**Linux**: введите `code` в терминале.</span><span class="sxs-lookup"><span data-stu-id="c4c24-124">**Linux**: typing `code` in your terminal</span></span>
  - <span data-ttu-id="c4c24-125">**macOS**: введите `code` в терминале.</span><span class="sxs-lookup"><span data-stu-id="c4c24-125">**macOS**: typing `code` in your terminal</span></span>

- <span data-ttu-id="c4c24-126">Запустите **Quick Open**, нажав клавиши **CTRL+P** (**CMD+P** на Mac).</span><span class="sxs-lookup"><span data-stu-id="c4c24-126">Launch **Quick Open** by pressing **Ctrl+P** (**Cmd+P** on Mac).</span></span>
- <span data-ttu-id="c4c24-127">В Quick Open введите `ext install powershell` и нажмите клавишу **ВВОД**.</span><span class="sxs-lookup"><span data-stu-id="c4c24-127">In Quick Open, type `ext install powershell` and hit **Enter**.</span></span>
- <span data-ttu-id="c4c24-128">На боковой панели открывается представление **Расширения**.</span><span class="sxs-lookup"><span data-stu-id="c4c24-128">The **Extensions** view opens on the Side Bar.</span></span> <span data-ttu-id="c4c24-129">Выберите расширение PowerShell корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="c4c24-129">Select the PowerShell extension from Microsoft.</span></span>
  <span data-ttu-id="c4c24-130">Отображается примерно следующее:</span><span class="sxs-lookup"><span data-stu-id="c4c24-130">You should see something like below:</span></span>

  ![VSCode](../../images/vscode.png)

- <span data-ttu-id="c4c24-132">Нажмите кнопку **Установить** для расширения PowerShell корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="c4c24-132">Click the **Install** button on the PowerShell extension from Microsoft.</span></span>
- <span data-ttu-id="c4c24-133">После установки кнопка **Установить** изменяется на **Перезагрузить**.</span><span class="sxs-lookup"><span data-stu-id="c4c24-133">After the install, you see the **Install** button turns to **Reload**.</span></span>
  <span data-ttu-id="c4c24-134">Нажмите кнопку **Перезагрузить**.</span><span class="sxs-lookup"><span data-stu-id="c4c24-134">Click on **Reload**.</span></span>
- <span data-ttu-id="c4c24-135">После перезагрузки Visual Studio Code можно приступать к редактированию.</span><span class="sxs-lookup"><span data-stu-id="c4c24-135">After Visual Studio Code has reload, you are ready for editing.</span></span>

<span data-ttu-id="c4c24-136">Например, чтобы создать файл, выберите **Файл -> Создать**.</span><span class="sxs-lookup"><span data-stu-id="c4c24-136">For example, to create a new file, click **File->New**.</span></span>
<span data-ttu-id="c4c24-137">Чтобы сохранить его, выберите **Файл -> Сохранить** и укажите имя файла, например `HelloWorld.ps1`.</span><span class="sxs-lookup"><span data-stu-id="c4c24-137">To save it, click **File->Save** and then provide a file name, let's say `HelloWorld.ps1`.</span></span>
<span data-ttu-id="c4c24-138">Чтобы закрыть файл, щелкните "x" рядом с его именем.</span><span class="sxs-lookup"><span data-stu-id="c4c24-138">To close the file, click on "x" next to the file name.</span></span>
<span data-ttu-id="c4c24-139">Чтобы завершить работу Visual Studio Code, выберите **Файл -> Выйти**.</span><span class="sxs-lookup"><span data-stu-id="c4c24-139">To exit Visual Studio Code, **File->Exit**.</span></span>

#### <a name="using-a-specific-installed-version-of-powershell"></a><span data-ttu-id="c4c24-140">Использование определенной установленной версии PowerShell</span><span class="sxs-lookup"><span data-stu-id="c4c24-140">Using a specific installed version of PowerShell</span></span>

<span data-ttu-id="c4c24-141">Если вы хотите использовать с Visual Studio Code определенную установку PowerShell, нужно добавить в файл параметров пользователя новую переменную.</span><span class="sxs-lookup"><span data-stu-id="c4c24-141">If you wish to use a specific installation of PowerShell with Visual Studio Code, you need to add a new variable to your user settings file.</span></span>

1. <span data-ttu-id="c4c24-142">Щелкните **Файл -> Параметры -> Параметры**</span><span class="sxs-lookup"><span data-stu-id="c4c24-142">Click **File -> Preferences -> Settings**</span></span>
1. <span data-ttu-id="c4c24-143">Отображаются две панели редактора.</span><span class="sxs-lookup"><span data-stu-id="c4c24-143">Two editor panes appear.</span></span>
   <span data-ttu-id="c4c24-144">На панели справа (`settings.json`) вставьте параметр в разделе соответствующей операционной системы между двумя фигурными скобками (`{` и `}`) и замените **\<версию\>** установленной версией PowerShell:</span><span class="sxs-lookup"><span data-stu-id="c4c24-144">In the right-most pane (`settings.json`), insert the setting below appropriate for your OS somewhere between the two curly brackets (`{` and `}`) and replace **\<version\>** with the installed PowerShell version:</span></span>

   ```json
    // On Windows:
    "powershell.powerShellExePath": "c:/Program Files/PowerShell/<version>/pwsh.exe"

    // On Linux:
    "powershell.powerShellExePath": "/opt/microsoft/powershell/<version>/pwsh"

    // On macOS:
    "powershell.powerShellExePath": "/usr/local/microsoft/powershell/<version>/pwsh"
   ```

1. <span data-ttu-id="c4c24-145">Замените параметр на путь к требуемому исполняемому файлу PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c4c24-145">Replace the setting with the path to the desired PowerShell executable</span></span>
1. <span data-ttu-id="c4c24-146">Сохраните файл параметров и перезапустите Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="c4c24-146">Save the settings file and restart Visual Studio Code</span></span>

#### <a name="configuration-settings-for-visual-studio-code"></a><span data-ttu-id="c4c24-147">Параметры конфигурации для Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="c4c24-147">Configuration settings for Visual Studio Code</span></span>

<span data-ttu-id="c4c24-148">Следуя инструкциям в предыдущем абзаце, вы можете добавить параметры конфигурации в `settings.json`.</span><span class="sxs-lookup"><span data-stu-id="c4c24-148">By using the steps in the previous paragraph you can add configuration settings in `settings.json`.</span></span>

<span data-ttu-id="c4c24-149">Мы рекомендуем использовать следующие параметры конфигурации для Visual Studio Code:</span><span class="sxs-lookup"><span data-stu-id="c4c24-149">We recommend the following configuration settings for Visual Studio Code:</span></span>

```json
{
    "csharp.suppressDotnetRestoreNotification": true,
    "editor.renderWhitespace": "all",
    "editor.renderControlCharacters": true,
    "omnisharp.projectLoadTimeout": 120,
    "files.trimTrailingWhitespace": true
}
```

## <a name="debugging-with-visual-studio-code"></a><span data-ttu-id="c4c24-150">Отладка с помощью Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="c4c24-150">Debugging with Visual Studio Code</span></span>

### <a name="no-workspace-debugging"></a><span data-ttu-id="c4c24-151">Отладка без рабочей области</span><span class="sxs-lookup"><span data-stu-id="c4c24-151">No-workspace debugging</span></span>

<span data-ttu-id="c4c24-152">Начиная с Visual Studio Code версии 1.9, вы можете отлаживать сценарии PowerShell, не открывая папку со сценарием PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c4c24-152">As of Visual Studio Code version 1.9 you can debug PowerShell scripts without having to open the folder containing the PowerShell script.</span></span>
<span data-ttu-id="c4c24-153">Просто откройте файл сценария PowerShell с помощью команды **Файл -> Открыть файл...** , установите точку останова на строке (нажав клавишу F9) и нажмите клавишу F5 для запуска отладки.</span><span class="sxs-lookup"><span data-stu-id="c4c24-153">Simply open the PowerShell script file with **File->Open File...**, set a breakpoint on a line (press F9) and then press F5 to start debugging.</span></span>
<span data-ttu-id="c4c24-154">Отображается панель действий отладки, позволяющая прервать работу отладчика, возобновить отладку, выполнить ее пошагово или остановить.</span><span class="sxs-lookup"><span data-stu-id="c4c24-154">You should see the Debug actions pane appear which allows you to break into the debugger, step, resume and stop debugging.</span></span>

### <a name="workspace-debugging"></a><span data-ttu-id="c4c24-155">Отладка с рабочей областью</span><span class="sxs-lookup"><span data-stu-id="c4c24-155">Workspace debugging</span></span>

<span data-ttu-id="c4c24-156">Отладка с рабочей областью обозначает отладку в контексте папки, которую вы открыли в Visual Studio Code с помощью команды **Открыть папку...** из меню **Файл**.</span><span class="sxs-lookup"><span data-stu-id="c4c24-156">Workspace debugging refers to debugging in the context of a folder that you have opened in Visual Studio Code using **Open Folder...** from the **File** menu.</span></span>
<span data-ttu-id="c4c24-157">Обычно открытая папка является папкой проекта PowerShell и (или) корнем репозитория Git.</span><span class="sxs-lookup"><span data-stu-id="c4c24-157">The folder you open is typically your PowerShell project folder and/or the root of your Git repository.</span></span>

<span data-ttu-id="c4c24-158">Даже в этом режиме вы можете начать отладку выбранного сценария PowerShell, просто нажав клавишу F5.</span><span class="sxs-lookup"><span data-stu-id="c4c24-158">Even in this mode, you can start debugging the currently selected PowerShell script by simply pressing F5.</span></span>
<span data-ttu-id="c4c24-159">Однако отладка с рабочей областью позволяет задать несколько конфигураций отладки, отличных от простой отладки открытого файла.</span><span class="sxs-lookup"><span data-stu-id="c4c24-159">However, workspace debugging allows you to define multiple debug configurations other than just debugging the currently open file.</span></span>
<span data-ttu-id="c4c24-160">Например, можно добавить конфигурации следующего характера:</span><span class="sxs-lookup"><span data-stu-id="c4c24-160">For instance, you can add a configurations to:</span></span>

- <span data-ttu-id="c4c24-161">Запуск тестов Pester в отладчике</span><span class="sxs-lookup"><span data-stu-id="c4c24-161">Launch Pester tests in the debugger</span></span>
- <span data-ttu-id="c4c24-162">Запуск определенного файла с аргументами в отладчике</span><span class="sxs-lookup"><span data-stu-id="c4c24-162">Launch a specific file with arguments in the debugger</span></span>
- <span data-ttu-id="c4c24-163">Запуск интерактивного сеанса в отладчике</span><span class="sxs-lookup"><span data-stu-id="c4c24-163">Launch an interactive session in the debugger</span></span>
- <span data-ttu-id="c4c24-164">Подключение отладчика к хост-процессу PowerShell</span><span class="sxs-lookup"><span data-stu-id="c4c24-164">Attach the debugger to a PowerShell host process</span></span>

  <span data-ttu-id="c4c24-165">Выполните следующие действия, чтобы создать файл конфигурации отладки:</span><span class="sxs-lookup"><span data-stu-id="c4c24-165">Follow these steps to create your debug configuration file:</span></span>

  1. <span data-ttu-id="c4c24-166">Откройте представление **Отладка**, нажав клавиши **CTRL+SHIFT+D** (**CMD+SHIFT+D** на Mac).</span><span class="sxs-lookup"><span data-stu-id="c4c24-166">Open the **Debug** view by pressing **Ctrl+Shift+D** (**Cmd+Shift+D** on Mac).</span></span>
  2. <span data-ttu-id="c4c24-167">Щелкните значок с шестеренкой **Настройка** на панели инструментов.</span><span class="sxs-lookup"><span data-stu-id="c4c24-167">Press the **Configure** gear icon in the toolbar.</span></span>
  3. <span data-ttu-id="c4c24-168">Visual Studio Code предлагает вам **выбрать среду**.</span><span class="sxs-lookup"><span data-stu-id="c4c24-168">Visual Studio Code prompts you to **Select Environment**.</span></span>
  <span data-ttu-id="c4c24-169">Выберите **PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="c4c24-169">Choose **PowerShell**.</span></span>

  <span data-ttu-id="c4c24-170">При этом Visual Studio Code создает каталог и файл ".vscode\launch.json" в корневой папке рабочей области.</span><span class="sxs-lookup"><span data-stu-id="c4c24-170">When you do this, Visual Studio Code creates a directory and a file ".vscode\launch.json" in the root of your workspace folder.</span></span>
  <span data-ttu-id="c4c24-171">Именно там хранится ваша конфигурация отладки.</span><span class="sxs-lookup"><span data-stu-id="c4c24-171">This is where your debug configuration is stored.</span></span> <span data-ttu-id="c4c24-172">Если ваши файлы хранятся в репозитории Git, скорее всего, вы захотите зафиксировать файл launch.json.</span><span class="sxs-lookup"><span data-stu-id="c4c24-172">If your files are in a Git repository, you typically want to commit the launch.json file.</span></span>
  <span data-ttu-id="c4c24-173">Файла launch.json содержит следующее:</span><span class="sxs-lookup"><span data-stu-id="c4c24-173">The contents of the launch.json file are:</span></span>

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

  <span data-ttu-id="c4c24-174">Это представляет типичные сценарии отладки.</span><span class="sxs-lookup"><span data-stu-id="c4c24-174">This represents the common debug scenarios.</span></span>
  <span data-ttu-id="c4c24-175">Однако при открытии этого файла в редакторе отображается кнопка **Добавить конфигурацию...**.</span><span class="sxs-lookup"><span data-stu-id="c4c24-175">However, when you open this file in the editor, you see an **Add Configuration...** button.</span></span>
  <span data-ttu-id="c4c24-176">Можете нажать ее, чтобы добавить дополнительные конфигурации отладки PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c4c24-176">You can press this button to add more PowerShell debug configurations.</span></span> <span data-ttu-id="c4c24-177">Одной из полезных конфигураций является **PowerShell: Launch Script**.</span><span class="sxs-lookup"><span data-stu-id="c4c24-177">One handy configuration to add is **PowerShell: Launch Script**.</span></span>
  <span data-ttu-id="c4c24-178">С помощью этой конфигурации можно указать определенный файл с дополнительными аргументами, которые нужно запускать при каждом нажатии клавиши F5 независимо от того, какой именно файл активен в редакторе.</span><span class="sxs-lookup"><span data-stu-id="c4c24-178">With this configuration, you can specify a specific file with optional arguments that should be launched whenever you press F5 no matter which file is currently active in the editor.</span></span>

  <span data-ttu-id="c4c24-179">После задания конфигурации отладки можно указать конфигурацию, используемую во время сеанса отладки, выбрав ее в раскрывающемся списке конфигураций отладки на панели инструментов представления **Отладка**.</span><span class="sxs-lookup"><span data-stu-id="c4c24-179">Once the debug configuration is established, you can select which configuration you want to use during a debug session by selecting one from the debug configuration drop-down in the **Debug** view's toolbar.</span></span>

  <span data-ttu-id="c4c24-180">Существует несколько блогов, которые могут оказаться полезными при начале работы с расширением PowerShell для Visual Studio Code:</span><span class="sxs-lookup"><span data-stu-id="c4c24-180">There are a few blogs that may be helpful to get you started using PowerShell extension for Visual Studio Code</span></span>

<span data-ttu-id="c4c24-181">Visual Studio Code:</span><span class="sxs-lookup"><span data-stu-id="c4c24-181">Visual Studio Code:</span></span>

- <span data-ttu-id="c4c24-182">[Расширение PowerShell][ps-extension]</span><span class="sxs-lookup"><span data-stu-id="c4c24-182">[PowerShell Extension][ps-extension]</span></span>
- <span data-ttu-id="c4c24-183">[Написание и отладка в сценариев PowerShell в Visual Studio Code][debug]</span><span class="sxs-lookup"><span data-stu-id="c4c24-183">[Write and debug PowerShell scripts in Visual Studio Code][debug]</span></span>
- <span data-ttu-id="c4c24-184">[Руководство по отладке Visual Studio Code][vscode-guide]</span><span class="sxs-lookup"><span data-stu-id="c4c24-184">[Debugging Visual Studio Code Guidance][vscode-guide]</span></span>
- <span data-ttu-id="c4c24-185">[Отладка PowerShell в Visual Studio Code][ps-vscode]</span><span class="sxs-lookup"><span data-stu-id="c4c24-185">[Debugging PowerShell in Visual Studio Code][ps-vscode]</span></span>
- <span data-ttu-id="c4c24-186">[Приступая к разработке PowerShell в Visual Studio Code][getting-started]</span><span class="sxs-lookup"><span data-stu-id="c4c24-186">[Get started with PowerShell development in Visual Studio Code][getting-started]</span></span>
- <span data-ttu-id="c4c24-187">[Функции редактирования Visual Studio Code для разработки PowerShell. Часть 1][editing-part1]</span><span class="sxs-lookup"><span data-stu-id="c4c24-187">[Visual Studio Code editing features for PowerShell development – Part 1][editing-part1]</span></span>
- <span data-ttu-id="c4c24-188">[Функции редактирования Visual Studio Code для разработки PowerShell. Часть 2][editing-part2]</span><span class="sxs-lookup"><span data-stu-id="c4c24-188">[Visual Studio Code editing features for PowerShell development – Part 2][editing-part2]</span></span>
- <span data-ttu-id="c4c24-189">[Отладка сценария PowerShell в Visual Studio Code. Часть 1][debugging-part1]</span><span class="sxs-lookup"><span data-stu-id="c4c24-189">[Debugging PowerShell script in Visual Studio Code – Part 1][debugging-part1]</span></span>
- <span data-ttu-id="c4c24-190">[Отладка сценария PowerShell в Visual Studio Code. Часть 2][debugging-part2]</span><span class="sxs-lookup"><span data-stu-id="c4c24-190">[Debugging PowerShell script in Visual Studio Code – Part 2][debugging-part2]</span></span>

[ise]: ../ise-guide.md
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

## <a name="powershell-extension-for-visual-studio-code"></a><span data-ttu-id="c4c24-191">Расширение PowerShell для Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="c4c24-191">PowerShell Extension for Visual Studio Code</span></span>

<span data-ttu-id="c4c24-192">Исходный код расширения PowerShell доступен на [GitHub](https://github.com/PowerShell/vscode-powershell).</span><span class="sxs-lookup"><span data-stu-id="c4c24-192">The PowerShell extension's source code can be found on [GitHub](https://github.com/PowerShell/vscode-powershell).</span></span>