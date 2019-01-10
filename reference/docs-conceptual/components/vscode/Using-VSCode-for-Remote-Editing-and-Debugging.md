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
# <a name="using-visual-studio-code-for-remote-editing-and-debugging"></a><span data-ttu-id="cb299-103">Удаленные редактирование и отладка в Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="cb299-103">Using Visual Studio Code for remote editing and debugging</span></span>

<span data-ttu-id="cb299-104">Для тех, которые были знакомы с интегрированной среды Сценариев, можно вспомнить, что можно выполнить `psedit file.ps1` из интегрированной консоли, чтобы открыть файлы — локальный или удаленный - непосредственно в интегрированной среде Сценариев.</span><span class="sxs-lookup"><span data-stu-id="cb299-104">For those of you that were familiar with the ISE, you may recall that you could run `psedit file.ps1` from the integrated console to open files - local or remote - right in the ISE.</span></span>

<span data-ttu-id="cb299-105">Оказывается, эта функция также доступна в модуле PowerShell для VSCode.</span><span class="sxs-lookup"><span data-stu-id="cb299-105">As it turns out, this feature is also available in the PowerShell extension for VSCode.</span></span> <span data-ttu-id="cb299-106">В этом руководстве показано, как это сделать.</span><span class="sxs-lookup"><span data-stu-id="cb299-106">This guide will show you how to do it.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="cb299-107">Необходимые компоненты</span><span class="sxs-lookup"><span data-stu-id="cb299-107">Prerequisites</span></span>

<span data-ttu-id="cb299-108">В этом руководстве предполагается, что у вас есть:</span><span class="sxs-lookup"><span data-stu-id="cb299-108">This guide assumes that you have:</span></span>

- <span data-ttu-id="cb299-109">удаленному ресурсу (например: виртуальную Машину, контейнер), имеется доступ к</span><span class="sxs-lookup"><span data-stu-id="cb299-109">a remote resource (ex: a VM, a container) that you have access to</span></span>
- <span data-ttu-id="cb299-110">PowerShell, выполняющихся в его и хост-компьютером</span><span class="sxs-lookup"><span data-stu-id="cb299-110">PowerShell running on it and the host machine</span></span>
- <span data-ttu-id="cb299-111">VSCode и модуль PowerShell для VSCode</span><span class="sxs-lookup"><span data-stu-id="cb299-111">VSCode and the PowerShell extension for VSCode</span></span>

<span data-ttu-id="cb299-112">Эта функция работает с Windows PowerShell и PowerShell Core.</span><span class="sxs-lookup"><span data-stu-id="cb299-112">This feature works on Windows PowerShell and PowerShell Core.</span></span>

