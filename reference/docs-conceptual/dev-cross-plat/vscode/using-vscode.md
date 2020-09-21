---
title: Использование Visual Studio Code для разработки в PowerShell
description: Использование Visual Studio Code для разработки в PowerShell
ms.date: 11/07/2019
ms.openlocfilehash: 181746e7d3df2880223d1f15a0c8b99b324f5b98
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87782537"
---
# <a name="using-visual-studio-code-for-powershell-development"></a>Использование Visual Studio Code для разработки в PowerShell

[Visual Studio Code][vscode] — это кросс-платформенный редактор скриптов, созданный корпорацией Майкрософт. Наряду с [расширением PowerShell][psext] он предоставляет широкие интерактивные возможности редактирования скриптов, упрощая написание надежных скриптов PowerShell. Редактор Visual Studio Code с расширением PowerShell рекомендуется использовать для написания сценариев PowerShell.

Он поддерживает следующие версии PowerShell:

- PowerShell 7 и последующие версии (Windows, macOS и Linux);
- PowerShell Core 6 (Windows, macOS и Linux);
- Windows PowerShell 5.1 (только для Windows).

> [!NOTE]
> Visual Studio Code отличается от [Visual Studio][].

## <a name="getting-started"></a>Начало работы

Перед запуском убедитесь, что оболочка PowerShell установлена в системе. Сведения о современных рабочих нагрузках для Windows, macOS и Linux см. по следующим ссылкам:

- [Установка PowerShell в Linux][install-pscore-linux]
- [Установка PowerShell в macOS][install-pscore-macos]
- [Установка PowerShell в Windows][install-pscore-windows]

Сведения о традиционных рабочих нагрузках Windows PowerShell см. в разделе [Установка Windows PowerShell][install-winps].

> [!IMPORTANT]
> [Интегрированная среда сценариев Windows PowerShell][ise] по-прежнему доступна для Windows, но функции для нее больше не разрабатываются. Интегрированная среда сценариев не работает с PowerShell 6 и более поздних версий. Как компонент Windows эта среда по-прежнему официально поддерживается для внесения критически важных исправлений, связанных с безопасностью и обслуживанием.
> Пока что мы не планируем удалять ее из Windows.

## <a name="editing-with-visual-studio-code"></a>Редактирование с помощью Visual Studio Code

1. Установите Visual Studio Code. Дополнительные сведения см. в статье [Setting up Visual Studio Code][vsc-setup] (Настройка Visual Studio Code).

   Доступны инструкции по установке на каждой платформе:

   - **Windows**: следуйте инструкциям по установке на странице [Запуск Visual Studio Code в Windows][vsc-setup-win].
   - **macOS**: следуйте инструкциям по установке на странице [Запуск Visual Studio Code в macOS][vsc-setup-macOS].
   - **Linux**: следуйте инструкциям по установке на странице [Запуск Visual Studio Code в Linux][vsc-setup-linux].

1. Установите расширение PowerShell.

   1. Запустите приложение Visual Studio Code, введя `code` в консоли или `code-insiders`, если вы установили Visual Studio Code Insiders.
   1. Запустите **Quick Open** в Windows или Linux, нажав клавиши <kbd>CTRL</kbd>+<kbd>P</kbd>. В macOS нажмите клавиши <kbd>CMD</kbd>+<kbd>P</kbd>.
   1. В Quick Open введите `ext install powershell` и нажмите клавишу **ВВОД**.
   1. На боковой панели открывается представление **Расширения**. Выберите расширение PowerShell корпорации Майкрософт.
      Откроется примерно следующий экран Visual Studio Code:

      ![Visual Studio Code — обзор расширения PowerShell](media/using-vscode/vscode.png)

   1. Нажмите кнопку **Установить** для расширения PowerShell корпорации Майкрософт.
   1. После установки кнопка **Установить** изменяется на **Reload** (Перезагрузить). Нажмите кнопку **Reload** (Перезагрузить).
   1. После перезагрузки Visual Studio Code можно приступать к редактированию.

