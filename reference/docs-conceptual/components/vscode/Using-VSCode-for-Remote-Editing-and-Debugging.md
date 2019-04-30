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
# <a name="using-visual-studio-code-for-remote-editing-and-debugging"></a><span data-ttu-id="03878-103">Удаленные редактирование и отладка в Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="03878-103">Using Visual Studio Code for remote editing and debugging</span></span>

<span data-ttu-id="03878-104">Каждый пользователь, знакомый с ISE, может вспомнить, как запускать `psedit file.ps1` из встроенной консоли, чтобы открыть локальные или удаленные файлы прямо в интегрированной среде сценариев.</span><span class="sxs-lookup"><span data-stu-id="03878-104">For those of you that were familiar with the ISE, you may recall that you could run `psedit file.ps1` from the integrated console to open files - local or remote - right in the ISE.</span></span>

<span data-ttu-id="03878-105">Оказывается, эта функция также доступна в расширении PowerShell для VSCode.</span><span class="sxs-lookup"><span data-stu-id="03878-105">As it turns out, this feature is also available in the PowerShell extension for VSCode.</span></span> <span data-ttu-id="03878-106">В этом руководстве показано, как это сделать.</span><span class="sxs-lookup"><span data-stu-id="03878-106">This guide will show you how to do it.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="03878-107">Необходимые компоненты</span><span class="sxs-lookup"><span data-stu-id="03878-107">Prerequisites</span></span>

<span data-ttu-id="03878-108">В этом руководстве предполагается, что у вас есть:</span><span class="sxs-lookup"><span data-stu-id="03878-108">This guide assumes that you have:</span></span>

- <span data-ttu-id="03878-109">удаленный ресурс (например, виртуальная машина, контейнер), к которому у вас есть доступ;</span><span class="sxs-lookup"><span data-stu-id="03878-109">a remote resource (ex: a VM, a container) that you have access to</span></span>
- <span data-ttu-id="03878-110">PowerShell, работающий на нем и на основном компьютере;</span><span class="sxs-lookup"><span data-stu-id="03878-110">PowerShell running on it and the host machine</span></span>
- <span data-ttu-id="03878-111">VSCode и расширение PowerShell для VSCode.</span><span class="sxs-lookup"><span data-stu-id="03878-111">VSCode and the PowerShell extension for VSCode</span></span>

<span data-ttu-id="03878-112">Эта возможность работает с Windows PowerShell и PowerShell Core.</span><span class="sxs-lookup"><span data-stu-id="03878-112">This feature works on Windows PowerShell and PowerShell Core.</span></span>

