---
title: Удаленные редактирование и отладка в Visual Studio Code
description: Удаленные редактирование и отладка в Visual Studio Code
ms.date: 08/06/2018
ms.openlocfilehash: bab1a629a7e9dafd5957cf93025abb18b8a4f326
ms.sourcegitcommit: 548547b2d5fc73e726bb9fec6175d452a351d975
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 12/20/2018
ms.locfileid: "53655638"
---
# <a name="using-visual-studio-code-for-remote-editing-and-debugging"></a>Удаленные редактирование и отладка в Visual Studio Code

Для тех, которые были знакомы с интегрированной среды Сценариев, можно вспомнить, что можно выполнить `psedit file.ps1` из интегрированной консоли, чтобы открыть файлы — локальный или удаленный - непосредственно в интегрированной среде Сценариев.

Оказывается, эта функция также доступна в модуле PowerShell для VSCode. В этом руководстве показано, как это сделать.

## <a name="prerequisites"></a>Необходимые компоненты

В этом руководстве предполагается, что у вас есть:

- удаленному ресурсу (например: виртуальную Машину, контейнер), имеется доступ к
- PowerShell, выполняющихся в его и хост-компьютером
- VSCode и модуль PowerShell для VSCode

Эта функция работает с Windows PowerShell и PowerShell Core.

Эта функция также работает при подключении к удаленному компьютеру с помощью WinRM, PowerShell Direct или SSH. Если вы хотите использовать SSH, но при использовании Windows, ознакомьтесь с [версии Win32 SSH](https://github.com/PowerShell/Win32-OpenSSH)!

## <a name="lets-go"></a>Приступим

В этом разделе мы рассмотрим удаленного редактирования и отладки из моей MacBook Pro к виртуальной Машине Ubuntu, работающих в Azure. Я не использует Windows, но **процесс идентичен**.

### <a name="local-file-editing-with-open-editorfile"></a>Локальный файл с открытым EditorFile

С помощью расширения PowerShell для работы VSCode и открыть консоль PowerShell, введя `Open-EditorFile foo.ps1` или `psedit foo.ps1` для открытия файла локального foo.ps1 прямо в редакторе.

![Открыть EditorFile foo.ps1 работает локально](https://user-images.githubusercontent.com/2644648/34895897-7c2c46ac-f79c-11e7-9410-a252aff52f13.png)

>[!NOTE]
> foo.ps1 должен уже существовать.

После этого можно:

добавить точки останова во внутренней области ![добавления точки останова для внутренней области](https://user-images.githubusercontent.com/2644648/34895893-7bdc38e2-f79c-11e7-8026-8ad53f9a1bad.png)

и нажмите клавишу F5 для отладки сценария PowerShell.
![Отладка локального сценария PowerShell](https://user-images.githubusercontent.com/2644648/34895894-7bedb874-f79c-11e7-9180-7e0dc2d02af8.png)

Во время отладки, можно взаимодействовать с консолью отладки, ознакомьтесь с переменные в области слева и другие стандартные средства отладки.

### <a name="remote-file-editing-with-open-editorfile"></a>Редактирование с открытым EditorFile удаленного файла

Теперь давайте рассмотрим удаленный файл, редактирования и отладки. Действия практически идентичны, есть только один момент, необходимо сначала выполнить: Введите наш сеанс PowerShell к удаленному серверу.

Для этого есть командлет для. Он называется `Enter-PSSession`.

Является упрощенная вниз объяснение командлета:

- `Enter-PSSession -ComputerName foo` запускает сеанс через WinRM
- `Enter-PSSession -ContainerId foo` и `Enter-PSSession -VmId foo` начать сеанс с помощью PowerShell Direct
- `Enter-PSSession -HostName foo` запускает сеанс по протоколу SSH

Дополнительные сведения о `Enter-PSSession`, ознакомьтесь с документацией [здесь](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/enter-pssession?view=powershell-6).

Я буду использовать SSH для удаленного взаимодействия, поскольку я собираюсь из macOS виртуальной Машины Ubuntu в Azure.

Во-первых в консоль, давайте запустим наш Enter-PSSession. Вы будете знать, находятся в сеанс, так как `[something]` будет отображаться слева от командном окне.

![Вызов Enter-PSSession](https://user-images.githubusercontent.com/2644648/34895896-7c18e0bc-f79c-11e7-9b36-6f4bd0e9b0db.png)

После этого мы можем конкретные шаги так, как если бы мы редактировали локальный сценарий.

1. Запустите `Open-EditorFile test.ps1` или `psedit test.ps1` для открытия удаленного `test.ps1` файл ![открытым-EditorFile файл test.ps1](https://user-images.githubusercontent.com/2644648/34895898-7c3e6a12-f79c-11e7-8bdf-549b591ecbcb.png)
2. Измените файл/Задание точек останова ![Измените и задайте точки останова](https://user-images.githubusercontent.com/2644648/34895892-7bb68246-f79c-11e7-8c0a-c2121773afbb.png)
3. Начать отладку (F5) удаленного файла

![Отладка удаленного файла](https://user-images.githubusercontent.com/2644648/34895895-7c040782-f79c-11e7-93ea-47724fa5c10d.png)

Это все, вот! Мы надеемся, что в этом руководстве помог прояснить возникнут вопросы по удаленной отладки и редактирования PowerShell в VSCode.

Если у вас возникли проблемы, вы можете открыть проблемы [в репозитории GitHub](http://github.com/powershell/vscode-powershell).
