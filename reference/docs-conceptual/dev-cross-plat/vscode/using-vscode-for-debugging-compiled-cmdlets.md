---
ms.date: 10/19/2020
keywords: powershell,командлет,отладка
title: Отладка скомпилированных командлетов с помощью Visual Studio Code
description: Настройка задачи сборки и конфигурации запуска для проекта PSModule в .NET Core
ms.openlocfilehash: b51a69110c64b386f5c3ccf2527d1e184ef89257
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2020
ms.locfileid: "92501649"
---
# <a name="using-visual-studio-code-to-debug-compiled-cmdlets"></a><span data-ttu-id="77f98-104">Отладка скомпилированных командлетов с помощью Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="77f98-104">Using Visual Studio Code to debug compiled cmdlets</span></span>

<span data-ttu-id="77f98-105">В этом руководстве описывается, как выполнять интерактивную отладку исходного кода на C# для скомпилированного модуля PowerShell с помощью Visual Studio Code (VS Code) и расширения C#.</span><span class="sxs-lookup"><span data-stu-id="77f98-105">This guide shows you how to interactively debug C# source code for a compiled PowerShell module using Visual Studio Code (VS Code) and the C# extension.</span></span>

<span data-ttu-id="77f98-106">Предполагается, что у вас уже есть некоторый опыт работы с отладчиком Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="77f98-106">Some familiarity with the Visual Studio Code debugger is assumed.</span></span>

- <span data-ttu-id="77f98-107">Общие сведения об отладчике VS Code см. в статье [Отладка в Visual Studio Code][].</span><span class="sxs-lookup"><span data-stu-id="77f98-107">For a general introduction to the VS Code debugger, see [Debugging in Visual Studio Code][].</span></span>

- <span data-ttu-id="77f98-108">Примеры отладки файлов скриптов и модулей PowerShell см. в статье [Удаленные редактирование и отладка в Visual Studio Code][].</span><span class="sxs-lookup"><span data-stu-id="77f98-108">For examples of debugging PowerShell script files and modules, see [Using Visual Studio Code for remote editing and debugging][].</span></span>

<span data-ttu-id="77f98-109">В этом руководстве предполагается, что вы прочитали и выполнили инструкции в руководстве [Создание переносимых модулей][].</span><span class="sxs-lookup"><span data-stu-id="77f98-109">This guide assumes you have read and followed the instructions in the [Writing Portable Modules][] guide.</span></span>

## <a name="creating-a-build-task"></a><span data-ttu-id="77f98-110">Создание задачи сборки</span><span class="sxs-lookup"><span data-stu-id="77f98-110">Creating a build task</span></span>

<span data-ttu-id="77f98-111">Выполняйте автоматическую сборку проекта перед запуском сеанса отладки.</span><span class="sxs-lookup"><span data-stu-id="77f98-111">Build your project automatically before launching a debugging session.</span></span> <span data-ttu-id="77f98-112">Это позволяет гарантировать, что вы отлаживаете последнюю версию кода.</span><span class="sxs-lookup"><span data-stu-id="77f98-112">Rebuilding ensures that you debug the latest version of your code.</span></span>

<span data-ttu-id="77f98-113">Настройте задачу сборки.</span><span class="sxs-lookup"><span data-stu-id="77f98-113">Configure a build task:</span></span>

1. <span data-ttu-id="77f98-114">В **палитре команд** выполните команду **Настроить задачу сборки по умолчанию** .</span><span class="sxs-lookup"><span data-stu-id="77f98-114">In the **Command Palette** , run the **Configure Default Build Task** command.</span></span>

   ![Выполнение команды "Настроить задачу сборки по умолчанию"](media/using-vscode-for-debugging-compiled-cmdlets/configure-default-build-task.png)

1. <span data-ttu-id="77f98-116">В диалоговом окне **Выбор задачи для настройки** выберите **Создать файл tasks.json из шаблона** .</span><span class="sxs-lookup"><span data-stu-id="77f98-116">In the **Select a task to configure** dialog, choose **Create tasks.json file from template** .</span></span>

1. <span data-ttu-id="77f98-117">В диалоговом окне **Выбор шаблона задачи** выберите **.NET Core** .</span><span class="sxs-lookup"><span data-stu-id="77f98-117">In the **Select a Task Template** dialog, choose **.NET Core** .</span></span>

