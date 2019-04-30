---
title: Удаленные редактирование и отладка в Visual Studio Code
description: Удаленные редактирование и отладка в Visual Studio Code
ms.date: 08/06/2018
ms.openlocfilehash: fbc1ee3556e822b4afb2b37111d0688dc89fdab3
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62086683"
---
# <a name="using-visual-studio-code-for-remote-editing-and-debugging"></a>Удаленные редактирование и отладка в Visual Studio Code

Каждый пользователь, знакомый с ISE, может вспомнить, как запускать `psedit file.ps1` из встроенной консоли, чтобы открыть локальные или удаленные файлы прямо в интегрированной среде сценариев.

Оказывается, эта функция также доступна в расширении PowerShell для VSCode. В этом руководстве показано, как это сделать.

## <a name="prerequisites"></a>Необходимые компоненты

В этом руководстве предполагается, что у вас есть:

- удаленный ресурс (например, виртуальная машина, контейнер), к которому у вас есть доступ;
- PowerShell, работающий на нем и на основном компьютере;
- VSCode и расширение PowerShell для VSCode.

Эта возможность работает с Windows PowerShell и PowerShell Core.

Эта возможность также работает при подключении к удаленному компьютеру с помощью WinRM, PowerShell Direct или SSH. Если вы хотите использовать SSH, но используете Windows, ознакомьтесь с [версией SSH Win32](https://github.com/PowerShell/Win32-OpenSSH).

## <a name="lets-go"></a>Приступим

В этом разделе мы рассмотрим удаленное редактирование и отладку виртуальной машины Ubuntu, которая запущена в Azure, с MacBook Pro. Если Windows не используется, то **процесс идентичен**.

### <a name="local-file-editing-with-open-editorfile"></a>Редактирование локального файла с помощью открытого редактора файлов

С помощью расширения PowerShell для VSCode и открытой интегрированной консоли PowerShell напечатайте `Open-EditorFile foo.ps1` или `psedit foo.ps1`, чтобы открыть локальный файл foo.ps1 прямо в редакторе.

![Файл foo.ps1 в открытом редакторе файлов работает локально](https://user-images.githubusercontent.com/2644648/34895897-7c2c46ac-f79c-11e7-9410-a252aff52f13.png)

>[!NOTE]
> foo.ps1 должен уже существовать.

После этого вы можете сделать следующее.

Добавить точки останова во внутреннее поле. ![Добавление точек останова во внутреннее поле](https://user-images.githubusercontent.com/2644648/34895893-7bdc38e2-f79c-11e7-8026-8ad53f9a1bad.png)

Нажать клавишу F5 для отладки сценария PowerShell.
![Отладка локального сценария PowerShell](https://user-images.githubusercontent.com/2644648/34895894-7bedb874-f79c-11e7-9180-7e0dc2d02af8.png)

Во время отладки можно взаимодействовать с консолью отладки, ознакомиться с переменными в левой области и другими стандартными средствами отладки.

### <a name="remote-file-editing-with-open-editorfile"></a>Редактирование удаленного файла с помощью открытого редактора файлов

Теперь давайте приступим к редактированию и отладке удаленного файла. Шаги практически одинаковы, но в первую очередь нам нужно начать сеанс PowerShell на удаленном сервере.

Для этого существует командлет. Он называется `Enter-PSSession`.

Проще говоря, командлет действует так:

- `Enter-PSSession -ComputerName foo` запускает сеанс через WinRM;
- `Enter-PSSession -ContainerId foo` и `Enter-PSSession -VmId foo` начинают сеанс с помощью PowerShell Direct;
- `Enter-PSSession -HostName foo` запускает сеанс через SSH.

Чтобы получить дополнительные сведения о `Enter-PSSession`, ознакомьтесь с документацией [здесь](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/enter-pssession?view=powershell-6).

Для удаленного взаимодействия используется SSH, поскольку мы будем работать с macOS в виртуальной машине Ubuntu в Azure.

Во-первых, давайте запустим в интегрированной консоли Enter-PSSession. Вы узнаете, что начали сеанс, когда слева от командной строки появится `[something]`.

![Вызов Enter-PSSession](https://user-images.githubusercontent.com/2644648/34895896-7c18e0bc-f79c-11e7-9b36-6f4bd0e9b0db.png)

После этого мы можем выполнить те же шаги, что и при редактировании локального сценария.

1. Запустите `Open-EditorFile test.ps1` или `psedit test.ps1`, чтобы открыть удаленный файл `test.ps1`. ![Файл test.ps1 в открытом редакторе файлов](https://user-images.githubusercontent.com/2644648/34895898-7c3e6a12-f79c-11e7-8bdf-549b591ecbcb.png)
2. Отредактируйте файл, установите точки останова. ![Редактирование и установка точек останова](https://user-images.githubusercontent.com/2644648/34895892-7bb68246-f79c-11e7-8c0a-c2121773afbb.png)
3. Начните отладку (F5) удаленного файла.

![Отладка удаленного файла](https://user-images.githubusercontent.com/2644648/34895895-7c040782-f79c-11e7-93ea-47724fa5c10d.png)

Вот и все! Мы надеемся, что это руководство помогло прояснить возникшие вопросы по удаленной отладке и редактированию PowerShell в VSCode.

Если у вас возникли проблемы, вы можете писать вопросы [в репозитории GitHub](http://github.com/powershell/vscode-powershell).
