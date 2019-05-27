---
title: Использование Visual Studio Code для разработки в PowerShell
description: Использование Visual Studio Code для разработки в PowerShell
ms.date: 08/06/2018
ms.openlocfilehash: 5badffd49252e0d72ae2c20d3147ad4b1e92d5ed
ms.sourcegitcommit: cf1a281cce9f7239c440c90f8b2798d32a13778d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2019
ms.locfileid: "65882574"
---
# <a name="using-visual-studio-code-for-powershell-development"></a>Использование Visual Studio Code для разработки в PowerShell

В дополнение к [интегрированной среде сценариев PowerShell][ise] продукт PowerShell также хорошо поддерживается в Visual Studio Code.
Кроме того, интегрированная среда сценариев не поддерживается в PowerShell Core, хотя Visual Studio Code поддерживается для PowerShell Core на всех платформах (Windows, macOS и Linux)

Вы можете использовать Visual Studio Code для Windows вместе с PowerShell версии 5 в Windows 10 или установить [Windows Management Framework 5.0 RTM](https://www.microsoft.com/en-us/download/details.aspx?id=50395) для более низких версий Windows (например, Windows 8.1 и т. д.).

Перед запуском убедитесь, что PowerShell установлен в системе.
Сведения о современных рабочих нагрузках для Windows, macOS и Linux см. в следующих разделах:

- [Установка PowerShell Core в Linux][install-pscore-linux]
- [Установка PowerShell Core в macOS][install-pscore-macos]
- [Установка PowerShell Core в Windows][install-pscore-windows]

Сведения о традиционных рабочих нагрузках Windows PowerShell см. в разделе [Установка Windows PowerShell][install-winps].

## <a name="editing-with-visual-studio-code"></a>Редактирование с помощью Visual Studio Code

### <a name="1-installing-visual-studio-codehttpscodevisualstudiocomdocssetupsetup-overview"></a>[1. Установка Visual Studio Code](https://code.visualstudio.com/Docs/setup/setup-overview)

- **Linux**: следуйте инструкциям по установке на странице [Запуск VS Code в Linux](https://code.visualstudio.com/docs/setup/linux).

- **macOS**: следуйте инструкциям по установке на странице [Запуск VS Code в macOS](https://code.visualstudio.com/docs/setup/mac).

  > [!IMPORTANT]
  > В macOS нужно установить OpenSSL для правильной работы расширения PowerShell.
  > Для этого проще всего установить [Homebrew](https://brew.sh/), а затем запустить `brew install openssl`.
  > Теперь VS Code сможет загрузить расширение PowerShell правильно.

- **Windows**: следуйте инструкциям по установке на странице [Запуск VS Code в Windows](https://code.visualstudio.com/docs/setup/windows).

### <a name="2-installing-powershell-extension"></a>2. Установка расширения PowerShell

- Запустите Visual Studio Code следующим образом:
  - **Windows**: введите `code` в сеансе PowerShell.
  - **Linux**: введите `code` в терминале.
  - **macOS**: введите `code` в терминале.

- Запустите **Quick Open**, нажав клавиши **CTRL+P** (**CMD+P** на Mac).
- В Quick Open введите `ext install powershell` и нажмите клавишу **ВВОД**.
- На боковой панели открывается представление **Расширения**. Выберите расширение PowerShell корпорации Майкрософт.
  Отображается примерно следующее:

  ![VSCode](../../images/vscode.png)

- Нажмите кнопку **Установить** для расширения PowerShell корпорации Майкрософт.
- После установки кнопка **Установить** изменяется на **Перезагрузить**.
  Нажмите кнопку **Перезагрузить**.
- После перезагрузки Visual Studio Code можно приступать к редактированию.

Например, чтобы создать файл, выберите **Файл -> Создать**.
Чтобы сохранить его, выберите **Файл -> Сохранить** и укажите имя файла, например `HelloWorld.ps1`.
Чтобы закрыть файл, щелкните "x" рядом с его именем.
Чтобы завершить работу Visual Studio Code, выберите **Файл -> Выйти**.

### <a name="installing-the-powershell-extension-on-restricted-systems"></a>Установка расширения PowerShell в системах с ограниченным доступом

Некоторые системы настроены таким образом, что требуется проверка всех подписей кода, и, следовательно, одобрение службы редактора PowerShell вручную для запуска в системе.
Обновление групповой политики, которое изменяет политику выполнения, является вероятной причиной того, что после установки расширения PowerShell вы сталкиваетесь со следующей ошибкой.

```
Language server startup failed.
```

Чтобы вручную утвердить службы редактора PowerShell и, следовательно, расширение PowerShell для VSCode, откройте командную строку PowerShell и выполните следующий код.

```powershell
Import-Module $HOME\.vscode\extensions\ms-vscode.powershell*\modules\PowerShellEditorServices\PowerShellEditorServices.psd1
```

Вы увидите подсказку "Не удается проверить издателя. Вы действительно хотите запустить эту программу?"
Введите `R` для запуска файла. Затем откройте Visual Studio Code и убедитесь, что расширение PowerShell работает правильно. Если у вас все еще есть проблемы с началом работы, сообщите нам об этом на [GitHub](https://github.com/PowerShell/vscode-powershell/issues).

#### <a name="choosing-a-version-of-powershell-to-use-with-the-extension"></a>Выбор версии PowerShell для использования с расширением

Благодаря одновременной установке PowerShell Core и Windows PowerShell теперь можно использовать конкретную версию PowerShell с расширением PowerShell. Выберите версию, сделав следующее:

1. Откройте палитру команд (<kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> на Windows и Linux, <kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> в macOS).
1. Выполните поиск по слову "Сеанс".
1. Щелкните PowerShell: Show Session Menu (PowerShell: показать меню сеансов).
1. Выберите версию PowerShell, которую хотите использовать, в списке, например PowerShell Core.

>[!IMPORTANT]
> Этот компонент проверяет несколько известных расположений в разных операционных системах, чтобы найти расположения установки PowerShell. Если вы установили PowerShell в нетипичном расположении, оно может первоначально не отобразиться в меню сеансов. Вы можете расширить меню сеансов, [добавив собственные пользовательские пути](#adding-your-own-powershell-paths-to-the-session-menu), как описано ниже.

>[!NOTE]
> Есть еще один способ перехода в меню сеансов. В правом нижнем углу открытого файла PowerShell в редакторе виден зеленый номер версии. Щелкнув его, вы перейдете в меню сеансов.

##### <a name="adding-your-own-powershell-paths-to-the-session-menu"></a>Добавление собственных путей PowerShell в меню сеансов

В меню сеансов можно добавить другие пути к исполнимому файлу PowerShell с помощью VS Code.

Добавьте элемент в список `powershell.powerShellAdditionalExePaths` или создайте список, если его нет в `settings.json`:

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

Каждый элемент должен иметь следующее:

* `exePath`: Путь к исполняемому файлу `pwsh` или `powershell`.
* `versionName`: Текст, который будет отображаться в меню сеансов.

Вы можете задать используемую версию PowerShell по умолчанию, задав параметр `powershell.powerShellDefaultVersion` для текста, отображаемого в меню сеансов (`versionName` в последнем параметре):

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

Задав этот параметр, перезапустите Visual Studio Code или используйте действие палитры команд Developer: Reload Window (Разработчик: перезагрузить окно) для перезагрузки текущего окна VS Code.

Открыв меню сеансов, вы увидите дополнительные версии PowerShell.

> [!NOTE]
> Если вы создаете PowerShell из исходного кода, это отличный способ протестировать локальную сборку PowerShell.

#### <a name="configuration-settings-for-visual-studio-code"></a>Параметры конфигурации для Visual Studio Code

Следуя инструкциям в предыдущем абзаце, вы можете добавить параметры конфигурации в `settings.json`.

Мы рекомендуем использовать следующие параметры конфигурации для Visual Studio Code:

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

Если вы не хотите, чтобы эти параметры влияли на все типы файлов, VSCode также позволяет задавать конфигурации для каждого языка отдельно. Параметр для конкретного языка можно создать, поместив параметры в поле `[<language-name>]`. Например:

```json
"[powershell]": {
    "files.encoding": "utf8bom",
    "files.autoGuessEncoding": true
}
```

Дополнительные сведения о кодировке файлов в VS Code см. в [этой статье](understanding-file-encoding.md).

## <a name="debugging-with-visual-studio-code"></a>Отладка с помощью Visual Studio Code

### <a name="no-workspace-debugging"></a>Отладка без рабочей области

Начиная с Visual Studio Code версии 1.9, вы можете отлаживать сценарии PowerShell, не открывая папку со сценарием PowerShell. Откройте файл сценария PowerShell с помощью команды **Файл -> Открыть файл...**, установите точку останова на строке (нажав клавишу F9) и нажмите клавишу F5 для запуска отладки. Отображается панель действий отладки, позволяющая прервать работу отладчика, возобновить отладку, выполнить ее пошагово или остановить.

### <a name="workspace-debugging"></a>Отладка с рабочей областью

Отладка с рабочей областью обозначает отладку в контексте папки, которую вы открыли в Visual Studio Code с помощью команды **Открыть папку...** из меню **Файл**.
Обычно открытая папка является папкой проекта PowerShell и (или) корнем репозитория Git.

Даже в этом режиме вы можете начать отладку выбранного сценария PowerShell, просто нажав клавишу F5.
Однако отладка с рабочей областью позволяет задать несколько конфигураций отладки, отличных от простой отладки открытого файла.
Например, можно добавить конфигурации следующего характера:

- Запуск тестов Pester в отладчике
- Запуск определенного файла с аргументами в отладчике
- Запуск интерактивного сеанса в отладчике
- Подключение отладчика к хост-процессу PowerShell

Выполните следующие действия, чтобы создать файл конфигурации отладки:

  1. Откройте представление **Отладка**, нажав клавиши **CTRL+SHIFT+D** (**CMD+SHIFT+D** на Mac).
  2. Щелкните значок с шестеренкой **Настройка** на панели инструментов.
  3. Visual Studio Code предлагает вам **выбрать среду**. Выберите **PowerShell**.

  При этом Visual Studio Code создает каталог и файл ".vscode\launch.json" в корневой папке рабочей области.
  Именно там хранится ваша конфигурация отладки. Если ваши файлы хранятся в репозитории Git, скорее всего, вы захотите зафиксировать файл launch.json.
  Файла launch.json содержит следующее:

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

  Это представляет типичные сценарии отладки.
  Однако при открытии этого файла в редакторе отображается кнопка **Добавить конфигурацию...**.
  Можете нажать ее, чтобы добавить дополнительные конфигурации отладки PowerShell. Одной из полезных конфигураций является **PowerShell: Launch Script** (Запустить сценарий).
  С помощью этой конфигурации можно указать определенный файл с дополнительными аргументами, которые нужно запускать при каждом нажатии клавиши F5 независимо от того, какой именно файл активен в редакторе.

  После задания конфигурации отладки можно указать конфигурацию, используемую во время сеанса отладки, выбрав ее в раскрывающемся списке конфигураций отладки на панели инструментов представления **Отладка**.

Существует несколько блогов, которые могут оказаться полезными при начале работы с расширением PowerShell для Visual Studio Code:

- [Расширение PowerShell][ps-extension]
- [Написание и отладка в сценариев PowerShell в Visual Studio Code][debug]
- [Руководство по отладке Visual Studio Code][vscode-guide]
- [Отладка PowerShell в Visual Studio Code][ps-vscode]
- [Приступая к разработке PowerShell в Visual Studio Code][getting-started]
- [Функции редактирования Visual Studio Code для разработки PowerShell. Часть 1][editing-part1]
- [Функции редактирования Visual Studio Code для разработки PowerShell. Часть 2][editing-part2]
- [Отладка сценария PowerShell в Visual Studio Code. Часть 1][debugging-part1]
- [Отладка сценария PowerShell в Visual Studio Code. Часть 2][debugging-part2]

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

## <a name="powershell-extension-for-visual-studio-code"></a>Расширение PowerShell для Visual Studio Code

Исходный код расширения PowerShell доступен на [GitHub](https://github.com/PowerShell/vscode-powershell).