<span data-ttu-id="77f98-118">Если файл `tasks.json` еще не существует, он будет создан.</span><span class="sxs-lookup"><span data-stu-id="77f98-118">A new `tasks.json` file is created if one doesn't exist yet.</span></span>

<span data-ttu-id="77f98-119">Чтобы протестировать задачу сборки, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="77f98-119">To test your build task:</span></span>

1. <span data-ttu-id="77f98-120">В **палитре команд** выполните команду **Выполнить задачу сборки** .</span><span class="sxs-lookup"><span data-stu-id="77f98-120">In the **Command Palette** , run the **Run Build Task** command.</span></span>

1. <span data-ttu-id="77f98-121">В диалоговом окне **Выбор задачи сборки для выполнения** выберите **сборка** .</span><span class="sxs-lookup"><span data-stu-id="77f98-121">In the **Select the build task to run** dialog, choose **build** .</span></span>

### <a name="information-about-dll-files-being-locked"></a><span data-ttu-id="77f98-122">Сведения о блокировке файлов DLL</span><span class="sxs-lookup"><span data-stu-id="77f98-122">Information about DLL files being locked</span></span>

<span data-ttu-id="77f98-123">По умолчанию в случае успешной сборки выходные данные в терминале не выводятся.</span><span class="sxs-lookup"><span data-stu-id="77f98-123">By default, a successful build doesn't show output in the terminal pane.</span></span> <span data-ttu-id="77f98-124">Если вы видите выходные данные c текстом **Файл проекта не существует** , следует изменить файл `tasks.json`.</span><span class="sxs-lookup"><span data-stu-id="77f98-124">If you see output that contains the text **Project file doesn't exist** , you should edit the `tasks.json` file.</span></span> <span data-ttu-id="77f98-125">Включите явный путь к проекту C# в виде `"${workspaceFolder}/myModule"`.</span><span class="sxs-lookup"><span data-stu-id="77f98-125">Include the explicit path to the C# project expressed as `"${workspaceFolder}/myModule"`.</span></span> <span data-ttu-id="77f98-126">В данном примере `myModule` — это имя папки проекта.</span><span class="sxs-lookup"><span data-stu-id="77f98-126">In this example, `myModule` is the name of the project folder.</span></span> <span data-ttu-id="77f98-127">Этот элемент должен следовать после элемента `build` в списке `args` следующим образом:</span><span class="sxs-lookup"><span data-stu-id="77f98-127">This entry must go after the `build` entry in the `args` list as follows:</span></span>

```json
    {
        "label": "build",
        "command": "dotnet",
        "type": "shell",
        "args": [
            "build",
            "${workspaceFolder}/myModule",
            // Ask dotnet build to generate full paths for file names.
            "/property:GenerateFullPaths=true",
            // Do not generate summary otherwise it leads to duplicate errors in Problems panel
            "/consoleloggerparameters:NoSummary",
        ],
        "group": "build",
        "presentation": {
            "reveal": "silent"
        },
        "problemMatcher": "$msCompile"
    }
```

<span data-ttu-id="77f98-128">При отладке библиотека DLL модуля импортируется в сеанс PowerShell в терминале VS Code.</span><span class="sxs-lookup"><span data-stu-id="77f98-128">When debugging, your module DLL is imported into the PowerShell session in the VS Code terminal.</span></span> <span data-ttu-id="77f98-129">При этом она блокируется.</span><span class="sxs-lookup"><span data-stu-id="77f98-129">The DLL becomes locked.</span></span> <span data-ttu-id="77f98-130">Если запустить задачу сборки, не закрывая сеанс терминала, появится следующее сообщение:</span><span class="sxs-lookup"><span data-stu-id="77f98-130">The following message is displayed when you run the build task without closing the terminal session:</span></span>