<span data-ttu-id="cb299-113">Эта функция также работает при подключении к удаленному компьютеру с помощью WinRM, PowerShell Direct или SSH.</span><span class="sxs-lookup"><span data-stu-id="cb299-113">This feature also works when connecting to a remote machine via WinRM, PowerShell Direct, or SSH.</span></span> <span data-ttu-id="cb299-114">Если вы хотите использовать SSH, но при использовании Windows, ознакомьтесь с [версии Win32 SSH](https://github.com/PowerShell/Win32-OpenSSH)!</span><span class="sxs-lookup"><span data-stu-id="cb299-114">If you want to use SSH, but are using Windows, check out the [Win32 version of SSH](https://github.com/PowerShell/Win32-OpenSSH)!</span></span>

## <a name="lets-go"></a><span data-ttu-id="cb299-115">Приступим</span><span class="sxs-lookup"><span data-stu-id="cb299-115">Let's go</span></span>

<span data-ttu-id="cb299-116">В этом разделе мы рассмотрим удаленного редактирования и отладки из моей MacBook Pro к виртуальной Машине Ubuntu, работающих в Azure.</span><span class="sxs-lookup"><span data-stu-id="cb299-116">In this section, I'll walk through remote editing and debugging from my MacBook Pro, to an Ubuntu VM running in Azure.</span></span> <span data-ttu-id="cb299-117">Я не использует Windows, но **процесс идентичен**.</span><span class="sxs-lookup"><span data-stu-id="cb299-117">I might not be using Windows, but **the process is identical**.</span></span>

### <a name="local-file-editing-with-open-editorfile"></a><span data-ttu-id="cb299-118">Локальный файл с открытым EditorFile</span><span class="sxs-lookup"><span data-stu-id="cb299-118">Local file editing with Open-EditorFile</span></span>

<span data-ttu-id="cb299-119">С помощью расширения PowerShell для работы VSCode и открыть консоль PowerShell, введя `Open-EditorFile foo.ps1` или `psedit foo.ps1` для открытия файла локального foo.ps1 прямо в редакторе.</span><span class="sxs-lookup"><span data-stu-id="cb299-119">With the PowerShell extension for VSCode started and the PowerShell Integrated Console opened, we can type `Open-EditorFile foo.ps1` or `psedit foo.ps1` to open the local foo.ps1 file right in the editor.</span></span>

![Открыть EditorFile foo.ps1 работает локально](https://user-images.githubusercontent.com/2644648/34895897-7c2c46ac-f79c-11e7-9410-a252aff52f13.png)

>[!NOTE]
> <span data-ttu-id="cb299-121">foo.ps1 должен уже существовать.</span><span class="sxs-lookup"><span data-stu-id="cb299-121">foo.ps1 must already exist.</span></span>

<span data-ttu-id="cb299-122">После этого можно:</span><span class="sxs-lookup"><span data-stu-id="cb299-122">From there, we can:</span></span>

<span data-ttu-id="cb299-123">добавить точки останова во внутренней области ![добавления точки останова для внутренней области](https://user-images.githubusercontent.com/2644648/34895893-7bdc38e2-f79c-11e7-8026-8ad53f9a1bad.png)</span><span class="sxs-lookup"><span data-stu-id="cb299-123">add breakpoints to the gutter ![adding breakpoint to gutter](https://user-images.githubusercontent.com/2644648/34895893-7bdc38e2-f79c-11e7-8026-8ad53f9a1bad.png)</span></span>

<span data-ttu-id="cb299-124">и нажмите клавишу F5 для отладки сценария PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cb299-124">and hit F5 to debug the PowerShell script.</span></span>
<span data-ttu-id="cb299-125">![Отладка локального сценария PowerShell](https://user-images.githubusercontent.com/2644648/34895894-7bedb874-f79c-11e7-9180-7e0dc2d02af8.png)</span><span class="sxs-lookup"><span data-stu-id="cb299-125">![debugging the PowerShell local script](https://user-images.githubusercontent.com/2644648/34895894-7bedb874-f79c-11e7-9180-7e0dc2d02af8.png)</span></span>

<span data-ttu-id="cb299-126">Во время отладки, можно взаимодействовать с консолью отладки, ознакомьтесь с переменные в области слева и другие стандартные средства отладки.</span><span class="sxs-lookup"><span data-stu-id="cb299-126">While debugging, you can interact with the debug console, check out the variables in the scope on the left, and all the other standard debugging tools.</span></span>

### <a name="remote-file-editing-with-open-editorfile"></a><span data-ttu-id="cb299-127">Редактирование с открытым EditorFile удаленного файла</span><span class="sxs-lookup"><span data-stu-id="cb299-127">Remote file editing with Open-EditorFile</span></span>

<span data-ttu-id="cb299-128">Теперь давайте рассмотрим удаленный файл, редактирования и отладки.</span><span class="sxs-lookup"><span data-stu-id="cb299-128">Now let's get into remote file editing and debugging.</span></span> <span data-ttu-id="cb299-129">Действия практически идентичны, есть только один момент, необходимо сначала выполнить: Введите наш сеанс PowerShell к удаленному серверу.</span><span class="sxs-lookup"><span data-stu-id="cb299-129">The steps are nearly the same, there's just one thing we need to do first - enter our PowerShell session to the remote server.</span></span>

<span data-ttu-id="cb299-130">Для этого есть командлет для.</span><span class="sxs-lookup"><span data-stu-id="cb299-130">There's a cmdlet for to do so.</span></span> <span data-ttu-id="cb299-131">Он называется `Enter-PSSession`.</span><span class="sxs-lookup"><span data-stu-id="cb299-131">It's called `Enter-PSSession`.</span></span>

<span data-ttu-id="cb299-132">Является упрощенная вниз объяснение командлета:</span><span class="sxs-lookup"><span data-stu-id="cb299-132">The watered down explanation of the cmdlet is:</span></span>

- <span data-ttu-id="cb299-133">`Enter-PSSession -ComputerName foo` запускает сеанс через WinRM</span><span class="sxs-lookup"><span data-stu-id="cb299-133">`Enter-PSSession -ComputerName foo` starts a session via WinRM</span></span>
- <span data-ttu-id="cb299-134">`Enter-PSSession -ContainerId foo` и `Enter-PSSession -VmId foo` начать сеанс с помощью PowerShell Direct</span><span class="sxs-lookup"><span data-stu-id="cb299-134">`Enter-PSSession -ContainerId foo` and `Enter-PSSession -VmId foo` start a session via PowerShell Direct</span></span>
- <span data-ttu-id="cb299-135">`Enter-PSSession -HostName foo` запускает сеанс по протоколу SSH</span><span class="sxs-lookup"><span data-stu-id="cb299-135">`Enter-PSSession -HostName foo` starts a session via SSH</span></span>

<span data-ttu-id="cb299-136">Дополнительные сведения о `Enter-PSSession`, ознакомьтесь с документацией [здесь](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/enter-pssession?view=powershell-6).</span><span class="sxs-lookup"><span data-stu-id="cb299-136">For more info on `Enter-PSSession`, check out the docs [here](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/enter-pssession?view=powershell-6).</span></span>

<span data-ttu-id="cb299-137">Я буду использовать SSH для удаленного взаимодействия, поскольку я собираюсь из macOS виртуальной Машины Ubuntu в Azure.</span><span class="sxs-lookup"><span data-stu-id="cb299-137">I'll be using SSH for remoting since I'm going from macOS to an Ubuntu VM in Azure.</span></span>

<span data-ttu-id="cb299-138">Во-первых в консоль, давайте запустим наш Enter-PSSession.</span><span class="sxs-lookup"><span data-stu-id="cb299-138">First, in the Integrated Console, let's run our Enter-PSSession.</span></span> <span data-ttu-id="cb299-139">Вы будете знать, находятся в сеанс, так как `[something]` будет отображаться слева от командном окне.</span><span class="sxs-lookup"><span data-stu-id="cb299-139">You'll know that you're in the session because `[something]` will show up to the left of your prompt.</span></span>

![Вызов Enter-PSSession](https://user-images.githubusercontent.com/2644648/34895896-7c18e0bc-f79c-11e7-9b36-6f4bd0e9b0db.png)

<span data-ttu-id="cb299-141">После этого мы можем конкретные шаги так, как если бы мы редактировали локальный сценарий.</span><span class="sxs-lookup"><span data-stu-id="cb299-141">From there, we can do the exact steps as if we were editing a local script.</span></span>

1. <span data-ttu-id="cb299-142">Запустите `Open-EditorFile test.ps1` или `psedit test.ps1` для открытия удаленного `test.ps1` файл ![открытым-EditorFile файл test.ps1](https://user-images.githubusercontent.com/2644648/34895898-7c3e6a12-f79c-11e7-8bdf-549b591ecbcb.png)</span><span class="sxs-lookup"><span data-stu-id="cb299-142">Run `Open-EditorFile test.ps1` or `psedit test.ps1` to open the remote `test.ps1` file ![Open-EditorFile the test.ps1 file](https://user-images.githubusercontent.com/2644648/34895898-7c3e6a12-f79c-11e7-8bdf-549b591ecbcb.png)</span></span>
2. <span data-ttu-id="cb299-143">Измените файл/Задание точек останова</span><span class="sxs-lookup"><span data-stu-id="cb299-143">Edit the file/set breakpoints</span></span> ![Измените и задайте точки останова](https://user-images.githubusercontent.com/2644648/34895892-7bb68246-f79c-11e7-8c0a-c2121773afbb.png)
3. <span data-ttu-id="cb299-145">Начать отладку (F5) удаленного файла</span><span class="sxs-lookup"><span data-stu-id="cb299-145">Start debugging (F5) the remote file</span></span>

![Отладка удаленного файла](https://user-images.githubusercontent.com/2644648/34895895-7c040782-f79c-11e7-93ea-47724fa5c10d.png)

<span data-ttu-id="cb299-147">Это все, вот!</span><span class="sxs-lookup"><span data-stu-id="cb299-147">That's all there's to it!</span></span> <span data-ttu-id="cb299-148">Мы надеемся, что в этом руководстве помог прояснить возникнут вопросы по удаленной отладки и редактирования PowerShell в VSCode.</span><span class="sxs-lookup"><span data-stu-id="cb299-148">We hope that this guide helped clear up any questions about remote debugging and editing PowerShell in VSCode.</span></span>

<span data-ttu-id="cb299-149">Если у вас возникли проблемы, вы можете открыть проблемы [в репозитории GitHub](http://github.com/powershell/vscode-powershell).</span><span class="sxs-lookup"><span data-stu-id="cb299-149">If you have any problems, feel free to open issues [on the GitHub repo](http://github.com/powershell/vscode-powershell).</span></span>
