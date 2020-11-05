---
ms.date: 06/12/2017
keywords: wmf,powershell,установка
title: Усовершенствования отладки сценариев PowerShell
description: WMF 5.0 добавляет новые функции отладки в Windows PowerShell.
ms.openlocfilehash: 5703343e1b85024931638e8b04a09f7208ea123c
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92646733"
---
# <a name="improvements-in-powershell-script-debugging"></a><span data-ttu-id="31a64-104">Усовершенствования отладки сценариев PowerShell</span><span class="sxs-lookup"><span data-stu-id="31a64-104">Improvements in PowerShell Script Debugging</span></span>

<span data-ttu-id="31a64-105">PowerShell 5.0 включает несколько улучшений для более эффективной отладки.</span><span class="sxs-lookup"><span data-stu-id="31a64-105">PowerShell 5.0 includes several improvements that enhance the debugging experience.</span></span>

## <a name="break-all"></a><span data-ttu-id="31a64-106">Команда "Прервать все"</span><span class="sxs-lookup"><span data-stu-id="31a64-106">Break All</span></span>

<span data-ttu-id="31a64-107">Консоль PowerShell и интегрированная среда сценариев PowerShell теперь позволяют переходить в режим отладчика при выполнении скриптов.</span><span class="sxs-lookup"><span data-stu-id="31a64-107">The PowerShell console and PowerShell ISE now allow you to break into the debugger for running scripts.</span></span> <span data-ttu-id="31a64-108">Это работает как в локальных, так и в удаленных сеансах.</span><span class="sxs-lookup"><span data-stu-id="31a64-108">This works in both local and remote sessions.</span></span>

<span data-ttu-id="31a64-109">В окне консоли нажмите клавиши <kbd>Ctrl</kbd>+<kbd>Break</kbd>.</span><span class="sxs-lookup"><span data-stu-id="31a64-109">In the console, press <kbd>Ctrl</kbd>+<kbd>Break</kbd>.</span></span>

<span data-ttu-id="31a64-110">В интегрированной среде сценариев нажмите клавиши <kbd>Ctrl</kbd>+<kbd>B</kbd> или воспользуйтесь командой меню **Отладка -> Прервать все**.</span><span class="sxs-lookup"><span data-stu-id="31a64-110">In ISE, press <kbd>Ctrl</kbd>+<kbd>B</kbd>, or use the **Debug -> Break All** menu command.</span></span>

## <a name="remote-debugging-and-remote-file-editing-in-powershell-ise"></a><span data-ttu-id="31a64-111">Удаленная отладка и удаленное редактирование файлов в интегрированной среде сценариев PowerShell</span><span class="sxs-lookup"><span data-stu-id="31a64-111">Remote debugging and remote file editing in PowerShell ISE</span></span>

<span data-ttu-id="31a64-112">Теперь среда PowerShell позволяет открывать и редактировать файлы в удаленном сеансе с помощью команды PSEdit.</span><span class="sxs-lookup"><span data-stu-id="31a64-112">PowerShell ISE now lets you open and edit files in a remote session by running the PSEdit command.</span></span>
<span data-ttu-id="31a64-113">Например, во время удаленного сеанса можно открыть файл для редактирования из командной строки, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="31a64-113">For example, you can open a file for editing from the command line in a remote session as follows:</span></span>

```powershell
[RemoteComputer1]: PS C:\> PSEdit C:\DebugDemoScripts\Test-GetMutex.ps1
```

<span data-ttu-id="31a64-114">Кроме того, вы можете вносить изменения и сохранять их в удаленном файле, который автоматически открывается в интегрированной среде сценариев PowerShell при попадании в точку останова.</span><span class="sxs-lookup"><span data-stu-id="31a64-114">In addition, you can now edit and save changes in a remote file that is automatically opened in PowerShell ISE when you hit a breakpoint.</span></span> <span data-ttu-id="31a64-115">Теперь можно выполнить отладку файла сценария, выполняемого на удаленном компьютере, отредактировать файл, чтобы исправить ошибку, а затем снова запустить обновленный сценарий.</span><span class="sxs-lookup"><span data-stu-id="31a64-115">Now, you can debug a script file that is running on a remote computer, edit the file to fix an error, and then rerun the modified script.</span></span>

