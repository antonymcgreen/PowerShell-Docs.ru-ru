---
title: Репликация функций интегрированной среды скриптов в Visual Studio Code
description: Репликация функций интегрированной среды скриптов в Visual Studio Code
ms.date: 08/06/2018
ms.openlocfilehash: 983da850c13d72bcdc7b2d33970c6e9e06b3d869
ms.sourcegitcommit: 9df29dfc637191b62ca591893c251c1e02d4eb4c
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 01/04/2019
ms.locfileid: "54012489"
---
# <a name="how-to-replicate-the-ise-experience-in-visual-studio-code"></a>Репликация функций интегрированной среды скриптов в Visual Studio Code

Хотя модуль PowerShell для VSCode не поиск полный функционально полностью интегрированной среде Сценариев PowerShell, позволяющие упростить процесс VSCode более естественным для пользователей интегрированной среды сценариев нет компонентов.

В этом документе пытается получить список параметров, которые можно настроить в Visual Studio Code для улучшить интерфейс чуть более привычной, по сравнению с в интегрированную среду сценариев пользователя.

## <a name="key-bindings"></a>Сочетания клавиш

| Функция                              | Интегрированная среда Сценариев привязки                  | VSCode привязки                              |
| ----------------                      | -----------                  | --------------                              |
| Прерывания и прерывания отладчика          | <kbd>CTRL</kbd>+<kbd>B</kbd> | <kbd>F6</kbd>                               |
| Выполнить текущий текст/выделенной строки | <kbd>F8</kbd>                | <kbd>F8</kbd>                               |
| Список доступных фрагментов               | <kbd>CTRL</kbd>+<kbd>J</kbd> | <kbd>CTRL</kbd>+<kbd>Alt</kbd>+<kbd>J</kbd> |

### <a name="custom-key-bindings"></a>Пользовательские привязки ключа

Вы можете [настроить собственные сочетания клавиш](https://code.visualstudio.com/docs/getstarted/keybindings#_custom-keybindings-for-refactorings) в VSCode также.

## <a name="tab-completion"></a>Заполнение нажатием клавиши TAB

Чтобы включить более интегрированной среды Сценариев по принципу нажатием клавиши TAB, добавьте этот параметр:

```json
"editor.tabCompletion": "on"
```

> [!NOTE]
> Этот параметр был добавлен непосредственно в VSCode (а не в расширении). Его поведение определяется непосредственно VSCode и не может изменяться с помощью расширения.

## <a name="no-focus-on-console-when-executing"></a>Нет сосредоточиться на консоль при выполнении

Чтобы полностью сосредоточиться в редакторе, при выполнении с <kbd>F8</kbd>:

```json
"powershell.integratedConsole.focusConsoleOnExecute": false
```

По умолчанию используется `true` для специальных возможностей.

## <a name="dont-start-integrated-console-on-startup"></a>Не выполнять интегрированной консоли при запуске

Чтобы остановить интегрированной консоли при запуске, установите:

```json
"powershell.integratedConsole.showOnStartup": false
```

> [!NOTE]
> Фоновый процесс PowerShell по-прежнему начнется с момента, предоставляющий возможности IntelliSense, анализ сценария, навигацию по символам и т. д. Однако консоль не будет отображаться.

## <a name="assume-files-are-powershell-by-default"></a>Предположим, что файлы являются PowerShell по умолчанию

Чтобы сделать новый/без названия файлов, зарегистрируйте как PowerShell, по умолчанию:

```json
"files.defaultLanguage": "powershell"
```

## <a name="color-scheme"></a>Цветовая схема

Существует ряд темы интегрированной среды Сценариев для VSCode сделать гораздо больше похожи на интегрированную среду Скриптов редактора.

В [Палитра команд] тип `theme` для получения `Preferences: Color Theme` и нажмите клавишу <kbd>ввод</kbd>.
В раскрывающемся списке выберите `PowerShell ISE`.

В настройках можно задать эту тему:

```json
"workbench.colorTheme": "PowerShell ISE"
```

## <a name="powershell-command-explorer"></a>Обозреватель команды PowerShell

Благодаря работе [ @corbob ](https://github.com/corbob), расширения PowerShell имеет об основах explorer свои собственные команды.

В [Палитра команд], введите `PowerShell Command Explorer` и нажмите клавишу <kbd>ввод</kbd>.

## <a name="open-in-the-ise"></a>Откройте в среде ISE

Если вы в итоге нужно открыть файл в интегрированной среде Сценариев в любом случае, вы можете использовать <kbd>Shift</kbd>+<kbd>Alt</kbd>+<kbd>P</kbd>.

## <a name="other-resources"></a>Другие ресурсы

- имеет 4sysops [хорошая статья](https://4sysops.com/archives/make-visual-studio-code-look-and-behave-like-powershell-ise/) о настройке Visual Studio Code для быть больше похожи на интегрированную среду Сценариев.
- Майк Ф. Роббинс имеет [потрясающее сообщение](https://mikefrobbins.com/2017/08/24/how-to-install-visual-studio-code-and-configure-it-as-a-replacement-for-the-powershell-ise/) по настройке VSCode.
- Узнать, имеет PowerShell [отличную записи](https://www.learnpwsh.com/setup-vs-code-for-powershell/) о том, как VSCode установки для PowerShell.

## <a name="more-settings"></a>Дополнительные параметры

Если вы знаете Дополнительные способы повышения VSCode показаться более знакомыми пользователям интегрированной среды Сценариев, участвуют в этом документе. Если вы ищете конфигурации совместимости, но не удается найти любым способом, чтобы включить его, [сообщите о них](https://github.com/PowerShell/vscode-powershell/issues/new/choose) и за ответами!

Мы всегда рады принимать запросы на Вытягивание и вклад также!

## <a name="vscode-tips"></a>Советы по VSCode

### <a name="command-palette"></a>Палитра команд

<kbd>F1</kbd> или <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> (<kbd>Cmd</kbd> + <kbd> Сдвинуть</kbd>+<kbd>P</kbd> в Mac OS)

Удобным способом выполнения команд в VSCode.
Дополнительные сведения см. в разделе [документация VSCode](https://code.visualstudio.com/docs/getstarted/userinterface#_command-palette).

[Палитра команд]: #command-palette
