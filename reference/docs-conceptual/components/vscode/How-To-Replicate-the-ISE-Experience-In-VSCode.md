---
title: Репликация функций интегрированной среды скриптов в Visual Studio Code
description: Репликация функций интегрированной среды скриптов в Visual Studio Code
ms.date: 08/06/2018
ms.openlocfilehash: 899e1c393fd49b0659631b88d610e80ec885e69e
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81005607"
---
# <a name="how-to-replicate-the-ise-experience-in-visual-studio-code"></a>Репликация функций интегрированной среды скриптов в Visual Studio Code

Расширение PowerShell для VS Code не вполне соответствует интегрированной среде скриптов PowerShell, но существуют функции, которые помогут пользователям интегрированной среды скриптов эффективней работать с VS Code.

В этой статье приведен список параметров, настраиваемых в VS Code, которые упростят работу с программой пользователям интегрированной среды скриптов.

## <a name="ise-mode"></a>Режим ISE

> [!NOTE]
> Эта функция доступна в расширении предварительной версии PowerShell, начиная с версии 2019.12.0, и в расширении PowerShell, начиная с версии 2020.3.0.

Самый простой способ реплицировать функции интегрированной среды скриптов (ISE) в Visual Studio Code — включить режим ISE.
Для этого откройте палитру команд (клавиша <kbd>F1</kbd> или клавиши <kbd>CTRL</kbd>+<kbd>SHIFT</kbd>+<kbd>P</kbd> или <kbd>CMD</kbd>+<kbd>SHIFT</kbd>+<kbd>P</kbd> в macOS) и введите ISE Mode (Режим ISE). Выберите в списке пункт "PowerShell: Enable ISE Mode" (PowerShell: включить режим ISE).

Эта команда автоматически применяет многие параметры, описанные в этом документе. Результат имеет следующий вид:

![Режим ISE](media/How-To-Replicate-the-ISE-Experience-In-VSCode/3-ise-mode.png)

## <a name="ise-mode-configuration-settings"></a>Параметры конфигурации режима ISE

Режим ISE вносит следующие изменения в параметры VS Code.

- Сочетания клавиш

  |               Компонент                |         Привязка интегрированной среды сценариев          |              Привязка VS Code                |
  | ------------------------------------- | ---------------------------- | ------------------------------------------- |
  | Прерывание и остановка отладчика          | <kbd>CTRL</kbd>+<kbd>B</kbd> | <kbd>F6</kbd>                               |
  | Выполнение текущей строки / выделение текста | <kbd>F8</kbd>                | <kbd>F8</kbd>                               |
  | Список доступных фрагментов               | <kbd>CTRL</kbd>+<kbd>J</kbd> | <kbd>CTRL</kbd>+<kbd>ALT</kbd>+<kbd>J</kbd> |

  > [!NOTE]
  > В VS Code также можно [настраивать собственные сочетания клавиш](https://code.visualstudio.com/docs/getstarted/keybindings#_custom-keybindings-for-refactorings).

- Упрощенный интерфейс, как в интегрированной среде сценариев

  Если вы хотите упростить пользовательский интерфейс Visual Studio Code, чтобы он стал больше похож на интерфейс интегрированной среды сценариев, примените эти два параметра:

  ```json
  "workbench.activityBar.visible": false,
  "debug.openDebug": "neverOpen",
  ```

  Эти параметры позволяют скрыть разделы с панелью действий и боковой панелью отладки, которые очерчены красной линией на следующей иллюстрации.

  ![Выделенный раздел с панелью действий и боковой панелью отладки](media/How-To-Replicate-the-ISE-Experience-In-VSCode/1-highlighted-sidebar.png)

  В итоге представление будет выглядеть так:

  ![Упрощенное представление VS Code](media/How-To-Replicate-the-ISE-Experience-In-VSCode/2-simplified-ui.png)

- Заполнение нажатием клавиши TAB

  Чтобы включить заполнение нажатием клавиши TAB (похожее на интегрированную среду сценариев), добавьте следующий параметр.

  ```json
  "editor.tabCompletion": "on",
  ```

- Отсутствие фокуса в консоли во время выполнения

  Чтобы сохранить фокус в редакторе во время выполнения с помощью клавиши <kbd>F8</kbd>, выполните следующее.

  ```json
  "powershell.integratedConsole.focusConsoleOnExecute": false
  ```

  Значение по умолчанию `true` устанавливается в соответствии с требованиями к поддержке специальных возможностей.

- Интегрированную консоль не следует запускать при начальной загрузке

  Чтобы остановить запуск интегрированной консоли при начальной загрузке, установите следующий параметр.

  ```json
  "powershell.integratedConsole.showOnStartup": false
  ```

  > [!NOTE]
  > Фоновый процесс PowerShell все равно запустится, так как он предоставляет IntelliSense, анализ скриптов, навигацию по символам и т. д., но консоль не будет запущена.

- Предположим, что по умолчанию файлы относятся к PowerShell

  Чтобы создать новые файлы без имени, по умолчанию следует зарегистрироваться в качестве PowerShell.

  ```json
  "files.defaultLanguage": "powershell",
  ```

- Цветовая схема

  Существует большое количество тем ISE, доступных для VS Code. Они позволяют сделать редактор более похожим на интегрированную среду скриптов.

  В [Палитра команд][] введите `theme`, чтобы получить `Preferences: Color Theme`, а затем нажмите <kbd>ВВОД</kbd>. В раскрывающемся списке выберите `PowerShell ISE`.

  Эту тему можно установить в параметрах следующим образом.

  ```json
  "workbench.colorTheme": "PowerShell ISE",
  ```

- Команды обозревателя PowerShell

  Благодаря работе, проделанной [@corbob](https://github.com/corbob), теперь расширение PowerShell обладает начальными командами обозревателя.

  В [Палитра команд][] введите `PowerShell Command Explorer` и нажмите <kbd>ВВОД</kbd>.

- Открытие в интегрированной среде сценариев

  Если вы хотите открыть файл в интегрированной среде скриптов Windows PowerShell, откройте [Палитра команд][], выполните поиск по запросу open in ise (Открыть в интегрированной среде скриптов) и выберите **PowerShell: Open Current File in PowerShell ISE** (Открыть текущий файл в интегрированной среде скриптов PowerShell).

## <a name="other-resources"></a>Другие ресурсы

- На веб-сайте 4sysops доступна [замечательная статья][4sysops] о настройках VS Code, которые сделают интерфейс программы похожим на интегрированную среду скриптов.
- [Отличная статья][mikefrobbins] о настройке VS Code, написанная Майком Ф. Роббинсом (Mike F. Robbins).
- Еще одна [хорошая статья][learnpwsh] о настройке VS Code для работы с PowerShell на сайте Learn PowerShell.

## <a name="vs-code-tips"></a>Рекомендации по работе с Visual Studio Code

- Палитра команд

  Палитра команд — это удобный инструмент выполнения команд в VS Code. Откройте палитру команд с помощью клавиши <kbd>F1</kbd> или клавиш <kbd>CTRL</kbd>+<kbd>SHIFT</kbd>+<kbd>P</kbd>, или <kbd>CMD</kbd>+<kbd>+</kbd>+<kbd>P</kbd> в macOS.

  Дополнительные сведения см. в [документации по VS Code][vsc-docs].

- Отключение консоли отладки

  Если вы планируете использовать VS Code только для создания скриптов PowerShell, можно скрыть **консоль отладки**, так как она не используется расширением PowerShell. Для этого щелкните правой кнопкой мыши **консоль отладки** и снимите флажок, чтобы скрыть ее.

## <a name="more-settings"></a>Дополнительные параметры

Если вы знаете, как еще можно упростить работу с VS Code для пользователей интегрированной среды скриптов, дополните эту статью. Если существует конфигурация совместимости, которую вы не можете включить, не медлите и [Отправить сообщение о проблеме][].

Мы всегда рады содействию и запросам на включение внесенных изменений.

<!-- link references -->
[vsc-docs]: https://code.visualstudio.com/docs/getstarted/userinterface#_command-palette
[Палитра команд]: #vs-code-tips
[Отправить сообщение о проблеме]: https://github.com/PowerShell/VSCode-powershell/issues/new/choose

[4sysops]: https://4sysops.com/archives/make-visual-studio-code-look-and-behave-like-powershell-ise/
[mikefrobbins]: https://mikefrobbins.com/2017/08/24/how-to-install-visual-studio-code-and-configure-it-as-a-replacement-for-the-powershell-ise/
[learnpwsh]: https://www.learnpwsh.com/setup-vs-code-for-powershell/