Например, чтобы создать файл, выберите **Файл > Создать**. Чтобы сохранить его, выберите **Файл > Сохранить** и укажите имя файла, например `HelloWorld.ps1`. Чтобы закрыть файл, щелкните `X` рядом с его именем. Чтобы завершить работу с Visual Studio Code, выберите элементы **Файл > Выйти**.

### <a name="installing-the-powershell-extension-on-restricted-systems"></a>Установка расширения PowerShell в системах с ограниченным доступом

Некоторые системы настроены так, что требуют проверки всех подписей кода. Может появиться следующее сообщение об ошибке:

```
Language server startup failed.
```

Эта проблема может возникать, когда политика выполнения PowerShell задается групповой политикой Windows. Чтобы вручную утвердить службы редактора PowerShell и, следовательно, расширение PowerShell для Visual Studio Code, откройте командную строку PowerShell и выполните следующую команду:

```powershell
Import-Module $HOME\.vscode\extensions\ms-vscode.powershell*\modules\PowerShellEditorServices\PowerShellEditorServices.psd1
```

Вы увидите подсказку **Не удается проверить издателя. Вы действительно хотите запустить эту программу?** Введите `A` для запуска файла. Затем откройте Visual Studio Code и убедитесь, что расширение PowerShell работает правильно. Если у вас все еще есть проблемы с началом работы, сообщите нам об этом на [Раздел с описанием проблем на GitHub][].

> [!NOTE]
> Расширение PowerShell для Visual Studio Code не поддерживает запуск в ограниченном языковом режиме. Дополнительные сведения см. в [описании ошибки № 606 на GitHub][i606].

### <a name="choosing-a-version-of-powershell-to-use-with-the-extension"></a>Выбор версии PowerShell для использования с расширением

Благодаря одновременной установке PowerShell Core и Windows PowerShell теперь можно использовать определенную версию PowerShell с расширением PowerShell. Этот компонент проверяет несколько известных расположений в разных операционных системах, чтобы найти установки PowerShell.

Выберите версию, сделав следующее:

1. Откройте **палитру команд** в Windows и Linux (<kbd>CTRL</kbd>+<kbd>SHIFT</kbd>+<kbd>P</kbd>). В macOS нажмите клавиши <kbd>CMD</kbd>+<kbd>SHIFT</kbd>+<kbd>P</kbd>.
1. Выполните поиск по слову **Сеанс**.
1. Щелкните **PowerShell: Show Session Menu** (PowerShell: показать меню сеансов).
1. Выберите версию PowerShell, которую хотите использовать, из списка, например **PowerShell Core**.

