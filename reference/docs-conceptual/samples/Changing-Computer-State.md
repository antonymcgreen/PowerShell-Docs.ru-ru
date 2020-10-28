---
ms.date: 12/23/2019
keywords: powershell,командлет
title: Изменение состояния компьютера
description: В этом примере показано, как можно использовать внешние команды из PowerShell для управления конфигурацией компьютера.
ms.openlocfilehash: 341f29f24d7e4bd341ccc0954b16d4b75880678b
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2020
ms.locfileid: "92500680"
---
# <a name="changing-computer-state"></a><span data-ttu-id="ebe48-104">Изменение состояния компьютера</span><span class="sxs-lookup"><span data-stu-id="ebe48-104">Changing Computer State</span></span>

<span data-ttu-id="ebe48-105">Чтобы вернуть компьютер в исходное состояние в PowerShell, используйте стандартную программу командной строки, инструментарий WMI или класс CIM.</span><span class="sxs-lookup"><span data-stu-id="ebe48-105">To reset a computer in PowerShell, use either a standard command-line tool, WMI, or a CIM class.</span></span>
<span data-ttu-id="ebe48-106">Хотя PowerShell используется только для запуска программы, сведения об изменении состояния электропитания для компьютера в PowerShell иллюстрируют некоторые важные особенности работы с внешними средствами в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ebe48-106">Although you are using PowerShell only to run the tool, learning how to change a computer's power state in PowerShell illustrates some of the important details about working with external tools in PowerShell.</span></span>

## <a name="locking-a-computer"></a><span data-ttu-id="ebe48-107">Блокировка компьютера</span><span class="sxs-lookup"><span data-stu-id="ebe48-107">Locking a Computer</span></span>

<span data-ttu-id="ebe48-108">Единственным способом непосредственной блокировки компьютера с помощью стандартных средств является вызов функции **LockWorkstation()** в **user32.dll** :</span><span class="sxs-lookup"><span data-stu-id="ebe48-108">The only way to lock a computer directly with the standard available tools is to call the **LockWorkstation()** function in **user32.dll** :</span></span>

```powershell
rundll32.exe user32.dll,LockWorkStation
```

<span data-ttu-id="ebe48-109">Эта команда немедленно блокирует рабочую станцию.</span><span class="sxs-lookup"><span data-stu-id="ebe48-109">This command immediately locks the workstation.</span></span> <span data-ttu-id="ebe48-110">Она использует **rundll32.exe** , который запускает библиотеки DLL Windows (и сохраняет их библиотеки для многократного использования), чтобы запустить `user32.dll` — библиотеку функций управления Windows.</span><span class="sxs-lookup"><span data-stu-id="ebe48-110">It uses **rundll32.exe** , which runs Windows DLLs (and saves their libraries for repeated use) to run `user32.dll`, a library of Windows management functions.</span></span>

<span data-ttu-id="ebe48-111">Если рабочая станция блокируется при включенном быстром переключении пользователей, например в Windows XP, компьютер отображает экран входа в систему вместо того, чтобы запустить заставку текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="ebe48-111">When you lock a workstation while Fast User Switching is enabled, such as on Windows XP, the computer displays the user logon screen rather than starting the current user's screensaver.</span></span>

<span data-ttu-id="ebe48-112">Чтобы завершить работу конкретных сеансов на сервере терминалов, используйте программу командной строки **tsshutdn.exe** .</span><span class="sxs-lookup"><span data-stu-id="ebe48-112">To shut down particular sessions on a Terminal Server, use the **tsshutdn.exe** command-line tool.</span></span>

## <a name="logging-off-the-current-session"></a><span data-ttu-id="ebe48-113">Выход из текущего сеанса</span><span class="sxs-lookup"><span data-stu-id="ebe48-113">Logging Off the Current Session</span></span>

<span data-ttu-id="ebe48-114">Выйти из сеанса в локальной системе можно несколькими способами.</span><span class="sxs-lookup"><span data-stu-id="ebe48-114">You can use several different techniques to log off of a session on the local system.</span></span> <span data-ttu-id="ebe48-115">Самый простой заключается в использовании программы командной строки удаленного рабочего стола или служб терминалов — **logoff.exe** (для получения дополнительных сведений введите `logoff /?` в командной строке PowerShell).</span><span class="sxs-lookup"><span data-stu-id="ebe48-115">The simplest way is to use the Remote Desktop/Terminal Services command-line tool, **logoff.exe** (For details, at the PowerShell prompt, type `logoff /?`).</span></span> <span data-ttu-id="ebe48-116">Чтобы выйти из текущего активного сеанса, введите `logoff` без аргументов.</span><span class="sxs-lookup"><span data-stu-id="ebe48-116">To log off the current active session, type `logoff` with no arguments.</span></span>

