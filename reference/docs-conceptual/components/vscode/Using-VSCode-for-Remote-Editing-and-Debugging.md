---
title: Удаленные редактирование и отладка в Visual Studio Code
description: Удаленные редактирование и отладка в Visual Studio Code
ms.date: 06/13/2019
ms.openlocfilehash: ae3b7a3709498fcd547a48d0849b0dc880217225
ms.sourcegitcommit: 13f24786ed39ca1c07eff2b73a1974c366e31cb8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2019
ms.locfileid: "67264009"
---
# <a name="using-visual-studio-code-for-remote-editing-and-debugging"></a><span data-ttu-id="0de40-103">Удаленные редактирование и отладка в Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="0de40-103">Using Visual Studio Code for remote editing and debugging</span></span>

<span data-ttu-id="0de40-104">Каждый пользователь, знакомый с ISE, может вспомнить, как запускать `psedit file.ps1` из встроенной консоли, чтобы открыть локальные или удаленные файлы прямо в интегрированной среде сценариев.</span><span class="sxs-lookup"><span data-stu-id="0de40-104">For those of you that are familiar with the ISE, you may recall that you could run `psedit file.ps1` from the integrated console to open files - local or remote - right in the ISE.</span></span>

<span data-ttu-id="0de40-105">Эта функция также доступна в расширении PowerShell для VSCode.</span><span class="sxs-lookup"><span data-stu-id="0de40-105">This feature is also available in the PowerShell extension for VSCode.</span></span> <span data-ttu-id="0de40-106">В этом руководстве показано, как это сделать.</span><span class="sxs-lookup"><span data-stu-id="0de40-106">This guide shows you how to do it.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0de40-107">Необходимые компоненты</span><span class="sxs-lookup"><span data-stu-id="0de40-107">Prerequisites</span></span>

<span data-ttu-id="0de40-108">В этом руководстве предполагается, что у вас есть:</span><span class="sxs-lookup"><span data-stu-id="0de40-108">This guide assumes that you have:</span></span>

- <span data-ttu-id="0de40-109">удаленный ресурс (например, виртуальная машина, контейнер), к которому у вас есть доступ;</span><span class="sxs-lookup"><span data-stu-id="0de40-109">A remote resource (ex: a VM, a container) that you have access to</span></span>
- <span data-ttu-id="0de40-110">PowerShell, работающий на нем и на основном компьютере;</span><span class="sxs-lookup"><span data-stu-id="0de40-110">PowerShell running on it and the host machine</span></span>
- <span data-ttu-id="0de40-111">VSCode и расширение PowerShell для VSCode.</span><span class="sxs-lookup"><span data-stu-id="0de40-111">VSCode and the PowerShell extension for VSCode</span></span>

<span data-ttu-id="0de40-112">Эта возможность работает с Windows PowerShell и PowerShell Core.</span><span class="sxs-lookup"><span data-stu-id="0de40-112">This feature works on Windows PowerShell and PowerShell Core.</span></span>

