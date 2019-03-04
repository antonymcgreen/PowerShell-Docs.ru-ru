---
ms.date: 06/05/2017
keywords: powershell,командлет
title: Изменение состояния компьютера
ms.assetid: 8093268b-27f8-4a49-8871-142c5cc33f01
ms.openlocfilehash: f2fadcedaeddfa6f8b9dd4d70738ee062b907d61
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 12/14/2018
ms.locfileid: "53403099"
---
# <a name="changing-computer-state"></a>Изменение состояния компьютера

Чтобы сбросить компьютер в Windows PowerShell, используйте стандартную программу командной строки или класс инструментария WMI. Хотя Windows PowerShell используется только для запуска программы, сведения об изменении состояния электропитания для компьютера в Windows PowerShell иллюстрируют некоторые важные особенности работы с внешними средствами в Windows PowerShell.

### <a name="locking-a-computer"></a>Блокировка компьютера

Единственным способом непосредственной блокировки компьютера с помощью стандартных средств является вызов функции **LockWorkstation()** в **user32.dll**:

```
rundll32.exe user32.dll,LockWorkStation
```

Эта команда немедленно блокирует рабочую станцию. Она использует *rundll32.exe*, который запускает библиотеки DLL Windows (и сохраняет их библиотеки для многократного использования), чтобы запустить user32.dll — библиотеку функций управления Windows.

Если рабочая станция блокируется при включенном быстром переключении пользователей, например, в Windows XP, на компьютере отображается экран входа в систему, а не заставка текущего пользователя.

Чтобы завершить работу конкретных сеансов на сервере терминалов, используйте программу командной строки **tsshutdn.exe**.

### <a name="logging-off-the-current-session"></a>Выход из текущего сеанса

Выйти из сеанса в локальной системе можно несколькими способами. Самый простой заключается в использовании программы командной строки удаленного рабочего стола или служб терминалов — **logoff.exe** (для получения дополнительных сведений введите **logoff /?** в командной строке Windows PowerShell). Чтобы выйти из текущего активного сеанса, введите **logoff** без аргументов.

Можно также использовать средство **shutdown.exe** с параметром выхода:

```
shutdown.exe -l
```

Третий вариант — использование инструментария WMI. Класс Win32_OperatingSystem имеет метод Win32Shutdown. Вызов метода с флагом 0 инициирует выход из системы:

```powershell
(Get-WmiObject -Class Win32_OperatingSystem -ComputerName .).Win32Shutdown(0)
```

Дополнительные сведения и другие возможности метода Win32Shutdown см. в статье Win32Shutdown Method of the Win32_OperatingSystem Class (Метод Win32Shutdown класса Win32_OperatingSystem) на сайте MSDN.

### <a name="shutting-down-or-restarting-a-computer"></a>Завершение работы или перезапуск компьютера

Завершение работы и перезапуск компьютеров обычно относятся к схожим типам задач. Средства, завершающие работу компьютера, обычно также перезапускают его и наоборот. Существует два варианта непосредственной перезагрузки компьютера из Windows PowerShell. Используйте Tsshutdn.exe или Shutdown.exe с соответствующими аргументами. Подробные сведения об использовании можно получить, запустив **tsshutdn.exe /?** или **shutdown.exe /?**.

Операции завершения работы и перезапуска можно также выполнять непосредственно из Windows PowerShell.

Чтобы завершить работу компьютера, используйте команду Stop-Computer.

```powershell
Stop-Computer
```

Чтобы перезапустить операционную систему, используйте команду Restart-Computer.

```powershell
Restart-Computer
```

Чтобы выполнить немедленную перезагрузку компьютера, используйте параметр -Force.

```powershell
Restart-Computer -Force
```