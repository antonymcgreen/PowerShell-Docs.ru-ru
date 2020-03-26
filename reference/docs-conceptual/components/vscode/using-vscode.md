---
title: Использование Visual Studio Code для разработки в PowerShell
description: Использование Visual Studio Code для разработки в PowerShell
ms.date: 11/07/2019
ms.openlocfilehash: 86739970b58460bef9686a75bf0604d0605d4888
ms.sourcegitcommit: d36db3a1bc44aee6bc97422b557041c3aece4c67
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "80082434"
---
# <a name="using-visual-studio-code-for-powershell-development"></a>Использование Visual Studio Code для разработки в PowerShell

[Visual Studio Code](https://code.visualstudio.com/) — это кросс-платформенный редактор сценариев (Windows, macOS и Linux), созданный корпорацией Майкрософт. Наряду с [расширением PowerShell](https://marketplace.visualstudio.com/items?itemName=ms-vscode.PowerShell) он предоставляет широкие интерактивные возможности редактирования сценариев, упрощая написание надежных сценариев PowerShell.

Редактор Visual Studio Code с расширением PowerShell рекомендуется использовать для написания сценариев PowerShell.
Он поддерживает следующие версии PowerShell:

- PowerShell 7 и более поздних версий
- PowerShell Core 6
- Windows PowerShell 5.1

Перед запуском убедитесь, что оболочка PowerShell установлена в системе. Сведения о современных рабочих нагрузках для Windows, macOS и Linux см. по следующим ссылкам:

- [Установка PowerShell Core в Linux][install-pscore-linux]
- [Установка PowerShell Core в macOS][install-pscore-macos]
- [Установка PowerShell Core в Windows][install-pscore-windows]

Сведения о традиционных рабочих нагрузках Windows PowerShell см. в разделе [Установка Windows PowerShell][install-winps].

> [!NOTE]
> Visual Studio Code отличается от [Visual Studio](https://visualstudio.microsoft.com/).

> [!IMPORTANT]
> [Windows PowerShell ISE][ise] также доступна для Windows, но ее возможности больше не в активной разработке и она не работает с PowerShell 7 и Windows PowerShell Core 6.
> Как компонент доставки Windows эта среда по-прежнему официально поддерживается для внесения наиболее важных исправлений, связанных с безопасностью и обслуживанием. Пока что мы не планируем удалять ISE из Windows.

## <a name="editing-with-visual-studio-code"></a>Редактирование с помощью Visual Studio Code

1. Установите Visual Studio Code. Дополнительные сведения см. в статье [Setting up Visual Studio Code](https://code.visualstudio.com/Docs/setup/setup-overview) (Настройка Visual Studio Code).

    Доступны инструкции по установке на каждой платформе:

    - **Windows**: следуйте инструкциям по установке на странице [Запуск Visual Studio Code в Windows](https://code.visualstudio.com/docs/setup/windows).
    - **macOS**: следуйте инструкциям по установке на странице [Запуск Visual Studio Code в macOS](https://code.visualstudio.com/docs/setup/mac).
    - **Linux**: следуйте инструкциям по установке на странице [Запуск Visual Studio Code в Linux](https://code.visualstudio.com/docs/setup/linux).

1. Установите расширение PowerShell.

   1. Запустите приложение Visual Studio Code, введя `code` в консоли или `code-insiders`, если вы установили Visual Studio Code Insiders.
   1. Запустите **Quick Open** в Windows или Linux, нажав клавиши <kbd>CTRL</kbd>+<kbd>P</kbd>. В macOS нажмите клавиши <kbd>CMD</kbd>+<kbd>P</kbd>.
   1. В Quick Open введите `ext install powershell` и нажмите клавишу **ВВОД**.
   1. На боковой панели открывается представление **Расширения**. Выберите расширение PowerShell корпорации Майкрософт.
      Откроется примерно следующий экран Visual Studio Code:

      ![Visual Studio Code](media/using-vscode/vscode.png)

   1. Нажмите кнопку **Установить** для расширения PowerShell корпорации Майкрософт.
   1. После установки кнопка **Установить** изменяется на **Reload** (Перезагрузить). Нажмите кнопку **Reload** (Перезагрузить).
   1. После перезагрузки Visual Studio Code можно приступать к редактированию.

Например, чтобы создать файл, выберите **Файл > Создать**. Чтобы сохранить его, выберите **Файл > Сохранить** и укажите имя файла, например `HelloWorld.ps1`. Чтобы закрыть файл, щелкните `X` рядом с его именем. Чтобы завершить работу с Visual Studio Code, выберите элементы **Файл > Выйти**.

### <a name="installing-the-powershell-extension-on-restricted-systems"></a>Установка расширения PowerShell в системах с ограниченным доступом

Некоторые системы настроены таким образом, что требуется проверка всех подписей кода и, следовательно, одобрение службы редактора PowerShell вручную для запуска в системе. Обновление групповой политики, которое изменяет политику выполнения, является вероятной причиной того, что после установки расширения PowerShell вы сталкиваетесь со следующей ошибкой:

```
Language server startup failed.
```

Чтобы вручную утвердить службы редактора PowerShell и, следовательно, расширение PowerShell для Visual Studio Code, откройте командную строку PowerShell и выполните следующую команду:

```powershell
Import-Module $HOME\.vscode\extensions\ms-vscode.powershell*\modules\PowerShellEditorServices\PowerShellEditorServices.psd1
```

Вы увидите подсказку **Не удается проверить издателя. Вы действительно хотите запустить эту программу?**
Введите `A` для запуска файла. Затем откройте Visual Studio Code и убедитесь, что расширение PowerShell работает правильно. Если у вас все еще есть проблемы с началом работы, сообщите нам об этом на [GitHub](https://github.com/PowerShell/vscode-powershell/issues).

> [!NOTE]
> Расширение PowerShell для Visual Studio Code не поддерживает запуск в ограниченном языковом режиме. Дополнительные сведения см. в разделе GitHub о [поддерживаемом отслеживании проблем](https://github.com/PowerShell/vscode-powershell/issues/606).

### <a name="using-an-older-version-of-the-powershell-extension-for-windows-powershell-v3-and-v4"></a>Использование более ранней версии расширения PowerShell для Windows PowerShell версий 3 и 4

Хотя текущее расширение PowerShell [не поддерживают версии 3 и 4](https://github.com/PowerShell/vscode-powershell/issues/1310), вы по-прежнему можете использовать последнюю версию расширения, которую они поддерживают.

> [!NOTE]
> Дополнительные исправления для этой старой версии расширения не будут внесены. Она предоставляется без изменений, но доступна для вас, если вы все еще используете Windows PowerShell версии 3 или 4.

Сначала откройте панель расширений и найдите `PowerShell`. Затем щелкните значок шестеренки и выберите команду **Install another version...** (Установить другую версию...).

![Install another version... (Установить другую версию...)](media/using-vscode/install-another-version.png)

Затем выберите версию **`2020.1.0`** . Эта версия расширения — последняя версия, которую поддерживает Windows PowerShell версий 3 и 4.

Кроме того, добавьте следующий параметр, чтобы версия расширения не обновлялась автоматически:

```json
{
    "extensions.autoUpdate": false
}
```

В ближайшем будущем в Visual Studio Code может появиться изменение, которое прервет поддержку этой версии расширения.
В связи с этим и отсутствием поддержки мы настоятельно рекомендуем:

- скачать PowerShell 7, которая доступна для параллельной установки с другими версиями Windows PowerShell и наилучшим образом подходит для расширения PowerShell.
- выполнить обновление до Windows PowerShell 5.1.

Подробные сведения о месте установки см. в разделе [Редактирование с помощью Visual Studio Code](#editing-with-visual-studio-code) в этой статье.

### <a name="choosing-a-version-of-powershell-to-use-with-the-extension"></a>Выбор версии PowerShell для использования с расширением

Благодаря одновременной установке PowerShell Core и Windows PowerShell теперь можно использовать конкретную версию PowerShell с расширением PowerShell. Выберите версию, сделав следующее:

1. Откройте **палитру команд** в Windows и Linux (<kbd>CTRL</kbd>+<kbd>SHIFT</kbd>+<kbd>P</kbd>). В macOS нажмите клавиши <kbd>CMD</kbd>+<kbd>SHIFT</kbd>+<kbd>P</kbd>.
1. Выполните поиск по слову **Сеанс**.
1. Щелкните **PowerShell: Show Session Menu** (PowerShell: показать меню сеансов).
1. Выберите версию PowerShell, которую хотите использовать, из списка, например **PowerShell Core**.

> [!IMPORTANT]
> Этот компонент проверяет несколько известных расположений в разных операционных системах, чтобы найти расположения установки PowerShell. Если вы установили PowerShell в нетипичном расположении, оно может первоначально не отобразиться в меню сеансов. Вы можете расширить меню сеансов, [добавив собственные пользовательские пути](#adding-your-own-powershell-paths-to-the-session-menu), как описано ниже.

>[!NOTE]
> Есть еще один способ перехода в меню сеансов. В правом нижнем углу открытого файла PowerShell в редакторе виден зеленый номер версии. Щелкнув его, вы перейдете в меню сеансов.

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

### <a name="configuration-settings-for-visual-studio-code"></a>Параметры конфигурации для Visual Studio Code

Прежде всего, если вы не знаете, как изменить параметры в Visual Studio Code, мы рекомендуем просмотреть [документацию по параметрам Visual Studio Code](https://code.visualstudio.com/docs/getstarted/settings).

Следуя инструкциям в предыдущем абзаце, вы можете добавить параметры конфигурации в `settings.json`.

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
> Дополнительные сведения о кодировке файлов в Visual Studio Code см. в статье [Основные сведения о кодировке файлов в VSCode и PowerShell](understanding-file-encoding.md).
>
> Также ознакомьтесь со статьей [Репликация функций интегрированной среды скриптов в Visual Studio Code](How-To-Replicate-the-ISE-Experience-In-VSCode.md) для получения других советов по настройке Visual Studio Code для редактирования в PowerShell.

## <a name="debugging-with-visual-studio-code"></a>Отладка с помощью Visual Studio Code

### <a name="no-workspace-debugging"></a>Отладка без рабочей области

Начиная с Visual Studio Code версии 1.9, вы можете отлаживать сценарии PowerShell, не открывая папку со сценарием PowerShell. Откройте файл сценария PowerShell с помощью команды **Файл > Открыть файл...** , установите точку останова на строке, нажмите клавишу <kbd>F9</kbd>, а затем — клавишу <kbd>F5</kbd> для запуска отладки. Откроется панель действий отладки, позволяющая прервать работу отладчика, возобновить отладку, выполнить ее пошагово или остановить.

### <a name="workspace-debugging"></a>Отладка с рабочей областью

Отладка с рабочей областью обозначает отладку в контексте папки, которую вы открыли в Visual Studio Code с помощью команды **Открыть папку...** из меню **Файл**. Обычно открытая папка является папкой проекта PowerShell и (или) корнем репозитория Git.

Даже в этом режиме вы можете начать отладку выбранного сценария PowerShell, нажав клавишу <kbd>F5</kbd>. Однако отладка с рабочей областью позволяет задать несколько конфигураций отладки, отличных от простой отладки открытого файла. Мы вернемся к этому чуть позже.

Выполните следующие действия, чтобы создать файл конфигурации отладки:

  1. Откройте представление **Отладка** в Windows или Linux (<kbd>CTRL</kbd>+<kbd>SHIFT</kbd>+<kbd>D</kbd>). В macOS нажмите клавиши <kbd>CMD</kbd>+<kbd>SHIFT</kbd>+<kbd>D</kbd>.
  1. Щелкните ссылку create a launch.json file (создать файл launch.json).
  1. Visual Studio Code предлагает вам **выбрать среду**. Выберите **PowerShell**.
  1. Наконец, выберите тип отладки, который вы хотите использовать:

- **Launch Current File** (Запуск текущего файла) — запуск и отладка файла в текущем активном окне редактора.
- **Launch Script** (Запуск скрипта) — запуск и отладка указанного файла или команды.
- **Interactive Session** (Интерактивный сеанс) — команды отладки, выполняемые из интегрированной консоли.
- **Attach (Подключение)**  — подключение отладчика к выполняемому хост-процессу PowerShell.

В результате Visual Studio Code создает каталог и файл `.vscode\launch.json` в корневой папке рабочей области. Именно там хранится ваша конфигурация отладки. Если ваши файлы хранятся в репозитории Git, скорее всего, вы захотите зафиксировать файл `launch.json`. Содержимое файла `launch.json`:

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

Этот файл представляет типичные сценарии отладки. При открытии его в редакторе отображается кнопка **Добавить конфигурацию...** Можете нажать ее, чтобы добавить дополнительные конфигурации отладки PowerShell. Одной из полезных конфигураций является **PowerShell: Launch Script** (Запустить сценарий). С помощью этой конфигурации можно указать файл с дополнительными аргументами, которые нужно запускать при каждом нажатии клавиши <kbd>F5</kbd>, независимо от того, какой именно файл активен в редакторе.

После задания конфигурации отладки вы можете указать конфигурацию, используемую во время сеанса отладки, выбрав ее в раскрывающемся списке конфигураций отладки на панели инструментов представления **Отладка**.

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
[install-pscore-linux]:  ../../install/Installing-PowerShell-Core-on-Linux.md
[install-pscore-macos]:  ../../install/Installing-PowerShell-Core-on-macOS.md
[install-pscore-windows]: ../../install/Installing-PowerShell-Core-on-Windows.md
[install-winps]: ../../install/Installing-Windows-PowerShell.md
[ps-extension]: https://blogs.msdn.microsoft.com/cdndevs/2015/12/11/visual-studio-code-powershell-extension/
[debug]: https://devblogs.microsoft.com/powershell/announcing-powershell-language-support-for-visual-studio-code-and-more/
[vscode-guide]: https://johnpapa.net/debugging-with-visual-studio-code/
[ps-vscode]: https://github.com/PowerShell/vscode-powershell/tree/master/examples
[getting-started]: https://devblogs.microsoft.com/scripting/get-started-with-powershell-development-in-visual-studio-code/
[editing-part1]: https://devblogs.microsoft.com/scripting/visual-studio-code-editing-features-for-powershell-development-part-1/
[editing-part2]: https://devblogs.microsoft.com/scripting/visual-studio-code-editing-features-for-powershell-development-part-2/
[debugging-part1]: https://devblogs.microsoft.com/scripting/debugging-powershell-script-in-visual-studio-code-part-1/
[debugging-part2]: https://devblogs.microsoft.com/scripting/debugging-powershell-script-in-visual-studio-code-part-2/

## <a name="powershell-extension-for-visual-studio-code"></a>Расширение PowerShell для Visual Studio Code

Исходный код расширения PowerShell доступен на [GitHub](https://github.com/PowerShell/vscode-powershell).

Если вы заинтересованы в участии, запрос на вытягивание очень важен. Чтобы приступить к работе, следуйте указаниям в [документации для разработчиков на сайте GitHub](https://github.com/PowerShell/vscode-powershell/blob/master/docs/development.md).

## <a name="troubleshooting-the-powershell-extension-for-visual-studio-code"></a>Устранение проблем с расширением PowerShell для Visual Studio Code.

Если у вас возникли проблемы с использованием Visual Studio Code для разработки сценариев PowerShell, ознакомьтесь с [руководством по устранению проблем на сайте GitHub](https://github.com/PowerShell/vscode-powershell/blob/master/docs/troubleshooting.md)