<span data-ttu-id="0de40-113">Эта возможность также работает при подключении к удаленному компьютеру с помощью WinRM, PowerShell Direct или SSH.</span><span class="sxs-lookup"><span data-stu-id="0de40-113">This feature also works when connecting to a remote machine via WinRM, PowerShell Direct, or SSH.</span></span> <span data-ttu-id="0de40-114">Если вы хотите использовать SSH, но используете Windows, ознакомьтесь с [версией SSH Win32](https://github.com/PowerShell/Win32-OpenSSH).</span><span class="sxs-lookup"><span data-stu-id="0de40-114">If you want to use SSH, but are using Windows, check out the [Win32 version of SSH](https://github.com/PowerShell/Win32-OpenSSH)!</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0de40-115">Команды `Open-EditorFile` и `psedit` работают только в **интегрированной консоли PowerShell**, созданной с помощью расширения PowerShell для VSCode.</span><span class="sxs-lookup"><span data-stu-id="0de40-115">The `Open-EditorFile` and `psedit` commands only work in the **PowerShell Integrated Console** created by the PowerShell extension for VSCode.</span></span>

## <a name="usage-examples"></a><span data-ttu-id="0de40-116">Примеры использования</span><span class="sxs-lookup"><span data-stu-id="0de40-116">Usage examples</span></span>

<span data-ttu-id="0de40-117">В этих примерах демонстрируется удаленное редактирование и отладка виртуальной машины Ubuntu, которая запущена в Azure, с MacBook Pro.</span><span class="sxs-lookup"><span data-stu-id="0de40-117">These examples show remote editing and debugging from a MacBook Pro to an Ubuntu VM running in Azure.</span></span> <span data-ttu-id="0de40-118">Процесс для Windows идентичен.</span><span class="sxs-lookup"><span data-stu-id="0de40-118">The process is identical on Windows.</span></span>

### <a name="local-file-editing-with-open-editorfile"></a><span data-ttu-id="0de40-119">Редактирование локального файла с помощью открытого редактора файлов</span><span class="sxs-lookup"><span data-stu-id="0de40-119">Local file editing with Open-EditorFile</span></span>

<span data-ttu-id="0de40-120">С помощью расширения PowerShell для VSCode и открытой интегрированной консоли PowerShell напечатайте `Open-EditorFile foo.ps1` или `psedit foo.ps1`, чтобы открыть локальный файл foo.ps1 прямо в редакторе.</span><span class="sxs-lookup"><span data-stu-id="0de40-120">With the PowerShell extension for VSCode started and the PowerShell Integrated Console opened, we can type `Open-EditorFile foo.ps1` or `psedit foo.ps1` to open the local foo.ps1 file right in the editor.</span></span>

![Файл foo.ps1 в открытом редакторе файлов работает локально](images/Using-VSCode-for-Remote-Editing-and-Debugging/1-open-local-file.png)

>[!NOTE]
> <span data-ttu-id="0de40-122">Файл `foo.ps1` должен уже существовать.</span><span class="sxs-lookup"><span data-stu-id="0de40-122">The file `foo.ps1` must already exist.</span></span>

<span data-ttu-id="0de40-123">После этого вы можете сделать следующее.</span><span class="sxs-lookup"><span data-stu-id="0de40-123">From there, we can:</span></span>

- <span data-ttu-id="0de40-124">Добавить точки останова во внутреннее поле.</span><span class="sxs-lookup"><span data-stu-id="0de40-124">Add breakpoints to the gutter</span></span>

  ![добавление точки останова во внутреннее поле](images/Using-VSCode-for-Remote-Editing-and-Debugging/2-adding-breakpoint-gutter.png)

- <span data-ttu-id="0de40-126">Нажать клавишу F5 для отладки сценария PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0de40-126">Hit F5 to debug the PowerShell script.</span></span>

  ![отладка локального скрипта PowerShell](images/Using-VSCode-for-Remote-Editing-and-Debugging/3-local-debug.png)

<span data-ttu-id="0de40-128">Во время отладки можно взаимодействовать с консолью отладки, ознакомиться с переменными в левой области и другими стандартными средствами отладки.</span><span class="sxs-lookup"><span data-stu-id="0de40-128">While debugging, you can interact with the debug console, check out the variables in the scope on the left, and all the other standard debugging tools.</span></span>

### <a name="remote-file-editing-with-open-editorfile"></a><span data-ttu-id="0de40-129">Редактирование удаленного файла с помощью открытого редактора файлов</span><span class="sxs-lookup"><span data-stu-id="0de40-129">Remote file editing with Open-EditorFile</span></span>

<span data-ttu-id="0de40-130">Теперь давайте приступим к редактированию и отладке удаленного файла.</span><span class="sxs-lookup"><span data-stu-id="0de40-130">Now let's get into remote file editing and debugging.</span></span> <span data-ttu-id="0de40-131">Шаги практически одинаковы, но в первую очередь нам нужно начать сеанс PowerShell на удаленном сервере.</span><span class="sxs-lookup"><span data-stu-id="0de40-131">The steps are nearly the same, there's just one thing we need to do first - enter our PowerShell session to the remote server.</span></span>

<span data-ttu-id="0de40-132">Для этого существует командлет.</span><span class="sxs-lookup"><span data-stu-id="0de40-132">There's a cmdlet for to do so.</span></span> <span data-ttu-id="0de40-133">Он называется `Enter-PSSession`.</span><span class="sxs-lookup"><span data-stu-id="0de40-133">It's called `Enter-PSSession`.</span></span>

<span data-ttu-id="0de40-134">Проще говоря, командлет действует так:</span><span class="sxs-lookup"><span data-stu-id="0de40-134">The watered down explanation of the cmdlet is:</span></span>

- <span data-ttu-id="0de40-135">`Enter-PSSession -ComputerName foo` запускает сеанс через WinRM;</span><span class="sxs-lookup"><span data-stu-id="0de40-135">`Enter-PSSession -ComputerName foo` starts a session via WinRM</span></span>
- <span data-ttu-id="0de40-136">`Enter-PSSession -ContainerId foo` и `Enter-PSSession -VmId foo` начинают сеанс с помощью PowerShell Direct;</span><span class="sxs-lookup"><span data-stu-id="0de40-136">`Enter-PSSession -ContainerId foo` and `Enter-PSSession -VmId foo` start a session via PowerShell Direct</span></span>
- <span data-ttu-id="0de40-137">`Enter-PSSession -HostName foo` запускает сеанс через SSH.</span><span class="sxs-lookup"><span data-stu-id="0de40-137">`Enter-PSSession -HostName foo` starts a session via SSH</span></span>

<span data-ttu-id="0de40-138">Дополнительные сведения см. в документации [Enter-PSSession](/powershell/module/microsoft.powershell.core/enter-pssession).</span><span class="sxs-lookup"><span data-stu-id="0de40-138">For more information, see the documentation for [Enter-PSSession](/powershell/module/microsoft.powershell.core/enter-pssession).</span></span>

<span data-ttu-id="0de40-139">Для удаленного взаимодействия используется SSH, так как мы будем работать с macOS в виртуальной машине Ubuntu в Azure.</span><span class="sxs-lookup"><span data-stu-id="0de40-139">Since we are going from macOS to an Ubuntu VM in Azure, we are using SSH for remoting.</span></span>

<span data-ttu-id="0de40-140">Сначала в интегрированной консоли запустите `Enter-PSSession`.</span><span class="sxs-lookup"><span data-stu-id="0de40-140">First, in the Integrated Console, run `Enter-PSSession`.</span></span> <span data-ttu-id="0de40-141">Вы подключены к удаленному сеансу, когда `[<hostname>]` отображается слева от командной строки.</span><span class="sxs-lookup"><span data-stu-id="0de40-141">You're connected to the remote session when `[<hostname>]` shows up to the left of your prompt.</span></span>

![Вызов Enter-PSSession](images/Using-VSCode-for-Remote-Editing-and-Debugging/4-enter-pssession.png)

<span data-ttu-id="0de40-143">Теперь мы можем выполнить те же шаги, что и при редактировании локального скрипта.</span><span class="sxs-lookup"><span data-stu-id="0de40-143">Now, we can do the same steps as if we are editing a local script.</span></span>

1. <span data-ttu-id="0de40-144">Чтобы открыть удаленный файл `test.ps1`, запустите `Open-EditorFile test.ps1` или `psedit test.ps1`.</span><span class="sxs-lookup"><span data-stu-id="0de40-144">Run `Open-EditorFile test.ps1` or `psedit test.ps1` to open the remote `test.ps1` file</span></span>

  ![Открытый файл test.ps1 в редакторе файлов](images/Using-VSCode-for-Remote-Editing-and-Debugging/5-open-remote-file.png)

1. <span data-ttu-id="0de40-146">Отредактируйте файл, установите точки останова.</span><span class="sxs-lookup"><span data-stu-id="0de40-146">Edit the file/set breakpoints</span></span>

   ![Редактирование и установка точек останова](images/Using-VSCode-for-Remote-Editing-and-Debugging/6-set-breakpoints.png)

1. <span data-ttu-id="0de40-148">Начните отладку (F5) удаленного файла.</span><span class="sxs-lookup"><span data-stu-id="0de40-148">Start debugging (F5) the remote file</span></span>

   ![Отладка удаленного файла](images/Using-VSCode-for-Remote-Editing-and-Debugging/7-start-debugging.png)

<span data-ttu-id="0de40-150">Если у вас возникли проблемы, вы можете писать вопросы [в репозитории GitHub](https://github.com/powershell/vscode-powershell).</span><span class="sxs-lookup"><span data-stu-id="0de40-150">If you have any problems, you can open issues in the [GitHub repo](https://github.com/powershell/vscode-powershell).</span></span>