<span data-ttu-id="03878-113">Эта возможность также работает при подключении к удаленному компьютеру с помощью WinRM, PowerShell Direct или SSH.</span><span class="sxs-lookup"><span data-stu-id="03878-113">This feature also works when connecting to a remote machine via WinRM, PowerShell Direct, or SSH.</span></span> <span data-ttu-id="03878-114">Если вы хотите использовать SSH, но используете Windows, ознакомьтесь с [версией SSH Win32](https://github.com/PowerShell/Win32-OpenSSH).</span><span class="sxs-lookup"><span data-stu-id="03878-114">If you want to use SSH, but are using Windows, check out the [Win32 version of SSH](https://github.com/PowerShell/Win32-OpenSSH)!</span></span>

## <a name="lets-go"></a><span data-ttu-id="03878-115">Приступим</span><span class="sxs-lookup"><span data-stu-id="03878-115">Let's go</span></span>

<span data-ttu-id="03878-116">В этом разделе мы рассмотрим удаленное редактирование и отладку виртуальной машины Ubuntu, которая запущена в Azure, с MacBook Pro.</span><span class="sxs-lookup"><span data-stu-id="03878-116">In this section, I'll walk through remote editing and debugging from my MacBook Pro, to an Ubuntu VM running in Azure.</span></span> <span data-ttu-id="03878-117">Если Windows не используется, то **процесс идентичен**.</span><span class="sxs-lookup"><span data-stu-id="03878-117">I might not be using Windows, but **the process is identical**.</span></span>

### <a name="local-file-editing-with-open-editorfile"></a><span data-ttu-id="03878-118">Редактирование локального файла с помощью открытого редактора файлов</span><span class="sxs-lookup"><span data-stu-id="03878-118">Local file editing with Open-EditorFile</span></span>

<span data-ttu-id="03878-119">С помощью расширения PowerShell для VSCode и открытой интегрированной консоли PowerShell напечатайте `Open-EditorFile foo.ps1` или `psedit foo.ps1`, чтобы открыть локальный файл foo.ps1 прямо в редакторе.</span><span class="sxs-lookup"><span data-stu-id="03878-119">With the PowerShell extension for VSCode started and the PowerShell Integrated Console opened, we can type `Open-EditorFile foo.ps1` or `psedit foo.ps1` to open the local foo.ps1 file right in the editor.</span></span>

![Файл foo.ps1 в открытом редакторе файлов работает локально](https://user-images.githubusercontent.com/2644648/34895897-7c2c46ac-f79c-11e7-9410-a252aff52f13.png)

>[!NOTE]
> <span data-ttu-id="03878-121">foo.ps1 должен уже существовать.</span><span class="sxs-lookup"><span data-stu-id="03878-121">foo.ps1 must already exist.</span></span>

<span data-ttu-id="03878-122">После этого вы можете сделать следующее.</span><span class="sxs-lookup"><span data-stu-id="03878-122">From there, we can:</span></span>

<span data-ttu-id="03878-123">Добавить точки останова во внутреннее поле. ![Добавление точек останова во внутреннее поле](https://user-images.githubusercontent.com/2644648/34895893-7bdc38e2-f79c-11e7-8026-8ad53f9a1bad.png)</span><span class="sxs-lookup"><span data-stu-id="03878-123">add breakpoints to the gutter ![adding breakpoint to gutter](https://user-images.githubusercontent.com/2644648/34895893-7bdc38e2-f79c-11e7-8026-8ad53f9a1bad.png)</span></span>

<span data-ttu-id="03878-124">Нажать клавишу F5 для отладки сценария PowerShell.</span><span class="sxs-lookup"><span data-stu-id="03878-124">and hit F5 to debug the PowerShell script.</span></span>
<span data-ttu-id="03878-125">![Отладка локального сценария PowerShell](https://user-images.githubusercontent.com/2644648/34895894-7bedb874-f79c-11e7-9180-7e0dc2d02af8.png)</span><span class="sxs-lookup"><span data-stu-id="03878-125">![debugging the PowerShell local script](https://user-images.githubusercontent.com/2644648/34895894-7bedb874-f79c-11e7-9180-7e0dc2d02af8.png)</span></span>

<span data-ttu-id="03878-126">Во время отладки можно взаимодействовать с консолью отладки, ознакомиться с переменными в левой области и другими стандартными средствами отладки.</span><span class="sxs-lookup"><span data-stu-id="03878-126">While debugging, you can interact with the debug console, check out the variables in the scope on the left, and all the other standard debugging tools.</span></span>

### <a name="remote-file-editing-with-open-editorfile"></a><span data-ttu-id="03878-127">Редактирование удаленного файла с помощью открытого редактора файлов</span><span class="sxs-lookup"><span data-stu-id="03878-127">Remote file editing with Open-EditorFile</span></span>

<span data-ttu-id="03878-128">Теперь давайте приступим к редактированию и отладке удаленного файла.</span><span class="sxs-lookup"><span data-stu-id="03878-128">Now let's get into remote file editing and debugging.</span></span> <span data-ttu-id="03878-129">Шаги практически одинаковы, но в первую очередь нам нужно начать сеанс PowerShell на удаленном сервере.</span><span class="sxs-lookup"><span data-stu-id="03878-129">The steps are nearly the same, there's just one thing we need to do first - enter our PowerShell session to the remote server.</span></span>

<span data-ttu-id="03878-130">Для этого существует командлет.</span><span class="sxs-lookup"><span data-stu-id="03878-130">There's a cmdlet for to do so.</span></span> <span data-ttu-id="03878-131">Он называется `Enter-PSSession`.</span><span class="sxs-lookup"><span data-stu-id="03878-131">It's called `Enter-PSSession`.</span></span>

<span data-ttu-id="03878-132">Проще говоря, командлет действует так:</span><span class="sxs-lookup"><span data-stu-id="03878-132">The watered down explanation of the cmdlet is:</span></span>

- <span data-ttu-id="03878-133">`Enter-PSSession -ComputerName foo` запускает сеанс через WinRM;</span><span class="sxs-lookup"><span data-stu-id="03878-133">`Enter-PSSession -ComputerName foo` starts a session via WinRM</span></span>
- <span data-ttu-id="03878-134">`Enter-PSSession -ContainerId foo` и `Enter-PSSession -VmId foo` начинают сеанс с помощью PowerShell Direct;</span><span class="sxs-lookup"><span data-stu-id="03878-134">`Enter-PSSession -ContainerId foo` and `Enter-PSSession -VmId foo` start a session via PowerShell Direct</span></span>
- <span data-ttu-id="03878-135">`Enter-PSSession -HostName foo` запускает сеанс через SSH.</span><span class="sxs-lookup"><span data-stu-id="03878-135">`Enter-PSSession -HostName foo` starts a session via SSH</span></span>

<span data-ttu-id="03878-136">Чтобы получить дополнительные сведения о `Enter-PSSession`, ознакомьтесь с документацией [здесь](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/enter-pssession?view=powershell-6).</span><span class="sxs-lookup"><span data-stu-id="03878-136">For more info on `Enter-PSSession`, check out the docs [here](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/enter-pssession?view=powershell-6).</span></span>

<span data-ttu-id="03878-137">Для удаленного взаимодействия используется SSH, поскольку мы будем работать с macOS в виртуальной машине Ubuntu в Azure.</span><span class="sxs-lookup"><span data-stu-id="03878-137">I'll be using SSH for remoting since I'm going from macOS to an Ubuntu VM in Azure.</span></span>

<span data-ttu-id="03878-138">Во-первых, давайте запустим в интегрированной консоли Enter-PSSession.</span><span class="sxs-lookup"><span data-stu-id="03878-138">First, in the Integrated Console, let's run our Enter-PSSession.</span></span> <span data-ttu-id="03878-139">Вы узнаете, что начали сеанс, когда слева от командной строки появится `[something]`.</span><span class="sxs-lookup"><span data-stu-id="03878-139">You'll know that you're in the session because `[something]` will show up to the left of your prompt.</span></span>

![Вызов Enter-PSSession](https://user-images.githubusercontent.com/2644648/34895896-7c18e0bc-f79c-11e7-9b36-6f4bd0e9b0db.png)

<span data-ttu-id="03878-141">После этого мы можем выполнить те же шаги, что и при редактировании локального сценария.</span><span class="sxs-lookup"><span data-stu-id="03878-141">From there, we can do the exact steps as if we were editing a local script.</span></span>

1. <span data-ttu-id="03878-142">Запустите `Open-EditorFile test.ps1` или `psedit test.ps1`, чтобы открыть удаленный файл `test.ps1`. ![Файл test.ps1 в открытом редакторе файлов](https://user-images.githubusercontent.com/2644648/34895898-7c3e6a12-f79c-11e7-8bdf-549b591ecbcb.png)</span><span class="sxs-lookup"><span data-stu-id="03878-142">Run `Open-EditorFile test.ps1` or `psedit test.ps1` to open the remote `test.ps1` file ![Open-EditorFile the test.ps1 file](https://user-images.githubusercontent.com/2644648/34895898-7c3e6a12-f79c-11e7-8bdf-549b591ecbcb.png)</span></span>
2. <span data-ttu-id="03878-143">Отредактируйте файл, установите точки останова.</span><span class="sxs-lookup"><span data-stu-id="03878-143">Edit the file/set breakpoints</span></span> ![Редактирование и установка точек останова](https://user-images.githubusercontent.com/2644648/34895892-7bb68246-f79c-11e7-8c0a-c2121773afbb.png)
3. <span data-ttu-id="03878-145">Начните отладку (F5) удаленного файла.</span><span class="sxs-lookup"><span data-stu-id="03878-145">Start debugging (F5) the remote file</span></span>

![Отладка удаленного файла](https://user-images.githubusercontent.com/2644648/34895895-7c040782-f79c-11e7-93ea-47724fa5c10d.png)

<span data-ttu-id="03878-147">Вот и все!</span><span class="sxs-lookup"><span data-stu-id="03878-147">That's all there's to it!</span></span> <span data-ttu-id="03878-148">Мы надеемся, что это руководство помогло прояснить возникшие вопросы по удаленной отладке и редактированию PowerShell в VSCode.</span><span class="sxs-lookup"><span data-stu-id="03878-148">We hope that this guide helped clear up any questions about remote debugging and editing PowerShell in VSCode.</span></span>

<span data-ttu-id="03878-149">Если у вас возникли проблемы, вы можете писать вопросы [в репозитории GitHub](http://github.com/powershell/vscode-powershell).</span><span class="sxs-lookup"><span data-stu-id="03878-149">If you have any problems, feel free to open issues [on the GitHub repo](http://github.com/powershell/vscode-powershell).</span></span>