## <a name="advanced-script-debugging"></a><span data-ttu-id="31a64-116">Расширенная отладка сценариев</span><span class="sxs-lookup"><span data-stu-id="31a64-116">Advanced Script Debugging</span></span>

<span data-ttu-id="31a64-117">Стали доступны новые расширенные функции отладки, которые позволяют подключиться к любому процессу локального компьютера, загруженному в PowerShell, и осуществить отладку произвольных пространств выполнения в нем.</span><span class="sxs-lookup"><span data-stu-id="31a64-117">There are new, advanced debugging features that let you attach to any local computer process that has loaded PowerShell, and debug arbitrary runspaces in that process.</span></span>

### <a name="runspace-debugging"></a><span data-ttu-id="31a64-118">Отладка пространств выполнения</span><span class="sxs-lookup"><span data-stu-id="31a64-118">Runspace Debugging</span></span>

<span data-ttu-id="31a64-119">Были добавлены новые командлеты, позволяющие вывести список текущих пространств выполнения в процессе, а также подключить консоль PowerShell или отладчик интегрированной среды сценариев к такому пространству для отладки сценариев:</span><span class="sxs-lookup"><span data-stu-id="31a64-119">New cmdlets have been added that let you list current runspaces in a process, and attach the PowerShell console or PowerShell ISE debugger to that runspace for script debugging:</span></span>

- <span data-ttu-id="31a64-120">Get-Runspace</span><span class="sxs-lookup"><span data-stu-id="31a64-120">Get-Runspace</span></span>
- <span data-ttu-id="31a64-121">Debug-Runspace</span><span class="sxs-lookup"><span data-stu-id="31a64-121">Debug-Runspace</span></span>
- <span data-ttu-id="31a64-122">Enable-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="31a64-122">Enable-RunspaceDebug</span></span>
- <span data-ttu-id="31a64-123">Disable-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="31a64-123">Disable-RunspaceDebug</span></span>
- <span data-ttu-id="31a64-124">Get-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="31a64-124">Get-RunspaceDebug</span></span>

### <a name="attach-to-process-hosting-powershell"></a><span data-ttu-id="31a64-125">Подключение к процессу, в котором размещается PowerShell</span><span class="sxs-lookup"><span data-stu-id="31a64-125">Attach to Process hosting PowerShell</span></span>

<span data-ttu-id="31a64-126">Теперь вы можете подключиться к любому процессу компьютера с загруженным PowerShell.</span><span class="sxs-lookup"><span data-stu-id="31a64-126">You can now attach to any computer process that has PowerShell loaded.</span></span> <span data-ttu-id="31a64-127">Чтобы сделать это, войдите в интерактивный сеанс с процессом узла.</span><span class="sxs-lookup"><span data-stu-id="31a64-127">You do this by entering into an interactive session with the host process.</span></span> <span data-ttu-id="31a64-128">Дополнительные сведения см. в разделе:</span><span class="sxs-lookup"><span data-stu-id="31a64-128">For more information, see:</span></span>

- [<span data-ttu-id="31a64-129">Enter-PSHostProcess</span><span class="sxs-lookup"><span data-stu-id="31a64-129">Enter-PSHostProcess</span></span>](/powershell/module/Microsoft.PowerShell.Core/Enter-PSHostProcess)
- [<span data-ttu-id="31a64-130">Exit-PSHostProcess</span><span class="sxs-lookup"><span data-stu-id="31a64-130">Exit-PSHostProcess</span></span>](/powershell/module/Microsoft.PowerShell.Core/Exit-PSHostProcess)