```Output
Could not copy "obj\Debug\netstandard2.0\myModule.dll" to "bin\Debug\netstandard2.0\myModule.dll"`.
```

<span data-ttu-id="77f98-131">Перед перестроением необходимо закрыть сеансы терминала.</span><span class="sxs-lookup"><span data-stu-id="77f98-131">Terminal sessions must be closed before you rebuild.</span></span>

## <a name="setting-up-the-debugger"></a><span data-ttu-id="77f98-132">Настройка отладчика</span><span class="sxs-lookup"><span data-stu-id="77f98-132">Setting up the debugger</span></span>

<span data-ttu-id="77f98-133">Чтобы отладить командлет PowerShell, необходимо настроить пользовательскую конфигурацию запуска.</span><span class="sxs-lookup"><span data-stu-id="77f98-133">To debug the PowerShell cmdlet, you need to set up a custom launch configuration.</span></span> <span data-ttu-id="77f98-134">Она используется в следующих целях:</span><span class="sxs-lookup"><span data-stu-id="77f98-134">This configuration is used to:</span></span>

- <span data-ttu-id="77f98-135">сборка исходного кода;</span><span class="sxs-lookup"><span data-stu-id="77f98-135">Build your source code</span></span>
- <span data-ttu-id="77f98-136">запуск PowerShell с загруженным модулем;</span><span class="sxs-lookup"><span data-stu-id="77f98-136">Start PowerShell with your module loaded</span></span>
- <span data-ttu-id="77f98-137">продолжение работы PowerShell в области терминала.</span><span class="sxs-lookup"><span data-stu-id="77f98-137">Leave PowerShell open in the terminal pane</span></span>

<span data-ttu-id="77f98-138">При вызове командлета в рамках сеанса терминала отладчик прерывает выполнение в точках останова, установленных в исходном коде.</span><span class="sxs-lookup"><span data-stu-id="77f98-138">When you invoke your cmdlet in the terminal session, the debugger stops at any breakpoints set in your source code.</span></span>

### <a name="configuring-launchjson-for-powershell-core"></a><span data-ttu-id="77f98-139">Настройка файла launch.json для PowerShell Core</span><span class="sxs-lookup"><span data-stu-id="77f98-139">Configuring launch.json for PowerShell Core</span></span>

1. <span data-ttu-id="77f98-140">Установите расширение [C# для Visual Studio Code][].</span><span class="sxs-lookup"><span data-stu-id="77f98-140">Install the [C# for Visual Studio Code][] extension</span></span>

1. <span data-ttu-id="77f98-141">В области "Отладка" добавьте конфигурацию отладки.</span><span class="sxs-lookup"><span data-stu-id="77f98-141">In the Debug pane, add a debug configuration</span></span>

1. <span data-ttu-id="77f98-142">В диалоговом окне `Select environment` выберите `.NET Core`.</span><span class="sxs-lookup"><span data-stu-id="77f98-142">In the `Select environment` dialog, choose `.NET Core`</span></span>

1. <span data-ttu-id="77f98-143">В редакторе откроется файл `launch.json`.</span><span class="sxs-lookup"><span data-stu-id="77f98-143">The `launch.json` file is opened in the editor.</span></span> <span data-ttu-id="77f98-144">Установив курсор внутри массива `configurations`, вы увидите средство выбора `configuration`.</span><span class="sxs-lookup"><span data-stu-id="77f98-144">With your cursor inside the `configurations` array, you see the `configuration` picker.</span></span> <span data-ttu-id="77f98-145">Если этот список не появляется, выберите **Добавить конфигурацию** .</span><span class="sxs-lookup"><span data-stu-id="77f98-145">If you don't see this list, select **Add Configuration** .</span></span>

1. <span data-ttu-id="77f98-146">Чтобы создать конфигурацию отладки по умолчанию, выберите **Запустить консольное приложение .NET Core** .</span><span class="sxs-lookup"><span data-stu-id="77f98-146">To create a default debug configuration, select **Launch .NET Core Console App** :</span></span>

   ![Запуск консольного приложения .NET Core](media/using-vscode-for-debugging-compiled-cmdlets/add-configuration-dialog.png)

1. <span data-ttu-id="77f98-148">Измените поля `name`, `program`, `args` и `console` следующим образом:</span><span class="sxs-lookup"><span data-stu-id="77f98-148">Edit the `name`, `program`, `args`, and `console` fields as follows:</span></span>

   ```json
    {
        "name": "PowerShell cmdlets: pwsh",
        "type": "coreclr",
        "request": "launch",
        "preLaunchTask": "build",
        "program": "pwsh",
        "args": [
            "-NoExit",
            "-NoProfile",
            "-Command",
            "Import-Module ${workspaceFolder}/myModule/bin/Debug/netstandard2.0/myModule.dll",
        ],
        "cwd": "${workspaceFolder}",
        "stopAtEntry": false,
        "console": "integratedTerminal"
    }
   ```

<span data-ttu-id="77f98-149">Поле `program` используется для запуска программы `pwsh`, что позволяет выполнить отлаживаемый командлет.</span><span class="sxs-lookup"><span data-stu-id="77f98-149">The `program` field is used to launch `pwsh` so that the cmdlet being debugged can be run.</span></span> <span data-ttu-id="77f98-150">Аргумент `-NoExit` предотвращает выход из сеанса PowerShell сразу после импорта модуля.</span><span class="sxs-lookup"><span data-stu-id="77f98-150">The `-NoExit` argument prevents the PowerShell session from exiting as soon as the module is imported.</span></span>
<span data-ttu-id="77f98-151">Путь в аргументе `Import-Module` — это выходной путь сборки по умолчанию согласно руководству [Создание переносимых модулей][].</span><span class="sxs-lookup"><span data-stu-id="77f98-151">The path in the `Import-Module` argument is the default build output path when you've followed the [Writing Portable Modules][] guide.</span></span> <span data-ttu-id="77f98-152">Если вы создали манифест модуля (файл `.psd1`), следует использовать путь к нему.</span><span class="sxs-lookup"><span data-stu-id="77f98-152">If you've created a module manifest (`.psd1` file), you should use the path to that instead.</span></span> <span data-ttu-id="77f98-153">Разделитель пути `/` работает в Windows, Linux и macOS.</span><span class="sxs-lookup"><span data-stu-id="77f98-153">The `/` path separator works on Windows, Linux, and macOS.</span></span> <span data-ttu-id="77f98-154">Для выполнения отлаживаемых команд PowerShell необходимо использовать встроенный терминал.</span><span class="sxs-lookup"><span data-stu-id="77f98-154">You must use the integrated terminal to run the PowerShell commands you want to debug.</span></span>

> [!NOTE]
> <span data-ttu-id="77f98-155">Если отладчик не прерывает выполнение в каких-либо точках останова, поищите в консоли отладки Visual Studio Code следующую строку:</span><span class="sxs-lookup"><span data-stu-id="77f98-155">If the debugger doesn't stop at any breakpoints, look in the Visual Studio Code Debug Console for a line that says:</span></span>
>
> ```
> Loaded '/path/to/myModule.dll'. Skipped loading symbols. Module is optimized and the debugger option 'Just My Code' is enabled.
> ```
>
> <span data-ttu-id="77f98-156">Если она есть, добавьте `"justMyCode": false` в конфигурацию запуска (на том же уровне, что и `"console": "integratedTerminal"`).</span><span class="sxs-lookup"><span data-stu-id="77f98-156">If you see this, add `"justMyCode": false` to your launch config (at the same level as `"console": "integratedTerminal"`.</span></span>

### <a name="configuring-launchjson-for-windows-powershell"></a><span data-ttu-id="77f98-157">Настройка файла launch.json для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="77f98-157">Configuring launch.json for Windows PowerShell</span></span>

<span data-ttu-id="77f98-158">Эта конфигурация запуска предназначена для тестирования командлетов в Windows PowerShell (`powershell.exe`).</span><span class="sxs-lookup"><span data-stu-id="77f98-158">This launch configuration works for testing your cmdlets in Windows PowerShell (`powershell.exe`).</span></span>
<span data-ttu-id="77f98-159">Создайте еще одну конфигурацию запуска со следующими изменениями:</span><span class="sxs-lookup"><span data-stu-id="77f98-159">Create a second launch configuration with the following changes:</span></span>

1. <span data-ttu-id="77f98-160">переменная `name` должна иметь значение `PowerShell cmdlets: powershell`;</span><span class="sxs-lookup"><span data-stu-id="77f98-160">`name` should be `PowerShell cmdlets: powershell`</span></span>

1. <span data-ttu-id="77f98-161">переменная `type` должна иметь значение `clr`;</span><span class="sxs-lookup"><span data-stu-id="77f98-161">`type` should be `clr`</span></span>

1. <span data-ttu-id="77f98-162">переменная `program` должна иметь значение `powershell`;</span><span class="sxs-lookup"><span data-stu-id="77f98-162">`program` should be `powershell`</span></span>

   <span data-ttu-id="77f98-163">Он должен выглядеть так:</span><span class="sxs-lookup"><span data-stu-id="77f98-163">It should look like this:</span></span>

   ```json
    {
        "name": "PowerShell cmdlets: powershell",
        "type": "clr",
        "request": "launch",
        "preLaunchTask": "build",
        "program": "powershell",
        "args": [
            "-NoExit",
            "-NoProfile",
            "-Command",
            "Import-Module ${workspaceFolder}/myModule/bin/Debug/netstandard2.0/myModule.dll",
        ],
        "cwd": "${workspaceFolder}",
        "stopAtEntry": false,
        "console": "integratedTerminal"
    }
   ```

## <a name="launching-a-debugging-session"></a><span data-ttu-id="77f98-164">Запуск сеанса отладки</span><span class="sxs-lookup"><span data-stu-id="77f98-164">Launching a debugging session</span></span>

<span data-ttu-id="77f98-165">Теперь все готово для начала отладки.</span><span class="sxs-lookup"><span data-stu-id="77f98-165">Now everything is ready to begin debugging.</span></span>

- <span data-ttu-id="77f98-166">Установите точку останова в исходном коде на командлете, который необходимо отладить.</span><span class="sxs-lookup"><span data-stu-id="77f98-166">Place a breakpoint in the source code for the cmdlet you want to debug:</span></span>

  ![Точка останова отображается в виде красной точки во внутреннем поле.](media/using-vscode-for-debugging-compiled-cmdlets/set-breakpoint.png)

- <span data-ttu-id="77f98-168">Убедитесь в том, что в раскрывающемся меню конфигурации в представлении **Отладка** выбрана соответствующая конфигурация **командлетов PowerShell** :</span><span class="sxs-lookup"><span data-stu-id="77f98-168">Ensure that the relevant **PowerShell cmdlets** configuration is selected in the configuration drop-down menu in the **Debug** view:</span></span>

  ![Выбор конфигурации запуска](media/using-vscode-for-debugging-compiled-cmdlets/select-launch-configuration.png)

- <span data-ttu-id="77f98-170">Нажмите клавишу <kbd>F5</kbd> или кнопку **Начать отладку** .</span><span class="sxs-lookup"><span data-stu-id="77f98-170">Press <kbd>F5</kbd> or click on the **Start Debugging** button</span></span>

- <span data-ttu-id="77f98-171">Перейдите в область терминала и вызовите командлет:</span><span class="sxs-lookup"><span data-stu-id="77f98-171">Switch to the terminal pane and invoke your cmdlet:</span></span>

  ![Вызов командлета](media/using-vscode-for-debugging-compiled-cmdlets/invoke-the-cmdlet.png)

- <span data-ttu-id="77f98-173">Выполнение прервется в точке останова:</span><span class="sxs-lookup"><span data-stu-id="77f98-173">Execution stops at the breakpoint:</span></span>

  ![Прерывание выполнения в точке останова](media/using-vscode-for-debugging-compiled-cmdlets/stopped-at-breakpoint.png)

<span data-ttu-id="77f98-175">Вы можете выполнять исходный код пошагово, проверять переменные и стек вызовов.</span><span class="sxs-lookup"><span data-stu-id="77f98-175">You can step through the source code, inspect variables, and inspect the call stack.</span></span>

<span data-ttu-id="77f98-176">Чтобы завершить отладку, щелкните **Остановить** на панели инструментов отладки или нажмите клавиши <kbd>SHIFT</kbd>-<kbd>F5</kbd>.</span><span class="sxs-lookup"><span data-stu-id="77f98-176">To end debugging, click **Stop** in the debug toolbar or press <kbd>Shift</kbd>-<kbd>F5</kbd>.</span></span> <span data-ttu-id="77f98-177">Оболочка, используемая для отладки, завершит работу и снимет блокировку со скомпилированного файла DLL.</span><span class="sxs-lookup"><span data-stu-id="77f98-177">The shell used for debugging exits and releases the lock on the compiled DLL file.</span></span>

<!-- reference links -->
[Debugging in Visual Studio Code]: https://code.visualstudio.com/docs/editor/debugging (Отладка в Visual Studio Code)
[Удаленные редактирование и отладка в Visual Studio Code]: using-vscode-for-remote-editing-and-debugging.md
[Using Visual Studio Code for remote editing and debugging]: using-vscode-for-remote-editing-and-debugging.md
[Создание переносимых модулей]: ../writing-portable-modules.md
[Writing Portable Modules]: ../writing-portable-modules.md
[C# для Visual Studio Code]: https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp
[C# for Visual Studio Code]: https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp
