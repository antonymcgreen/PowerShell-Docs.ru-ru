---
title: Удаленные редактирование и отладка в Visual Studio Code
description: Удаленные редактирование и отладка в Visual Studio Code
ms.date: 06/13/2019
ms.openlocfilehash: 5ce7f575d90ff47fd6b8a0a2b567e972ec3a9fef
ms.sourcegitcommit: 2aec310ad0c0b048400cb56f6fa64c1e554c812a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/23/2020
ms.locfileid: "83809280"
---
# <a name="using-visual-studio-code-for-remote-editing-and-debugging"></a>Удаленные редактирование и отладка в Visual Studio Code

Каждый пользователь, знакомый с ISE, может вспомнить, как запускать `psedit file.ps1` из встроенной консоли, чтобы открыть локальные или удаленные файлы прямо в интегрированной среде сценариев.

Эта функция также доступна в расширении PowerShell для VSCode. В этом руководстве показано, как это сделать.

## <a name="prerequisites"></a>предварительные требования

В этом руководстве предполагается, что у вас есть:

- удаленный ресурс (например, виртуальная машина, контейнер), к которому у вас есть доступ;
- PowerShell, работающий на нем и на основном компьютере;
- VSCode и расширение PowerShell для VSCode.

Эта возможность работает с Windows PowerShell и PowerShell Core.

Эта возможность также работает при подключении к удаленному компьютеру с помощью WinRM, PowerShell Direct или SSH. Если вы хотите использовать SSH, но используете Windows, ознакомьтесь с [версией SSH Win32](https://github.com/PowerShell/Win32-OpenSSH).

> [!IMPORTANT]
> Команды `Open-EditorFile` и `psedit` работают только в **интегрированной консоли PowerShell**, созданной с помощью расширения PowerShell для VSCode.

## <a name="usage-examples"></a>Примеры использования

В этих примерах демонстрируется удаленное редактирование и отладка виртуальной машины Ubuntu, которая запущена в Azure, с MacBook Pro. Процесс для Windows идентичен.

### <a name="local-file-editing-with-open-editorfile"></a>Редактирование локального файла с помощью открытого редактора файлов

С помощью расширения PowerShell для VSCode и открытой интегрированной консоли PowerShell напечатайте `Open-EditorFile foo.ps1` или `psedit foo.ps1`, чтобы открыть локальный файл foo.ps1 прямо в редакторе.

![Файл foo.ps1 в открытом редакторе файлов работает локально](media/Using-VSCode-for-Remote-Editing-and-Debugging/1-open-local-file.png)

>[!NOTE]
> Файл `foo.ps1` должен уже существовать.

После этого вы можете сделать следующее.

- Добавить точки останова во внутреннее поле.

  ![добавление точки останова во внутреннее поле](media/Using-VSCode-for-Remote-Editing-and-Debugging/2-adding-breakpoint-gutter.png)

- Нажать клавишу F5 для отладки сценария PowerShell.

  ![отладка локального скрипта PowerShell](media/Using-VSCode-for-Remote-Editing-and-Debugging/3-local-debug.png)

Во время отладки можно взаимодействовать с консолью отладки, ознакомиться с переменными в левой области и другими стандартными средствами отладки.

### <a name="remote-file-editing-with-open-editorfile"></a>Редактирование удаленного файла с помощью открытого редактора файлов

Теперь давайте приступим к редактированию и отладке удаленного файла. Шаги практически одинаковы, но в первую очередь нам нужно начать сеанс PowerShell на удаленном сервере.

Для этого существует командлет. Он называется `Enter-PSSession`.

Проще говоря, командлет действует так:

- `Enter-PSSession -ComputerName foo` запускает сеанс через WinRM;
- `Enter-PSSession -ContainerId foo` и `Enter-PSSession -VmId foo` начинают сеанс с помощью PowerShell Direct;
- `Enter-PSSession -HostName foo` запускает сеанс через SSH.

Дополнительные сведения см. в документации [Enter-PSSession](/powershell/module/microsoft.powershell.core/enter-pssession).

Для удаленного взаимодействия используется SSH, так как мы будем работать с macOS в виртуальной машине Ubuntu в Azure.

Сначала в интегрированной консоли запустите `Enter-PSSession`. Вы подключены к удаленному сеансу, когда `[<hostname>]` отображается слева от командной строки.

![Вызов Enter-PSSession](media/Using-VSCode-for-Remote-Editing-and-Debugging/4-enter-pssession.png)

Теперь мы можем выполнить те же шаги, что и при редактировании локального скрипта.

1. Чтобы открыть удаленный файл `test.ps1`, запустите `Open-EditorFile test.ps1` или `psedit test.ps1`.

  ![Открытый файл test.ps1 в редакторе файлов](media/Using-VSCode-for-Remote-Editing-and-Debugging/5-open-remote-file.png)

1. Отредактируйте файл, установите точки останова.

   ![Редактирование и установка точек останова](media/Using-VSCode-for-Remote-Editing-and-Debugging/6-set-breakpoints.png)

1. Начните отладку (F5) удаленного файла.

   ![Отладка удаленного файла](media/Using-VSCode-for-Remote-Editing-and-Debugging/7-start-debugging.png)

Если у вас возникли проблемы, вы можете писать вопросы [в репозитории GitHub](https://github.com/powershell/vscode-powershell).
