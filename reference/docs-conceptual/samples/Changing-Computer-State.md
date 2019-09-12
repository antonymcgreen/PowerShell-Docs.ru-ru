---
ms.date: 06/05/2017
keywords: powershell,командлет
title: Изменение состояния компьютера
ms.openlocfilehash: de3e31e358548943a015b7bba275c4461202b20f
ms.sourcegitcommit: d1ba596f9e0d4df9565601a70687a126d535c917
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2019
ms.locfileid: "70386286"
---
# <a name="changing-computer-state"></a><span data-ttu-id="55323-103">Изменение состояния компьютера</span><span class="sxs-lookup"><span data-stu-id="55323-103">Changing Computer State</span></span>

<span data-ttu-id="55323-104">Чтобы вернуть компьютер в исходное состояние в Windows PowerShell, используйте стандартную программу командной строки, инструментарий WMI или класс CIM.</span><span class="sxs-lookup"><span data-stu-id="55323-104">To reset a computer in Windows PowerShell, use either a standard command-line tool, WMI or CIM class.</span></span> <span data-ttu-id="55323-105">Хотя Windows PowerShell используется только для запуска программы, сведения об изменении состояния электропитания для компьютера в Windows PowerShell иллюстрируют некоторые важные особенности работы с внешними средствами в Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="55323-105">Although you are using Windows PowerShell only to run the tool, learning how to change a computer's power state in Windows PowerShell illustrates some of the important details about working with external tools in Windows PowerShell.</span></span>

## <a name="locking-a-computer"></a><span data-ttu-id="55323-106">Блокировка компьютера</span><span class="sxs-lookup"><span data-stu-id="55323-106">Locking a Computer</span></span>

<span data-ttu-id="55323-107">Единственным способом непосредственной блокировки компьютера с помощью стандартных средств является вызов функции **LockWorkstation()** в **user32.dll**:</span><span class="sxs-lookup"><span data-stu-id="55323-107">The only way to lock a computer directly with the standard available tools is to call the **LockWorkstation()** function in **user32.dll**:</span></span>

```
rundll32.exe user32.dll,LockWorkStation
```

<span data-ttu-id="55323-108">Эта команда немедленно блокирует рабочую станцию.</span><span class="sxs-lookup"><span data-stu-id="55323-108">This command immediately locks the workstation.</span></span> <span data-ttu-id="55323-109">Она использует *rundll32.exe*, который запускает библиотеки DLL Windows (и сохраняет их библиотеки для многократного использования), чтобы запустить user32.dll — библиотеку функций управления Windows.</span><span class="sxs-lookup"><span data-stu-id="55323-109">It uses *rundll32.exe*, which runs Windows DLLs (and saves their libraries for repeated use) to run user32.dll, a library of Windows management functions.</span></span>

<span data-ttu-id="55323-110">Если рабочая станция блокируется при включенном быстром переключении пользователей, например, в Windows XP, на компьютере отображается экран входа в систему, а не заставка текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="55323-110">When you lock a workstation while Fast User Switching is enabled, such as on Windows XP, the computer displays the user logon screen rather than starting the current user's screensaver.</span></span>

<span data-ttu-id="55323-111">Чтобы завершить работу конкретных сеансов на сервере терминалов, используйте программу командной строки **tsshutdn.exe**.</span><span class="sxs-lookup"><span data-stu-id="55323-111">To shut down particular sessions on a Terminal Server, use the **tsshutdn.exe** command-line tool.</span></span>

## <a name="logging-off-the-current-session"></a><span data-ttu-id="55323-112">Выход из текущего сеанса</span><span class="sxs-lookup"><span data-stu-id="55323-112">Logging Off the Current Session</span></span>

<span data-ttu-id="55323-113">Выйти из сеанса в локальной системе можно несколькими способами.</span><span class="sxs-lookup"><span data-stu-id="55323-113">You can use several different techniques to log off of a session on the local system.</span></span> <span data-ttu-id="55323-114">Самый простой заключается в использовании программы командной строки удаленного рабочего стола или служб терминалов — **logoff.exe** (для получения дополнительных сведений введите **logoff /?** в командной строке Windows PowerShell).</span><span class="sxs-lookup"><span data-stu-id="55323-114">The simplest way is to use the Remote Desktop/Terminal Services command-line tool, **logoff.exe** (For details, at the Windows PowerShell prompt, type **logoff /?**).</span></span> <span data-ttu-id="55323-115">Чтобы выйти из текущего активного сеанса, введите **logoff** без аргументов.</span><span class="sxs-lookup"><span data-stu-id="55323-115">To log off the current active session, type **logoff** with no arguments.</span></span>

<span data-ttu-id="55323-116">Можно также использовать средство **shutdown.exe** с параметром выхода:</span><span class="sxs-lookup"><span data-stu-id="55323-116">You can also use the **shutdown.exe** tool with its logoff option:</span></span>

```
shutdown.exe -l
```

<span data-ttu-id="55323-117">Еще один вариант — использование инструментария WMI.</span><span class="sxs-lookup"><span data-stu-id="55323-117">Another option is to use WMI.</span></span> <span data-ttu-id="55323-118">Класс Win32_OperatingSystem имеет метод Win32Shutdown.</span><span class="sxs-lookup"><span data-stu-id="55323-118">The Win32_OperatingSystem class has a Win32Shutdown method.</span></span> <span data-ttu-id="55323-119">Вызов метода с флагом 0 инициирует выход из системы:</span><span class="sxs-lookup"><span data-stu-id="55323-119">Invoking the method with the 0 flag initiates logoff:</span></span>

```powershell
(Get-WmiObject -Class Win32_OperatingSystem -ComputerName .).Win32Shutdown(0)
```

<span data-ttu-id="55323-120">Дополнительные сведения и другие возможности метода Win32Shutdown см. в статье Win32Shutdown Method of the Win32_OperatingSystem Class (Метод Win32Shutdown класса Win32_OperatingSystem) на сайте MSDN.</span><span class="sxs-lookup"><span data-stu-id="55323-120">For more information, and to find other features of the Win32Shutdown method, see "Win32Shutdown Method of the Win32_OperatingSystem Class" in MSDN.</span></span>

<span data-ttu-id="55323-121">Наконец, можно использовать CIM с тем же классом Win32_OperatingSystem, как описано выше в методе WMI.</span><span class="sxs-lookup"><span data-stu-id="55323-121">Finally you can use CIM with the same Win32_OperatingSystem class as described above in the WMI method.</span></span>

```powershell
Get-CIMInstance -Classname Win32_OperatingSystem | Invoke-CimMethod -MethodName Shutdown
```

## <a name="shutting-down-or-restarting-a-computer"></a><span data-ttu-id="55323-122">Завершение работы или перезапуск компьютера</span><span class="sxs-lookup"><span data-stu-id="55323-122">Shutting Down or Restarting a Computer</span></span>

<span data-ttu-id="55323-123">Завершение работы и перезапуск компьютеров обычно относятся к схожим типам задач.</span><span class="sxs-lookup"><span data-stu-id="55323-123">Shutting down and restarting computers are generally the same types of task.</span></span> <span data-ttu-id="55323-124">Средства, завершающие работу компьютера, обычно также перезапускают его и наоборот.</span><span class="sxs-lookup"><span data-stu-id="55323-124">Tools that shut down a computer will generally restart it as well—and vice versa.</span></span> <span data-ttu-id="55323-125">Существует два варианта непосредственной перезагрузки компьютера из Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="55323-125">There are two straightforward options for restarting a computer from Windows PowerShell.</span></span> <span data-ttu-id="55323-126">Используйте Tsshutdn.exe или Shutdown.exe с соответствующими аргументами.</span><span class="sxs-lookup"><span data-stu-id="55323-126">Use either Tsshutdn.exe or Shutdown.exe with appropriate arguments.</span></span> <span data-ttu-id="55323-127">Подробные сведения об использовании можно получить, запустив **tsshutdn.exe /?**</span><span class="sxs-lookup"><span data-stu-id="55323-127">You can get detailed usage information from **tsshutdn.exe /?**</span></span> <span data-ttu-id="55323-128">или **shutdown.exe /?** .</span><span class="sxs-lookup"><span data-stu-id="55323-128">or **shutdown.exe /?**.</span></span>

<span data-ttu-id="55323-129">Операции завершения работы и перезапуска можно также выполнять непосредственно из Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="55323-129">You can also perform shutdown and restart operations directly from Windows PowerShell as well.</span></span>

<span data-ttu-id="55323-130">Чтобы завершить работу компьютера, используйте команду Stop-Computer.</span><span class="sxs-lookup"><span data-stu-id="55323-130">To shut down the computer, use the Stop-Computer command</span></span>

```powershell
Stop-Computer
```

<span data-ttu-id="55323-131">Чтобы перезапустить операционную систему, используйте команду Restart-Computer.</span><span class="sxs-lookup"><span data-stu-id="55323-131">To restart the operating system, use the Restart-Computer command</span></span>

```powershell
Restart-Computer
```

<span data-ttu-id="55323-132">Чтобы выполнить немедленную перезагрузку компьютера, используйте параметр -Force.</span><span class="sxs-lookup"><span data-stu-id="55323-132">To force an immediate restart of the computer, use the -Force parameter.</span></span>

```powershell
Restart-Computer -Force
```