Если вы установили PowerShell в нетипичном расположении, оно может первоначально не отобразиться в меню сеансов. Вы можете расширить меню сеансов, [добавив собственные пользовательские пути](#adding-your-own-powershell-paths-to-the-session-menu), как описано ниже.

> [!NOTE]
> Меню сеансов PowerShell также можно открыть, щелкнув номер версии, который показан зеленым шрифтом в правом нижнем углу строки состояния.

## <a name="configuration-settings-for-visual-studio-code"></a>Параметры конфигурации для Visual Studio Code

Прежде всего, если вы не знаете, как изменить параметры в Visual Studio Code, мы рекомендуем ознакомиться с [документацией по параметрам Visual Studio Code][vsc-settings].

После этого вы сможете добавить параметры конфигурации в `settings.json`.

```json
{
    "editor.renderWhitespace": "all",
    "editor.renderControlCharacters": true,
    "files.trimTrailingWhitespace": true,
    "files.encoding": "utf8bom",
    "files.autoGuessEncoding": true
}
```

Если вы не хотите, чтобы эти параметры влияли на файлы всех типов, Visual Studio Code также позволяет задавать конфигурации для каждого языка отдельно. Создать параметр для конкретного языка можно, поместив параметры в поле `[<language-name>]`. Пример:

```json
{
    "[powershell]": {
        "files.encoding": "utf8bom",
        "files.autoGuessEncoding": true
    }
}
```

> [!TIP]
> Дополнительные сведения о кодировке файлов в Visual Studio Code см. в статье [Основные сведения о кодировке файлов в VSCode и PowerShell][file-encoding].
>
> Также ознакомьтесь со статьей [Репликация функций интегрированной среды скриптов в Visual Studio Code][vsc-ise], в которой даны рекомендации по настройке Visual Studio Code для редактирования в PowerShell.

### <a name="adding-your-own-powershell-paths-to-the-session-menu"></a>Добавление собственных путей PowerShell в меню сеансов

В меню сеанса можно добавить другие пути к исполнимому файлу PowerShell с помощью [параметра Visual Studio Code](https://code.visualstudio.com/docs/getstarted/settings): `powershell.powerShellAdditionalExePaths`.

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

- `exePath`: Путь к исполняемому файлу `pwsh` или `powershell`.
- `versionName`: Текст, который будет отображаться в меню сеансов.

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

Задав этот параметр, перезапустите Visual Studio Code или перезагрузите текущее окно Visual Studio Code через**Палитру команд**, введя **Разработчик: Reload Window** (Разработчик: перезагрузить окно).

Открыв меню сеансов, вы увидите дополнительные версии PowerShell.

> [!NOTE]
> Если вы создаете PowerShell из исходного кода, это отличный способ протестировать локальную сборку PowerShell.

### <a name="using-an-older-version-of-the-powershell-extension-for-windows-powershell-v3-and-v4"></a>Использование более ранней версии расширения PowerShell для Windows PowerShell версий 3 и 4

Хотя текущее расширение PowerShell не поддерживает работу с [PowerShell версии 3 и 4][i1310], вы можете использовать последнюю версию расширения, которая поддерживает работу с третьей и четвертой версией.

> [!CAUTION]
> Дополнительные исправления для этой старой версии расширения не будут внесены. Она предоставляется без изменений, но доступна для вас, если вы все еще используете Windows PowerShell версии 3 или 4.

Сначала откройте панель расширений и найдите `PowerShell`. Затем щелкните значок шестеренки и выберите команду **Install another version...** (Установить другую версию...).

![Пункт меню — "Установить другую версию..."](media/using-vscode/install-another-version.png)

Затем выберите версию **2020.1.0**. Эта версия расширения — последняя версия, которую поддерживает Windows PowerShell версий 3 и 4. Обязательно добавьте следующий параметр, чтобы версия расширения не обновлялась автоматически:

```json
{
    "extensions.autoUpdate": false
}
```

Версия **2020.1.0** будет актуальной в ближайшем будущем, но в Visual Studio Code может появиться изменение, которое приведет к прекращению поддержки этой версии расширения. Учитывая это, а также отсутствие поддержки, мы рекомендуем:

- выполнить обновление до Windows PowerShell 5.1.
- установить среду PowerShell 7, которая доступна для параллельной установки с другими версиями Windows PowerShell и наилучшим образом подходит для расширения PowerShell.

## <a name="debugging-with-visual-studio-code"></a>Отладка с помощью Visual Studio Code

### <a name="no-workspace-debugging"></a>Отладка без рабочей области

Начиная с версии Visual Studio Code 1.9, вы можете отлаживать скрипты PowerShell, не открывая папку со скриптом PowerShell.

1. Откройте файл скрипта PowerShell с помощью команды **Файл > Открыть файл**.
1. Установите точку останова на строке и нажмите клавишу <kbd>F9</kbd>.
1. Нажмите клавишу <kbd>F5</kbd>, чтобы запустить отладку.

Откроется панель действий отладки, позволяющая прервать работу отладчика, возобновить отладку, выполнить ее пошагово или остановить.

### <a name="workspace-debugging"></a>Отладка с рабочей областью

Отладка с рабочей областью обозначает отладку в контексте папки, которую вы открыли с помощью команды **Открыть папку** из меню **Файл**. Открытая папка обычно является папкой проекта PowerShell или корнем репозитория Git. Отладка с рабочей областью позволяет задать несколько конфигураций отладки, а не просто выполнить отладку открытого файла.

Выполните следующие действия, чтобы создать файл конфигурации отладки:

1. Откройте представление **Отладка** в Windows или Linux (<kbd>CTRL</kbd>+<kbd>SHIFT</kbd>+<kbd>D</kbd>). В macOS нажмите клавиши <kbd>CMD</kbd>+<kbd>SHIFT</kbd>+<kbd>D</kbd>.
1. Щелкните ссылку **create a launch.json file** (Создать файл launch.json).
1. В окне запроса **Select Environment** (Выбор среды) выберите **PowerShell**.
1. Выберите тип отладки, который хотите использовать:

   - **Launch Current File** (Запуск текущего файла) — запуск и отладка файла в текущем активном окне редактора.
   - **Launch Script** (Запуск скрипта) — запуск и отладка указанного файла или команды.
   - **Interactive Session** (Интерактивный сеанс) — команды отладки, выполняемые из интегрированной консоли.
   - **Attach (Подключение)**  — подключение отладчика к выполняемому хост-процессу PowerShell.

Visual Studio Code создаст каталог и файл `.vscode\launch.json` в корневой папке рабочей области, где будет храниться конфигурация отладки. Если ваши файлы хранятся в репозитории Git, скорее всего, вы захотите зафиксировать файл `launch.json`. Содержимое файла `launch.json`:

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

Этот файл представляет типичные сценарии отладки. При открытии его в редакторе отображается кнопка **Добавить конфигурацию...** Можете нажать ее, чтобы добавить дополнительные конфигурации отладки PowerShell. Одной из полезных конфигураций является **PowerShell: Launch Script** (Запустить сценарий). С помощью этой конфигурации можно указать файл с дополнительными аргументами, которые используются при каждом нажатии клавиши <kbd>F5</kbd>, независимо от того, какой файл активен в редакторе.

После задания конфигурации отладки вы можете указать конфигурацию, используемую во время сеанса отладки, выбрав ее в раскрывающемся списке конфигураций отладки на панели инструментов представления **Отладка**.

## <a name="troubleshooting-the-powershell-extension-for-visual-studio-code"></a>Устранение проблем с расширением PowerShell для Visual Studio Code.

Если у вас возникли проблемы с использованием Visual Studio Code для разработки скриптов PowerShell, ознакомьтесь с [руководством по устранению неполадок][troubleshooting] на сайте GitHub.

## <a name="useful-resources"></a>Полезные ресурсы

Существует несколько видео и записей блогов, которые могут оказаться полезными при начале работы с расширением PowerShell для Visual Studio Code:

### <a name="videos"></a>Видео

- [Использование Visual Studio Code в качестве редактора PowerShell по умолчанию](https://youtu.be/bGn45vIeAMM)
- [Visual Studio Code: подробный обзор отладки сценариев PowerShell](https://youtu.be/cSbIXmlkr8o)

### <a name="blog-posts"></a>Записи блога

- [Расширение PowerShell][pscdn]
- [Написание и отладка в сценариев PowerShell в Visual Studio Code][debug]
- [Руководство по отладке Visual Studio Code][psdbgblog]
- [Отладка PowerShell в Visual Studio Code][psdbg-gh]
- [Приступая к разработке PowerShell в Visual Studio Code][getting-started]
- [Функции редактирования Visual Studio Code для разработки PowerShell. Часть 1][editing-part1]
- [Функции редактирования Visual Studio Code для разработки PowerShell. Часть 2][editing-part2]
- [Отладка сценария PowerShell в Visual Studio Code. Часть 1][debugging-part1]
- [Отладка сценария PowerShell в Visual Studio Code. Часть 2][debugging-part2]

## <a name="powershell-extension-project-source-code"></a>Исходный код проекта расширения PowerShell

Исходный код расширения PowerShell доступен на [GitHub][psext-src].

Если вы хотите принять участие в проекте в качестве разработчика, отправьте запрос на вытягивание. Чтобы приступить к работе, следуйте указаниям из [документации для разработчиков][dev-docs] на сайте GitHub.

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
[pscdn]:                  https://blogs.msdn.microsoft.com/cdndevs/2015/12/11/visual-studio-code-powershell-extension/

<!-- issues -->
[Раздел с описанием проблем на GitHub]:          https://github.com/PowerShell/vscode-powershell/issues
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
