---
title: Репликация функций интегрированной среды скриптов в Visual Studio Code
description: Репликация функций интегрированной среды скриптов в Visual Studio Code
ms.date: 08/06/2018
ms.openlocfilehash: 983da850c13d72bcdc7b2d33970c6e9e06b3d869
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62058528"
---
# <a name="how-to-replicate-the-ise-experience-in-visual-studio-code"></a>Репликация функций интегрированной среды скриптов в Visual Studio Code

В то время, как расширение PowerShell для VSCode не совсем совместимо с интегрированной средой сценариев PowerShell, существуют функции, использование которых позволит пользователям интегрированной среды сценариев почувствовать себя более свободно в VSCode.

В этой статье приведен список параметров, настраиваемых в VSCode, которые смогут облегчить ее использование для пользователей интегрированной среды сценариев.

## <a name="key-bindings"></a>Сочетания клавиш

| Функция                              | Привязка интегрированной среды сценариев                  | Привязка VSCode                              |
| ----------------                      | -----------                  | --------------                              |
| Прерывание и остановка отладчика          | <kbd>CTRL</kbd>+<kbd>B</kbd> | <kbd>F6</kbd>                               |
| Выполнение текущей строки / выделение текста | <kbd>F8</kbd>                | <kbd>F8</kbd>                               |
| Список доступных фрагментов               | <kbd>CTRL</kbd>+<kbd>J</kbd> | <kbd>CTRL</kbd>+<kbd>ALT</kbd>+<kbd>J</kbd> |

### <a name="custom-key-bindings"></a>Сочетания клавиш, настраиваемые пользователем

Также в VSCode можно [настраивать собственные сочетания клавиш](https://code.visualstudio.com/docs/getstarted/keybindings#_custom-keybindings-for-refactorings).

## <a name="tab-completion"></a>Заполнение нажатием клавиши TAB

Чтобы включить заполнение нажатием клавиши TAB (похожее на интегрированную среду сценариев), добавьте следующий параметр.

```json
"editor.tabCompletion": "on"
```

> [!NOTE]
> Данный параметр был добавлен в VSCode напрямую (вместо расширения). Его поведение определяется напрямую VSCode. Его невозможно изменить с помощью расширения.

## <a name="no-focus-on-console-when-executing"></a>Отсутствие фокуса на консоли во время выполнения

Чтобы сохранить фокус в редакторе во время выполнения с помощью клавиши <kbd>F8</kbd>, выполните следующее.

```json
"powershell.integratedConsole.focusConsoleOnExecute": false
```

Для специальных возможностей значением по умолчанию будет `true`.

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
"files.defaultLanguage": "powershell"
```

## <a name="color-scheme"></a>Цветовая схема

Существует большое количество тем интегрированной среды сценариев, которые доступны для VSCode, предназначенные для того, чтобы сделать редактор более похожим на интегрированную среду сценариев.

В [Палитра команд] введите `theme`, чтобы получить `Preferences: Color Theme`, а затем нажмите <kbd>ВВОД</kbd>.
В раскрывающемся списке выберите `PowerShell ISE`.

Эту тему можно установить в параметрах следующим образом.

```json
"workbench.colorTheme": "PowerShell ISE"
```

## <a name="powershell-command-explorer"></a>Команды обозревателя PowerShell

Благодаря работе, проделанной [@corbob](https://github.com/corbob), теперь расширение PowerShell обладает начальными командами обозревателя.

В [Палитра команд] введите `PowerShell Command Explorer` и нажмите <kbd>ВВОД</kbd>.

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