<span data-ttu-id="ebe48-117">Можно также использовать средство **shutdown.exe** с параметром выхода:</span><span class="sxs-lookup"><span data-stu-id="ebe48-117">You can also use the **shutdown.exe** tool with its logoff option:</span></span>

```powershell
shutdown.exe -l
```

<span data-ttu-id="ebe48-118">Еще один вариант — использование инструментария WMI.</span><span class="sxs-lookup"><span data-stu-id="ebe48-118">Another option is to use WMI.</span></span> <span data-ttu-id="ebe48-119">Класс **Win32_OperatingSystem** имеет метод **Shutdown** .</span><span class="sxs-lookup"><span data-stu-id="ebe48-119">The **Win32_OperatingSystem** class has a **Shutdown** method.</span></span>
<span data-ttu-id="ebe48-120">Вызов метода с флагом 0 инициирует выход из системы:</span><span class="sxs-lookup"><span data-stu-id="ebe48-120">Invoking the method with the 0 flag initiates logoff:</span></span>

<span data-ttu-id="ebe48-121">Дополнительные сведения о методе **Shutdown** класса Win32_OperatingSystem см. в [этой статье](/windows/win32/cimwin32prov/shutdown-method-in-class-win32-operatingsystem).</span><span class="sxs-lookup"><span data-stu-id="ebe48-121">For more information about the **Shutdown** method, see [Shutdown method of the Win32_OperatingSystem class](/windows/win32/cimwin32prov/shutdown-method-in-class-win32-operatingsystem)</span></span>

```powershell
Get-CimInstance -Classname Win32_OperatingSystem | Invoke-CimMethod -MethodName Shutdown
```

## <a name="shutting-down-or-restarting-a-computer"></a><span data-ttu-id="ebe48-122">Завершение работы или перезапуск компьютера</span><span class="sxs-lookup"><span data-stu-id="ebe48-122">Shutting Down or Restarting a Computer</span></span>

<span data-ttu-id="ebe48-123">Завершение работы и перезапуск компьютеров обычно относятся к схожим типам задач.</span><span class="sxs-lookup"><span data-stu-id="ebe48-123">Shutting down and restarting computers are generally the same types of task.</span></span> <span data-ttu-id="ebe48-124">Средства, завершающие работу компьютера, обычно также перезапускают его и наоборот.</span><span class="sxs-lookup"><span data-stu-id="ebe48-124">Tools that shut down a computer will generally restart it as well—and vice versa.</span></span> <span data-ttu-id="ebe48-125">Есть два варианта непосредственной перезагрузки компьютера из PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ebe48-125">There are two straightforward options for restarting a computer from PowerShell.</span></span> <span data-ttu-id="ebe48-126">Используйте **tsshutdn.exe** или **shutdown.exe** с соответствующими аргументами.</span><span class="sxs-lookup"><span data-stu-id="ebe48-126">Use either **tsshutdn.exe** or **shutdown.exe** with appropriate arguments.</span></span> <span data-ttu-id="ebe48-127">Подробные сведения об использовании можно получить, запустив `tsshutdn.exe /?` или `shutdown.exe /?`.</span><span class="sxs-lookup"><span data-stu-id="ebe48-127">You can get detailed usage information from `tsshutdn.exe /?` or `shutdown.exe /?`.</span></span>

<span data-ttu-id="ebe48-128">Операции завершения работы и перезапуска можно также выполнять непосредственно из PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ebe48-128">You can also perform shutdown and restart operations directly from PowerShell as well.</span></span>

<span data-ttu-id="ebe48-129">Чтобы завершить работу компьютера, используйте команду Stop-Computer.</span><span class="sxs-lookup"><span data-stu-id="ebe48-129">To shut down the computer, use the Stop-Computer command</span></span>

```powershell
Stop-Computer
```

<span data-ttu-id="ebe48-130">Чтобы перезапустить операционную систему, используйте команду Restart-Computer.</span><span class="sxs-lookup"><span data-stu-id="ebe48-130">To restart the operating system, use the Restart-Computer command</span></span>

```powershell
Restart-Computer
```

<span data-ttu-id="ebe48-131">Чтобы выполнить немедленную перезагрузку компьютера, используйте параметр -Force.</span><span class="sxs-lookup"><span data-stu-id="ebe48-131">To force an immediate restart of the computer, use the -Force parameter.</span></span>

```powershell
Restart-Computer -Force
```
