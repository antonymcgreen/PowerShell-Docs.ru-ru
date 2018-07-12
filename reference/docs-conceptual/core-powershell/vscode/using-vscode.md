# <a name="using-visual-studio-code-for-powershell-development"></a><span data-ttu-id="c28ac-101">Использование Visual Studio Code для разработки в PowerShell</span><span class="sxs-lookup"><span data-stu-id="c28ac-101">Using Visual Studio Code for PowerShell Development</span></span>

<span data-ttu-id="c28ac-102">В дополнение к [интегрированной среде сценариев PowerShell][ise] продукт PowerShell также хорошо поддерживается в Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="c28ac-102">In addition to the [PowerShell ISE][ise], PowerShell is also well-supported in Visual Studio Code.</span></span>
<span data-ttu-id="c28ac-103">Кроме того, интегрированная среда сценариев не поддерживается в PowerShell Core, хотя Visual Studio Code поддерживается для PowerShell Core на всех платформах (Windows, macOS и Linux)</span><span class="sxs-lookup"><span data-stu-id="c28ac-103">Furthermore, the ISE is not supported with PowerShell Core, while Visual Studio Code is supported for PowerShell Core on all platforms (Windows, macOS, and Linux)</span></span>

<span data-ttu-id="c28ac-104">Вы можете использовать Visual Studio Code для Windows вместе с PowerShell версии 5 в Windows 10 или установить [Windows Management Framework 5.0 RTM](https://www.microsoft.com/en-us/download/details.aspx?id=50395) для более низких версий Windows (например, Windows 8.1 и т. д.).</span><span class="sxs-lookup"><span data-stu-id="c28ac-104">You can use Visual Studio Code on Windows with PowerShell version 5 by using Windows 10 or by installing [Windows Management Framework 5.0 RTM](https://www.microsoft.com/en-us/download/details.aspx?id=50395) for down-level Windows OSs (e.g. Windows 8.1, etc.).</span></span>

<span data-ttu-id="c28ac-105">Перед запуском убедитесь, что PowerShell установлен в системе.</span><span class="sxs-lookup"><span data-stu-id="c28ac-105">Before starting it, please make sure PowerShell exists on your system.</span></span>
<span data-ttu-id="c28ac-106">Сведения о современных рабочих нагрузках для Windows, macOS и Linux см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="c28ac-106">For modern workloads on Windows, macOS, and Linux, see:</span></span>

- <span data-ttu-id="c28ac-107">[Установка PowerShell Core в Linux][install-pscore-linux]</span><span class="sxs-lookup"><span data-stu-id="c28ac-107">[Installing PowerShell Core on Linux][install-pscore-linux]</span></span>
- <span data-ttu-id="c28ac-108">[Установка PowerShell Core в macOS][install-pscore-macos]</span><span class="sxs-lookup"><span data-stu-id="c28ac-108">[Installing PowerShell Core on macOS][install-pscore-macos]</span></span>
- <span data-ttu-id="c28ac-109">[Установка PowerShell Core в Windows][install-pscore-windows]</span><span class="sxs-lookup"><span data-stu-id="c28ac-109">[Installing PowerShell Core on Windows][install-pscore-windows]</span></span>

<span data-ttu-id="c28ac-110">Сведения о традиционных рабочих нагрузках Windows PowerShell см. в разделе [Установка Windows PowerShell][install-winps].</span><span class="sxs-lookup"><span data-stu-id="c28ac-110">For traditional Windows PowerShell workloads, see [Installing Windows PowerShell][install-winps].</span></span>

## <a name="editing-with-visual-studio-code"></a><span data-ttu-id="c28ac-111">Редактирование с помощью Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="c28ac-111">Editing with Visual Studio Code</span></span>

### <a name="1-installing-visual-studio-codehttpscodevisualstudiocomdocssetupsetup-overview"></a>[<span data-ttu-id="c28ac-112">1. Установка Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="c28ac-112">1. Installing Visual Studio Code</span></span>](https://code.visualstudio.com/Docs/setup/setup-overview)

- <span data-ttu-id="c28ac-113">**Linux**: следуйте инструкциям по установке на странице [Запуск VS Code в Linux](https://code.visualstudio.com/docs/setup/linux).</span><span class="sxs-lookup"><span data-stu-id="c28ac-113">**Linux**: follow the installation instructions on the [Running VS Code on Linux](https://code.visualstudio.com/docs/setup/linux) page</span></span>

- <span data-ttu-id="c28ac-114">**macOS**: следуйте инструкциям по установке на странице [Запуск VS Code в macOS](https://code.visualstudio.com/docs/setup/mac).</span><span class="sxs-lookup"><span data-stu-id="c28ac-114">**macOS**: follow the installation instructions on the [Running VS Code on macOS](https://code.visualstudio.com/docs/setup/mac) page</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="c28ac-115">В macOS нужно установить OpenSSL для правильной работы расширения PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c28ac-115">On macOS, you must install OpenSSL for the PowerShell extension to work correctly.</span></span>
  > <span data-ttu-id="c28ac-116">Для этого проще всего установить [Homebrew](http://brew.sh/), а затем запустить `brew install openssl`.</span><span class="sxs-lookup"><span data-stu-id="c28ac-116">The easiest way to accomplish this is to install [Homebrew](http://brew.sh/) and then run `brew install openssl`.</span></span>
  > <span data-ttu-id="c28ac-117">Теперь Visual Studio Code может загрузить расширение PowerShell правильно.</span><span class="sxs-lookup"><span data-stu-id="c28ac-117">VS Code can now load the the PowerShell extension successfully.</span></span>

- <span data-ttu-id="c28ac-118">**Windows**: следуйте инструкциям по установке на странице [Запуск VS Code в Windows](https://code.visualstudio.com/docs/setup/windows).</span><span class="sxs-lookup"><span data-stu-id="c28ac-118">**Windows**: follow the installation instructions on the [Running VS Code on Windows](https://code.visualstudio.com/docs/setup/windows) page</span></span>

### <a name="2-installing-powershell-extension"></a><span data-ttu-id="c28ac-119">2. Установка расширения PowerShell</span><span class="sxs-lookup"><span data-stu-id="c28ac-119">2. Installing PowerShell Extension</span></span>

- <span data-ttu-id="c28ac-120">Запустите Visual Studio Code следующим образом:</span><span class="sxs-lookup"><span data-stu-id="c28ac-120">Launch the Visual Studio Code app by:</span></span>
  - <span data-ttu-id="c28ac-121">**Windows**: введите `code` в сеансе PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c28ac-121">**Windows**: typing `code` in your PowerShell session</span></span>
  - <span data-ttu-id="c28ac-122">**Linux**: введите `code` в терминале.</span><span class="sxs-lookup"><span data-stu-id="c28ac-122">**Linux**: typing `code` in your terminal</span></span>
  - <span data-ttu-id="c28ac-123">**macOS**: введите `code` в терминале.</span><span class="sxs-lookup"><span data-stu-id="c28ac-123">**macOS**: typing `code` in your terminal</span></span>

- <span data-ttu-id="c28ac-124">Запустите **Quick Open**, нажав клавиши **CTRL+P** (**CMD+P** на Mac).</span><span class="sxs-lookup"><span data-stu-id="c28ac-124">Launch **Quick Open** by pressing **Ctrl+P** (**Cmd+P** on Mac).</span></span>
- <span data-ttu-id="c28ac-125">В Quick Open введите `ext install powershell` и нажмите клавишу **ВВОД**.</span><span class="sxs-lookup"><span data-stu-id="c28ac-125">In Quick Open, type `ext install powershell` and hit **Enter**.</span></span>
- <span data-ttu-id="c28ac-126">На боковой панели открывается представление **Расширения**.</span><span class="sxs-lookup"><span data-stu-id="c28ac-126">The **Extensions** view opens on the Side Bar.</span></span> <span data-ttu-id="c28ac-127">Выберите расширение PowerShell корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="c28ac-127">Select the PowerShell extension from Microsoft.</span></span>
  <span data-ttu-id="c28ac-128">Отображается примерно следующее:</span><span class="sxs-lookup"><span data-stu-id="c28ac-128">You should see something like below:</span></span>

  ![VSCode](../../images/vscode.png)

- <span data-ttu-id="c28ac-130">Нажмите кнопку **Установить** для расширения PowerShell корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="c28ac-130">Click the **Install** button on the PowerShell extension from Microsoft.</span></span>
- <span data-ttu-id="c28ac-131">После установки кнопка **Установить** изменяется на **Перезагрузить**.</span><span class="sxs-lookup"><span data-stu-id="c28ac-131">After the install, you see the **Install** button turns to **Reload**.</span></span>
  <span data-ttu-id="c28ac-132">Нажмите кнопку **Перезагрузить**.</span><span class="sxs-lookup"><span data-stu-id="c28ac-132">Click on **Reload**.</span></span>
- <span data-ttu-id="c28ac-133">После перезагрузки Visual Studio Code можно приступать к редактированию.</span><span class="sxs-lookup"><span data-stu-id="c28ac-133">After Visual Studio Code has reload, you are ready for editing.</span></span>

<span data-ttu-id="c28ac-134">Например, чтобы создать файл, выберите **Файл -> Создать**.</span><span class="sxs-lookup"><span data-stu-id="c28ac-134">For example, to create a new file, click **File->New**.</span></span>
<span data-ttu-id="c28ac-135">Чтобы сохранить его, выберите **Файл -> Сохранить** и укажите имя файла, например `HelloWorld.ps1`.</span><span class="sxs-lookup"><span data-stu-id="c28ac-135">To save it, click **File->Save** and then provide a file name, let's say `HelloWorld.ps1`.</span></span>
<span data-ttu-id="c28ac-136">Чтобы закрыть файл, щелкните "x" рядом с его именем.</span><span class="sxs-lookup"><span data-stu-id="c28ac-136">To close the file, click on "x" next to the file name.</span></span>
<span data-ttu-id="c28ac-137">Чтобы завершить работу Visual Studio Code, выберите **Файл -> Выйти**.</span><span class="sxs-lookup"><span data-stu-id="c28ac-137">To exit Visual Studio Code, **File->Exit**.</span></span>

#### <a name="using-a-specific-installed-version-of-powershell"></a><span data-ttu-id="c28ac-138">Использование определенной установленной версии PowerShell</span><span class="sxs-lookup"><span data-stu-id="c28ac-138">Using a specific installed version of PowerShell</span></span>

<span data-ttu-id="c28ac-139">Если вы хотите использовать с Visual Studio Code определенную установку PowerShell, нужно добавить в файл параметров пользователя новую переменную.</span><span class="sxs-lookup"><span data-stu-id="c28ac-139">If you wish to use a specific installation of PowerShell with Visual Studio Code, you need to add a new variable to your user settings file.</span></span>

1. <span data-ttu-id="c28ac-140">Щелкните **Файл -> Параметры -> Параметры**</span><span class="sxs-lookup"><span data-stu-id="c28ac-140">Click **File -> Preferences -> Settings**</span></span>
2. <span data-ttu-id="c28ac-141">Отображаются две панели редактора.</span><span class="sxs-lookup"><span data-stu-id="c28ac-141">Two editor panes appear.</span></span>
   <span data-ttu-id="c28ac-142">На панели справа (`settings.json`) вставьте параметр в разделе соответствующей операционной системы между двумя фигурными скобками (`{` и `}`) и замените *<version>* на установленную версию PowerShell:</span><span class="sxs-lookup"><span data-stu-id="c28ac-142">In the right-most pane (`settings.json`), insert the setting below appropriate for your OS somewhere between the two curly brackets (`{` and `}`) and replace *<version>* with the installed PowerShell version:</span></span>

   ```json
    // On Windows:
    "powershell.powerShellExePath": "c:/Program Files/PowerShell/<version>/pwsh.exe"

    // On Linux:
    "powershell.powerShellExePath": "/opt/microsoft/powershell/<version>/pwsh"

    // On macOS:
    "powershell.powerShellExePath": "/usr/local/microsoft/powershell/<version>/pwsh"
   ```

3. <span data-ttu-id="c28ac-143">Замените параметр на путь к требуемому исполняемому файлу PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c28ac-143">Replace the setting with the path to the desired PowerShell executable</span></span>
4. <span data-ttu-id="c28ac-144">Сохраните файл параметров и перезапустите Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="c28ac-144">Save the settings file and restart Visual Studio Code</span></span>

#### <a name="configuration-settings-for-visual-studio-code"></a><span data-ttu-id="c28ac-145">Параметры конфигурации для Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="c28ac-145">Configuration settings for Visual Studio Code</span></span>

<span data-ttu-id="c28ac-146">Следуя инструкциям в предыдущем абзаце, вы можете добавить параметры конфигурации в `settings.json`.</span><span class="sxs-lookup"><span data-stu-id="c28ac-146">By using the steps in the previous paragraph you can add configuration settings in `settings.json`.</span></span>

<span data-ttu-id="c28ac-147">Мы рекомендуем использовать следующие параметры конфигурации для Visual Studio Code:</span><span class="sxs-lookup"><span data-stu-id="c28ac-147">We recommend the following configuration settings for Visual Studio Code:</span></span>

```json
{
    "csharp.suppressDotnetRestoreNotification": true,
    "editor.renderWhitespace": "all",
    "editor.renderControlCharacters": true,
    "omnisharp.projectLoadTimeout": 120,
    "files.trimTrailingWhitespace": true
}
```

## <a name="debugging-with-visual-studio-code"></a><span data-ttu-id="c28ac-148">Отладка с помощью Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="c28ac-148">Debugging with Visual Studio Code</span></span>

### <a name="no-workspace-debugging"></a><span data-ttu-id="c28ac-149">Отладка без рабочей области</span><span class="sxs-lookup"><span data-stu-id="c28ac-149">No-workspace debugging</span></span>

<span data-ttu-id="c28ac-150">Начиная с Visual Studio Code версии 1.9, вы можете отлаживать сценарии PowerShell, не открывая папку со сценарием PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c28ac-150">As of Visual Studio Code version 1.9 you can debug PowerShell scripts without having to open the folder containing the PowerShell script.</span></span>
<span data-ttu-id="c28ac-151">Просто откройте файл сценария PowerShell с помощью команды **Файл -> Открыть файл...** , установите точку останова на строке (нажав клавишу F9) и нажмите клавишу F5 для запуска отладки.</span><span class="sxs-lookup"><span data-stu-id="c28ac-151">Simply open the PowerShell script file with **File->Open File...**, set a breakpoint on a line (press F9) and then press F5 to start debugging.</span></span>
<span data-ttu-id="c28ac-152">Отображается панель действий отладки, позволяющая прервать работу отладчика, возобновить отладку, выполнить ее пошагово или остановить.</span><span class="sxs-lookup"><span data-stu-id="c28ac-152">You should see the Debug actions pane appear which allows you to break into the debugger, step, resume and stop debugging.</span></span>

### <a name="workspace-debugging"></a><span data-ttu-id="c28ac-153">Отладка с рабочей областью</span><span class="sxs-lookup"><span data-stu-id="c28ac-153">Workspace debugging</span></span>

<span data-ttu-id="c28ac-154">Отладка с рабочей областью обозначает отладку в контексте папки, которую вы открыли в Visual Studio Code с помощью команды **Открыть папку...** из меню **Файл**.</span><span class="sxs-lookup"><span data-stu-id="c28ac-154">Workspace debugging refers to debugging in the context of a folder that you have opened in Visual Studio Code using **Open Folder...** from the **File** menu.</span></span>
<span data-ttu-id="c28ac-155">Обычно открытая папка является папкой проекта PowerShell и (или) корнем репозитория Git.</span><span class="sxs-lookup"><span data-stu-id="c28ac-155">The folder you open is typically your PowerShell project folder and/or the root of your Git repository.</span></span>

<span data-ttu-id="c28ac-156">Даже в этом режиме вы можете начать отладку выбранного сценария PowerShell, просто нажав клавишу F5.</span><span class="sxs-lookup"><span data-stu-id="c28ac-156">Even in this mode, you can start debugging the currently selected PowerShell script by simply pressing F5.</span></span>
<span data-ttu-id="c28ac-157">Однако отладка с рабочей областью позволяет задать несколько конфигураций отладки, отличных от простой отладки открытого файла.</span><span class="sxs-lookup"><span data-stu-id="c28ac-157">However, workspace debugging allows you to define multiple debug configurations other than just debugging the currently open file.</span></span>
<span data-ttu-id="c28ac-158">Например, можно добавить конфигурации следующего характера:</span><span class="sxs-lookup"><span data-stu-id="c28ac-158">For instance, you can add a configurations to:</span></span>

- <span data-ttu-id="c28ac-159">Запуск тестов Pester в отладчике</span><span class="sxs-lookup"><span data-stu-id="c28ac-159">Launch Pester tests in the debugger</span></span>
- <span data-ttu-id="c28ac-160">Запуск определенного файла с аргументами в отладчике</span><span class="sxs-lookup"><span data-stu-id="c28ac-160">Launch a specific file with arguments in the debugger</span></span>
- <span data-ttu-id="c28ac-161">Запуск интерактивного сеанса в отладчике</span><span class="sxs-lookup"><span data-stu-id="c28ac-161">Launch an interactive session in the debugger</span></span>
- <span data-ttu-id="c28ac-162">Подключение отладчика к хост-процессу PowerShell</span><span class="sxs-lookup"><span data-stu-id="c28ac-162">Attach the debugger to a PowerShell host process</span></span>

  <span data-ttu-id="c28ac-163">Выполните следующие действия, чтобы создать файл конфигурации отладки:</span><span class="sxs-lookup"><span data-stu-id="c28ac-163">Follow these steps to create your debug configuration file:</span></span>

  1. <span data-ttu-id="c28ac-164">Откройте представление **Отладка**, нажав клавиши **CTRL+SHIFT+D** (**CMD+SHIFT+D** на Mac).</span><span class="sxs-lookup"><span data-stu-id="c28ac-164">Open the **Debug** view by pressing **Ctrl+Shift+D** (**Cmd+Shift+D** on Mac).</span></span>
  2. <span data-ttu-id="c28ac-165">Щелкните значок с шестеренкой **Настройка** на панели инструментов.</span><span class="sxs-lookup"><span data-stu-id="c28ac-165">Press the **Configure** gear icon in the toolbar.</span></span>
  3. <span data-ttu-id="c28ac-166">Visual Studio Code предлагает вам **выбрать среду**.</span><span class="sxs-lookup"><span data-stu-id="c28ac-166">Visual Studio Code prompts you to **Select Environment**.</span></span>
  <span data-ttu-id="c28ac-167">Выберите **PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="c28ac-167">Choose **PowerShell**.</span></span>

  <span data-ttu-id="c28ac-168">При этом Visual Studio Code создает каталог и файл ".vscode\launch.json" в корневой папке рабочей области.</span><span class="sxs-lookup"><span data-stu-id="c28ac-168">When you do this, Visual Studio Code creates a directory and a file ".vscode\launch.json" in the root of your workspace folder.</span></span>
  <span data-ttu-id="c28ac-169">Именно там хранится ваша конфигурация отладки.</span><span class="sxs-lookup"><span data-stu-id="c28ac-169">This is where your debug configuration is stored.</span></span> <span data-ttu-id="c28ac-170">Если ваши файлы хранятся в репозитории Git, скорее всего, вы захотите зафиксировать файл launch.json.</span><span class="sxs-lookup"><span data-stu-id="c28ac-170">If your files are in a Git repository, you typically want to commit the launch.json file.</span></span>
  <span data-ttu-id="c28ac-171">Файла launch.json содержит следующее:</span><span class="sxs-lookup"><span data-stu-id="c28ac-171">The contents of the launch.json file are:</span></span>

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

  <span data-ttu-id="c28ac-172">Это представляет типичные сценарии отладки.</span><span class="sxs-lookup"><span data-stu-id="c28ac-172">This represents the common debug scenarios.</span></span>
  <span data-ttu-id="c28ac-173">Однако при открытии этого файла в редакторе отображается кнопка **Добавить конфигурацию...**.</span><span class="sxs-lookup"><span data-stu-id="c28ac-173">However, when you open this file in the editor, you see an **Add Configuration...** button.</span></span>
  <span data-ttu-id="c28ac-174">Можете нажать ее, чтобы добавить дополнительные конфигурации отладки PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c28ac-174">You can press this button to add more PowerShell debug configurations.</span></span> <span data-ttu-id="c28ac-175">Одной из полезных конфигураций является **PowerShell: Launch Script**.</span><span class="sxs-lookup"><span data-stu-id="c28ac-175">One handy configuration to add is **PowerShell: Launch Script**.</span></span>
  <span data-ttu-id="c28ac-176">С помощью этой конфигурации можно указать определенный файл с дополнительными аргументами, которые нужно запускать при каждом нажатии клавиши F5 независимо от того, какой именно файл активен в редакторе.</span><span class="sxs-lookup"><span data-stu-id="c28ac-176">With this configuration, you can specify a specific file with optional arguments that should be launched whenever you press F5 no matter which file is currently active in the editor.</span></span>

  <span data-ttu-id="c28ac-177">После задания конфигурации отладки можно указать конфигурацию, используемую во время сеанса отладки, выбрав ее в раскрывающемся списке конфигураций отладки на панели инструментов представления **Отладка**.</span><span class="sxs-lookup"><span data-stu-id="c28ac-177">Once the debug configuration is established, you can select which configuration you want to use during a debug session by selecting one from the debug configuration drop-down in the **Debug** view's toolbar.</span></span>

  <span data-ttu-id="c28ac-178">Существует несколько блогов, которые могут оказаться полезными при начале работы с расширением PowerShell для Visual Studio Code:</span><span class="sxs-lookup"><span data-stu-id="c28ac-178">There are a few blogs that may be helpful to get you started using PowerShell extension for Visual Studio Code</span></span>

<span data-ttu-id="c28ac-179">Visual Studio Code:</span><span class="sxs-lookup"><span data-stu-id="c28ac-179">Visual Studio Code:</span></span>

- <span data-ttu-id="c28ac-180">[Расширение PowerShell][ps-extension]</span><span class="sxs-lookup"><span data-stu-id="c28ac-180">[PowerShell Extension][ps-extension]</span></span>
- <span data-ttu-id="c28ac-181">[Написание и отладка в сценариев PowerShell в Visual Studio Code][debug]</span><span class="sxs-lookup"><span data-stu-id="c28ac-181">[Write and debug PowerShell scripts in Visual Studio Code][debug]</span></span>
- <span data-ttu-id="c28ac-182">[Руководство по отладке Visual Studio Code][vscode-guide]</span><span class="sxs-lookup"><span data-stu-id="c28ac-182">[Debugging Visual Studio Code Guidance][vscode-guide]</span></span>
- <span data-ttu-id="c28ac-183">[Отладка PowerShell в Visual Studio Code][ps-vscode]</span><span class="sxs-lookup"><span data-stu-id="c28ac-183">[Debugging PowerShell in Visual Studio Code][ps-vscode]</span></span>
- <span data-ttu-id="c28ac-184">[Приступая к разработке PowerShell в Visual Studio Code][getting-started]</span><span class="sxs-lookup"><span data-stu-id="c28ac-184">[Get started with PowerShell development in Visual Studio Code][getting-started]</span></span>
- <span data-ttu-id="c28ac-185">[Функции редактирования Visual Studio Code для разработки PowerShell. Часть 1][editing-part1]</span><span class="sxs-lookup"><span data-stu-id="c28ac-185">[Visual Studio Code editing features for PowerShell development – Part 1][editing-part1]</span></span>
- <span data-ttu-id="c28ac-186">[Функции редактирования Visual Studio Code для разработки PowerShell. Часть 2][editing-part2]</span><span class="sxs-lookup"><span data-stu-id="c28ac-186">[Visual Studio Code editing features for PowerShell development – Part 2][editing-part2]</span></span>
- <span data-ttu-id="c28ac-187">[Отладка сценария PowerShell в Visual Studio Code. Часть 1][debugging-part1]</span><span class="sxs-lookup"><span data-stu-id="c28ac-187">[Debugging PowerShell script in Visual Studio Code – Part 1][debugging-part1]</span></span>
- <span data-ttu-id="c28ac-188">[Отладка сценария PowerShell в Visual Studio Code. Часть 2][debugging-part2]</span><span class="sxs-lookup"><span data-stu-id="c28ac-188">[Debugging PowerShell script in Visual Studio Code – Part 2][debugging-part2]</span></span>

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

## <a name="powershell-extension-for-visual-studio-code"></a><span data-ttu-id="c28ac-189">Расширение PowerShell для Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="c28ac-189">PowerShell Extension for Visual Studio Code</span></span>

<span data-ttu-id="c28ac-190">Исходный код расширения PowerShell доступен на [GitHub](https://github.com/PowerShell/vscode-powershell).</span><span class="sxs-lookup"><span data-stu-id="c28ac-190">The PowerShell extension's source code can be found on [GitHub](https://github.com/PowerShell/vscode-powershell).</span></span>