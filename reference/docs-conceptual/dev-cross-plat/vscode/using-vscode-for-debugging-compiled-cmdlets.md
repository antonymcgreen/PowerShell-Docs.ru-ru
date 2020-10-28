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
# <a name="using-visual-studio-code-to-debug-compiled-cmdlets"></a>Отладка скомпилированных командлетов с помощью Visual Studio Code

В этом руководстве описывается, как выполнять интерактивную отладку исходного кода на C# для скомпилированного модуля PowerShell с помощью Visual Studio Code (VS Code) и расширения C#.

Предполагается, что у вас уже есть некоторый опыт работы с отладчиком Visual Studio Code.

- Общие сведения об отладчике VS Code см. в статье [Отладка в Visual Studio Code][].

- Примеры отладки файлов скриптов и модулей PowerShell см. в статье [Удаленные редактирование и отладка в Visual Studio Code][].

В этом руководстве предполагается, что вы прочитали и выполнили инструкции в руководстве [Создание переносимых модулей][].

## <a name="creating-a-build-task"></a>Создание задачи сборки

Выполняйте автоматическую сборку проекта перед запуском сеанса отладки. Это позволяет гарантировать, что вы отлаживаете последнюю версию кода.

Настройте задачу сборки.

1. В **палитре команд** выполните команду **Настроить задачу сборки по умолчанию** .

   ![Выполнение команды "Настроить задачу сборки по умолчанию"](media/using-vscode-for-debugging-compiled-cmdlets/configure-default-build-task.png)

1. В диалоговом окне **Выбор задачи для настройки** выберите **Создать файл tasks.json из шаблона** .

1. В диалоговом окне **Выбор шаблона задачи** выберите **.NET Core** .

Если файл `tasks.json` еще не существует, он будет создан.

Чтобы протестировать задачу сборки, выполните указанные ниже действия.

1. В **палитре команд** выполните команду **Выполнить задачу сборки** .

1. В диалоговом окне **Выбор задачи сборки для выполнения** выберите **сборка** .

### <a name="information-about-dll-files-being-locked"></a>Сведения о блокировке файлов DLL

По умолчанию в случае успешной сборки выходные данные в терминале не выводятся. Если вы видите выходные данные c текстом **Файл проекта не существует** , следует изменить файл `tasks.json`. Включите явный путь к проекту C# в виде `"${workspaceFolder}/myModule"`. В данном примере `myModule` — это имя папки проекта. Этот элемент должен следовать после элемента `build` в списке `args` следующим образом:

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

При отладке библиотека DLL модуля импортируется в сеанс PowerShell в терминале VS Code. При этом она блокируется. Если запустить задачу сборки, не закрывая сеанс терминала, появится следующее сообщение:

```Output
Could not copy "obj\Debug\netstandard2.0\myModule.dll" to "bin\Debug\netstandard2.0\myModule.dll"`.
```

Перед перестроением необходимо закрыть сеансы терминала.

## <a name="setting-up-the-debugger"></a>Настройка отладчика

Чтобы отладить командлет PowerShell, необходимо настроить пользовательскую конфигурацию запуска. Она используется в следующих целях:

- сборка исходного кода;
- запуск PowerShell с загруженным модулем;
- продолжение работы PowerShell в области терминала.

При вызове командлета в рамках сеанса терминала отладчик прерывает выполнение в точках останова, установленных в исходном коде.

### <a name="configuring-launchjson-for-powershell-core"></a>Настройка файла launch.json для PowerShell Core

1. Установите расширение [C# для Visual Studio Code][].

1. В области "Отладка" добавьте конфигурацию отладки.

1. В диалоговом окне `Select environment` выберите `.NET Core`.

1. В редакторе откроется файл `launch.json`. Установив курсор внутри массива `configurations`, вы увидите средство выбора `configuration`. Если этот список не появляется, выберите **Добавить конфигурацию** .

1. Чтобы создать конфигурацию отладки по умолчанию, выберите **Запустить консольное приложение .NET Core** .

   ![Запуск консольного приложения .NET Core](media/using-vscode-for-debugging-compiled-cmdlets/add-configuration-dialog.png)

1. Измените поля `name`, `program`, `args` и `console` следующим образом:

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

Поле `program` используется для запуска программы `pwsh`, что позволяет выполнить отлаживаемый командлет. Аргумент `-NoExit` предотвращает выход из сеанса PowerShell сразу после импорта модуля.
Путь в аргументе `Import-Module` — это выходной путь сборки по умолчанию согласно руководству [Создание переносимых модулей][]. Если вы создали манифест модуля (файл `.psd1`), следует использовать путь к нему. Разделитель пути `/` работает в Windows, Linux и macOS. Для выполнения отлаживаемых команд PowerShell необходимо использовать встроенный терминал.

> [!NOTE]
> Если отладчик не прерывает выполнение в каких-либо точках останова, поищите в консоли отладки Visual Studio Code следующую строку:
>
> ```
> Loaded '/path/to/myModule.dll'. Skipped loading symbols. Module is optimized and the debugger option 'Just My Code' is enabled.
> ```
>
> Если она есть, добавьте `"justMyCode": false` в конфигурацию запуска (на том же уровне, что и `"console": "integratedTerminal"`).

### <a name="configuring-launchjson-for-windows-powershell"></a>Настройка файла launch.json для Windows PowerShell

Эта конфигурация запуска предназначена для тестирования командлетов в Windows PowerShell (`powershell.exe`).
Создайте еще одну конфигурацию запуска со следующими изменениями:

1. переменная `name` должна иметь значение `PowerShell cmdlets: powershell`;

1. переменная `type` должна иметь значение `clr`;

1. переменная `program` должна иметь значение `powershell`;

   Он должен выглядеть так:

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

## <a name="launching-a-debugging-session"></a>Запуск сеанса отладки

Теперь все готово для начала отладки.

- Установите точку останова в исходном коде на командлете, который необходимо отладить.

  ![Точка останова отображается в виде красной точки во внутреннем поле.](media/using-vscode-for-debugging-compiled-cmdlets/set-breakpoint.png)

- Убедитесь в том, что в раскрывающемся меню конфигурации в представлении **Отладка** выбрана соответствующая конфигурация **командлетов PowerShell** :

  ![Выбор конфигурации запуска](media/using-vscode-for-debugging-compiled-cmdlets/select-launch-configuration.png)

- Нажмите клавишу <kbd>F5</kbd> или кнопку **Начать отладку** .

- Перейдите в область терминала и вызовите командлет:

  ![Вызов командлета](media/using-vscode-for-debugging-compiled-cmdlets/invoke-the-cmdlet.png)

- Выполнение прервется в точке останова:

  ![Прерывание выполнения в точке останова](media/using-vscode-for-debugging-compiled-cmdlets/stopped-at-breakpoint.png)

Вы можете выполнять исходный код пошагово, проверять переменные и стек вызовов.

Чтобы завершить отладку, щелкните **Остановить** на панели инструментов отладки или нажмите клавиши <kbd>SHIFT</kbd>-<kbd>F5</kbd>. Оболочка, используемая для отладки, завершит работу и снимет блокировку со скомпилированного файла DLL.

<!-- reference links -->
[Debugging in Visual Studio Code]: https://code.visualstudio.com/docs/editor/debugging (Отладка в Visual Studio Code)
[Удаленные редактирование и отладка в Visual Studio Code]: using-vscode-for-remote-editing-and-debugging.md
[Создание переносимых модулей]: ../writing-portable-modules.md
[C# для Visual Studio Code]: https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp
