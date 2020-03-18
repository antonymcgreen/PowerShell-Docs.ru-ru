---
title: Репликация функций интегрированной среды скриптов в Visual Studio Code
description: Репликация функций интегрированной среды скриптов в Visual Studio Code
ms.date: 08/06/2018
ms.openlocfilehash: 193243dc2e3e921b22a6ee068370200ae84ce4ac
ms.sourcegitcommit: 01c60c0c97542dbad48ae34339cddbd813f1353b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2020
ms.locfileid: "78279276"
---
# <a name="how-to-replicate-the-ise-experience-in-visual-studio-code"></a>Репликация функций интегрированной среды скриптов в Visual Studio Code

В то время, как расширение PowerShell для VSCode не совсем совместимо с интегрированной средой сценариев PowerShell, существуют функции, использование которых позволит пользователям интегрированной среды сценариев почувствовать себя более свободно в VSCode.

В этой статье приведен список параметров, настраиваемых в VSCode, которые смогут облегчить ее использование для пользователей интегрированной среды сценариев.

## <a name="ise-mode"></a>Режим ISE

> [!NOTE]
> Эта функция доступна в расширении предварительной версии PowerShell, начиная с версии 2019.12.0, и в расширении PowerShell, начиная с версии 2020.3.0.

Самый простой способ реплицировать функции интегрированной среды скриптов (ISE) в Visual Studio Code — включить режим ISE.
Для этого откройте палитру команд (<kbd>F1</kbd> или <kbd>CTRL</kbd>+<kbd>SHIFT</kbd>+<kbd>P</kbd> или <kbd>CMD</kbd>+<kbd>SHIFT</kbd>+<kbd>P</kbd> в macOS) и введите "ISE Mode" (Режим ISE).
Выберите в списке пункт "PowerShell: Enable ISE Mode" (PowerShell: включить режим ISE).

Эта команда автоматически применяет многие параметры, описанные в этом документе.
Результат имеет следующий вид:

![Режим ISE](media/How-To-Replicate-the-ISE-Experience-In-VSCode/3-ise-mode.png)

В оставшейся части этой статьи приводятся более подробные сведения о параметрах в режиме ISE и некоторых дополнительных параметрах.

## <a name="key-bindings"></a>Сочетания клавиш

| Компонент                              | Привязка интегрированной среды сценариев                  | Привязка VSCode                              |
| ----------------                      | -----------                  | --------------                              |
| Прерывание и остановка отладчика          | <kbd>CTRL</kbd>+<kbd>B</kbd> | <kbd>F6</kbd>                               |
| Выполнение текущей строки / выделение текста | <kbd>F8</kbd>                | <kbd>F8</kbd>                               |
| Список доступных фрагментов               | <kbd>CTRL</kbd>+<kbd>J</kbd> | <kbd>CTRL</kbd>+<kbd>ALT</kbd>+<kbd>J</kbd> |

### <a name="custom-key-bindings"></a>Сочетания клавиш, настраиваемые пользователем

Также в VSCode можно [настраивать собственные сочетания клавиш](https://code.visualstudio.com/docs/getstarted/keybindings#_custom-keybindings-for-refactorings).

## <a name="simplified-ise-like-ui"></a>Упрощенный интерфейс, как в интегрированной среде сценариев

Если вы хотите упростить пользовательский интерфейс Visual Studio Code, чтобы он стал больше похож на интерфейс интегрированной среды сценариев, примените эти два параметра:

```json
"workbench.activityBar.visible": false,
"debug.openDebug": "neverOpen",
```

> [!NOTE]
> Эти параметры включены в [режим ISE](#ise-mode).

Это скроет разделы с панелью действий и боковой панелью отладки в красной области, как на изображении ниже.

![Выделенный раздел с панелью действий и боковой панелью отладки](media/How-To-Replicate-the-ISE-Experience-In-VSCode/1-highlighted-sidebar.png)

В итоге представление будет выглядеть так:

![Упрощенное представление VS Code](media/How-To-Replicate-the-ISE-Experience-In-VSCode/2-simplified-ui.png)

## <a name="tab-completion"></a>Заполнение нажатием клавиши TAB

Чтобы включить заполнение нажатием клавиши TAB (похожее на интегрированную среду сценариев), добавьте следующий параметр.

```json
"editor.tabCompletion": "on",
```

> [!NOTE]
> Данный параметр был добавлен в VSCode напрямую (вместо расширения). Его поведение определяется напрямую VSCode. Его невозможно изменить с помощью расширения.

> [!NOTE]
> Этот параметр включен в [режим ISE](#ise-mode).

## <a name="no-focus-on-console-when-executing"></a>Отсутствие фокуса в консоли во время выполнения

Чтобы сохранить фокус в редакторе во время выполнения с помощью клавиши <kbd>F8</kbd>, выполните следующее.

```json
"powershell.integratedConsole.focusConsoleOnExecute": false
```

> [!NOTE]
> Этот параметр включен в [режим ISE](#ise-mode).

Значение по умолчанию `true` устанавливается в соответствии с требованиями к поддержке специальных возможностей.

## <a name="dont-start-integrated-console-on-startup"></a>Интегрированную консоль не следует запускать при начальной загрузке

Чтобы остановить запуск интегрированной консоли при начальной загрузке, установите следующий параметр.

```json
"powershell.integratedConsole.showOnStartup": false
```

> [!NOTE]
> Тем не менее фоновый процесс PowerShell все равно запустится, так как он предоставляет IntelliSense, анализ сценариев, навигацию по символам и т. д. Консоль не будет отображаться.

## <a name="assume-files-are-powershell-by-default"></a>Предположим, что по умолчанию файлы относятся к PowerShell

Чтобы создать новые файлы без имени, по умолчанию следует зарегистрироваться в качестве PowerShell.

```json
"files.defaultLanguage": "powershell",
```

> [!NOTE]
> Этот параметр включен в [режим ISE](#ise-mode).

## <a name="color-scheme"></a>Цветовая схема

Существует большое количество тем интегрированной среды сценариев, которые доступны для VSCode, предназначенные для того, чтобы сделать редактор более похожим на интегрированную среду сценариев.

В [Палитра команд] введите `theme`, чтобы получить `Preferences: Color Theme`, а затем нажмите <kbd>ВВОД</kbd>.
В раскрывающемся списке выберите `PowerShell ISE`.

Эту тему можно установить в параметрах следующим образом.

```json
"workbench.colorTheme": "PowerShell ISE",
```

> [!NOTE]
> Этот параметр включен в [режим ISE](#ise-mode).

## <a name="powershell-command-explorer"></a>Команды обозревателя PowerShell

Благодаря работе, проделанной [@corbob](https://github.com/corbob), теперь расширение PowerShell обладает начальными командами обозревателя.

В [Палитра команд] введите `PowerShell Command Explorer` и нажмите <kbd>ВВОД</kbd>.

> [!NOTE]
> В [режиме ISE](#ise-mode) они отображаются автоматически.

## <a name="open-in-the-ise"></a>Открытие в интегрированной среде сценариев

Если вам понадобится открыть файл в интегрированной среде сценариев, то вы также можете использовать <kbd>SHIFT</kbd>+<kbd>ALT</kbd>+<kbd>P</kbd>.

## <a name="other-resources"></a>Другие ресурсы

- На веб-сайте 4sysops можно найти [замечательную статью](https://4sysops.com/archives/make-visual-studio-code-look-and-behave-like-powershell-ise/) о настройках VSCode, которые приблизят ее к интегрированной среде сценариев.
- Также Майк Ф. Роббинс (Mike F Robbins) написал [отличную статью](https://mikefrobbins.com/2017/08/24/how-to-install-visual-studio-code-and-configure-it-as-a-replacement-for-the-powershell-ise/) о настройке VSCode.
- Во время изучения PowerShell можно ознакомится с [информативной статьей](https://www.learnpwsh.com/setup-vs-code-for-powershell/) о настройке VSCode для работы с PowerShell.

## <a name="more-settings"></a>Дополнительные параметры

Если вам известны дополнительные способы сделать VSCode более удобным для пользователей интегрированной среды разработки, внесите их в этот документ. Если существует конфигурация совместимости, которую вы не можете включить, не медлите и [создайте запрос](https://github.com/PowerShell/vscode-powershell/issues/new/choose).

Мы всегда рады содействию и запросам на включение внесенных изменений.

## <a name="vscode-tips"></a>Советы по работе в VSCode

### <a name="command-palette"></a>Палитра команд

<kbd>F1</kbd> или <kbd>CTRL</kbd>+<kbd>SHIFT</kbd>+<kbd>P</kbd> (<kbd>Cmd</kbd>+<kbd>SHIFT</kbd>+<kbd>P</kbd> на macOS)

Удобный способ выполнения команд в VSCode.
Дополнительные сведения см. в [документации по VSCode](https://code.visualstudio.com/docs/getstarted/userinterface#_command-palette).

[Палитра команд]: #command-palette
