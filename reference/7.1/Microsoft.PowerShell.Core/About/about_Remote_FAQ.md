---
description: Содержит вопросы и ответы о выполнении удаленных команд в PowerShell.
keywords: powershell,командлет
Locale: en-US
ms.date: 07/23/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_faq?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Remote_FAQ
ms.openlocfilehash: db3b7b554096c0cee6f13365dd8b2fbacb498282
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93232113"
---
# <a name="about-remote-faq"></a><span data-ttu-id="3d239-104">about_Remote_FAQ</span><span class="sxs-lookup"><span data-stu-id="3d239-104">About Remote FAQ</span></span>

## <a name="short-description"></a><span data-ttu-id="3d239-105">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="3d239-105">Short description</span></span>
<span data-ttu-id="3d239-106">Содержит вопросы и ответы о выполнении удаленных команд в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3d239-106">Contains questions and answers about running remote commands in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="3d239-107">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="3d239-107">Long description</span></span>

<span data-ttu-id="3d239-108">При удаленной работе вы вводите команды в PowerShell на одном компьютере (называемом "локальный компьютер"), но команды запускаются на другом компьютере (называемом "удаленным компьютером").</span><span class="sxs-lookup"><span data-stu-id="3d239-108">When you work remotely, you type commands in PowerShell on one computer (known as the "local computer"), but the commands run on another computer (known as the "remote computer").</span></span> <span data-ttu-id="3d239-109">Работа по удаленному интерфейсу должна быть настолько, насколько это возможно, непосредственно на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="3d239-109">The experience of working remotely should be as much like working directly at the remote computer as possible.</span></span>

<span data-ttu-id="3d239-110">Примечание. чтобы использовать удаленное взаимодействие PowerShell, необходимо настроить удаленный компьютер для удаленного взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="3d239-110">Note: To use PowerShell remoting, the remote computer must be configured for remoting.</span></span> <span data-ttu-id="3d239-111">Дополнительные сведения см. в разделе [about_Remote_Requirements](about_Remote_Requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3d239-111">For more information, see [about_Remote_Requirements](about_Remote_Requirements.md).</span></span>

### <a name="must-both-computers-have-powershell-installed"></a><span data-ttu-id="3d239-112">Необходимо ли установить PowerShell на обоих компьютерах?</span><span class="sxs-lookup"><span data-stu-id="3d239-112">Must both computers have PowerShell installed?</span></span>

<span data-ttu-id="3d239-113">Да.</span><span class="sxs-lookup"><span data-stu-id="3d239-113">Yes.</span></span> <span data-ttu-id="3d239-114">Для удаленной работы на локальном и удаленном компьютерах должны быть установлены PowerShell, платформа Microsoft .NET и веб-службы для управления (WS-Management).</span><span class="sxs-lookup"><span data-stu-id="3d239-114">To work remotely, the local and remote computers must have PowerShell, the Microsoft .NET Framework, and the Web Services for Management (WS-Management) protocol.</span></span> <span data-ttu-id="3d239-115">Все файлы и другие ресурсы, необходимые для выполнения определенной команды, должны находиться на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="3d239-115">Any files and other resources that are needed to execute a particular command must be on the remote computer.</span></span>

<span data-ttu-id="3d239-116">Компьютеры, на которых выполняется Windows PowerShell 3,0 и компьютеры с Windows PowerShell 2,0, могут подключаться друг к другу удаленно и выполнять удаленные команды.</span><span class="sxs-lookup"><span data-stu-id="3d239-116">Computers running Windows PowerShell 3.0 and computers running Windows PowerShell 2.0 can connect to each other remotely and run remote commands.</span></span>
<span data-ttu-id="3d239-117">Однако некоторые функции, например возможность отключения от сеанса и повторного подключения к нему, работают только в том случае, если оба компьютера работают под управлением Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="3d239-117">However, some features, such as the ability to disconnect from a session and reconnect to it, work only when both computers are running Windows PowerShell 3.0.</span></span>

<span data-ttu-id="3d239-118">Необходимо иметь разрешение на подключение к удаленному компьютеру, разрешение на запуск PowerShell и разрешение на доступ к хранилищам данных (например, файлам и папкам) и реестру на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="3d239-118">You must have permission to connect to the remote computer, permission to run PowerShell, and permission to access data stores (such as files and folders), and the registry on the remote computer.</span></span>

<span data-ttu-id="3d239-119">Дополнительные сведения см. в разделе [about_Remote_Requirements](about_Remote_Requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3d239-119">For more information, see [about_Remote_Requirements](about_Remote_Requirements.md).</span></span>

### <a name="how-does-remoting-work"></a><span data-ttu-id="3d239-120">Как работает удаленное взаимодействие?</span><span class="sxs-lookup"><span data-stu-id="3d239-120">How does remoting work?</span></span>

<span data-ttu-id="3d239-121">При отправке удаленной команды команда передается по сети модулю PowerShell на удаленном компьютере и выполняется в клиенте PowerShell на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="3d239-121">When you submit a remote command, the command is transmitted across the network to the PowerShell engine on the remote computer, and it runs in the PowerShell client on the remote computer.</span></span> <span data-ttu-id="3d239-122">Результаты команды отправляются обратно на локальный компьютер и отображаются в сеансе PowerShell на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="3d239-122">The command results are sent back to the local computer and appear in the PowerShell session on the local computer.</span></span>

<span data-ttu-id="3d239-123">Для передачи команд и получения выходных данных PowerShell использует протокол WS-Management.</span><span class="sxs-lookup"><span data-stu-id="3d239-123">To transmit the commands and receive the output, PowerShell uses the WS-Management protocol.</span></span> <span data-ttu-id="3d239-124">Дополнительные сведения о протоколе WS-Management см. в разделе [протокол WS-Management](/windows/win32/winrm/ws-management-protocol) документации по Windows.</span><span class="sxs-lookup"><span data-stu-id="3d239-124">For information about the WS-Management protocol, see [WS-Management Protocol](/windows/win32/winrm/ws-management-protocol) in the Windows documentation.</span></span>

<span data-ttu-id="3d239-125">Начиная с Windows PowerShell 3,0, удаленные сеансы хранятся на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="3d239-125">Beginning in Windows PowerShell 3.0, remote sessions are stored on the remote computer.</span></span> <span data-ttu-id="3d239-126">Это позволяет отключиться от сеанса и повторно подключиться из другого сеанса или другого компьютера без прерывания команд или потери состояния.</span><span class="sxs-lookup"><span data-stu-id="3d239-126">This enables you to disconnect from the session and reconnect from a different session or a different computer without interrupting the commands or losing state.</span></span>

### <a name="is-powershell-remoting-secure"></a><span data-ttu-id="3d239-127">Безопасна ли служба удаленного взаимодействия PowerShell?</span><span class="sxs-lookup"><span data-stu-id="3d239-127">Is PowerShell remoting secure?</span></span>

<span data-ttu-id="3d239-128">При подключении к удаленному компьютеру система использует учетные данные пользователя и пароля на локальном компьютере или учетные данные, предоставленные в команде для входа на удаленный компьютер.</span><span class="sxs-lookup"><span data-stu-id="3d239-128">When you connect to a remote computer, the system uses the username and password credentials on the local computer or the credentials that you supply in the command to log you in to the remote computer.</span></span> <span data-ttu-id="3d239-129">Учетные данные и остальная часть передачи шифруются.</span><span class="sxs-lookup"><span data-stu-id="3d239-129">The credentials and the rest of the transmission are encrypted.</span></span>

<span data-ttu-id="3d239-130">Чтобы добавить дополнительную защиту, можно настроить удаленный компьютер на использование SSL (SSL) вместо HTTP для прослушивания запросов служба удаленного управления Windows (WinRM).</span><span class="sxs-lookup"><span data-stu-id="3d239-130">To add additional protection, you can configure the remote computer to use Secure Sockets Layer (SSL) instead of HTTP to listen for Windows Remote Management (WinRM) requests.</span></span> <span data-ttu-id="3d239-131">Затем при установлении соединения пользователи **UseSSL** могут использовать параметр UseSSL `Invoke-Command` `New-PSSession` `Enter-PSSession` командлетов, и.</span><span class="sxs-lookup"><span data-stu-id="3d239-131">Then, users can use the **UseSSL** parameter of the `Invoke-Command`, `New-PSSession`, and `Enter-PSSession` cmdlets when establishing a connection.</span></span> <span data-ttu-id="3d239-132">Этот параметр использует более защищенный канал HTTPS вместо HTTP.</span><span class="sxs-lookup"><span data-stu-id="3d239-132">This option uses the more secure HTTPS channel instead of HTTP.</span></span>

### <a name="do-all-remote-commands-require-powershell-remoting"></a><span data-ttu-id="3d239-133">Требуется ли удаленное взаимодействие PowerShell для всех удаленных команд?</span><span class="sxs-lookup"><span data-stu-id="3d239-133">Do all remote commands require PowerShell remoting?</span></span>

<span data-ttu-id="3d239-134">Нет.</span><span class="sxs-lookup"><span data-stu-id="3d239-134">No.</span></span> <span data-ttu-id="3d239-135">Несколько командлетов имеют параметр **ComputerName** , позволяющий получать объекты с удаленного компьютера.</span><span class="sxs-lookup"><span data-stu-id="3d239-135">Several cmdlets have a **ComputerName** parameter that lets you get objects from the remote computer.</span></span>

<span data-ttu-id="3d239-136">Эти командлеты не используют удаленное взаимодействие PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3d239-136">These cmdlets do not use PowerShell remoting.</span></span> <span data-ttu-id="3d239-137">Поэтому их можно использовать на любом компьютере, на котором работает PowerShell, даже если компьютер не настроен для удаленного взаимодействия PowerShell или компьютер не соответствует требованиям удаленного взаимодействия PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3d239-137">So, you can use them on any computer that is running PowerShell, even if the computer is not configured for PowerShell remoting or if the computer does not meet the requirements for PowerShell remoting.</span></span>

<span data-ttu-id="3d239-138">К этим командлетам относятся следующие:</span><span class="sxs-lookup"><span data-stu-id="3d239-138">These cmdlets include the following:</span></span>

- `Get-Process`
- `Get-Service`
- `Get-WinEvent`
- `Get-EventLog`
- `Test-Connection`

<span data-ttu-id="3d239-139">Чтобы найти все командлеты с параметром **ComputerName** , введите:</span><span class="sxs-lookup"><span data-stu-id="3d239-139">To find all the cmdlets with a **ComputerName** parameter, type:</span></span>

```powershell
Get-Help * -Parameter ComputerName
# or
Get-Command -ParameterName ComputerName
```

<span data-ttu-id="3d239-140">Чтобы определить, требуется ли для параметра **ComputerName** конкретного командлета удаленное взаимодействие PowerShell, см. Описание параметра.</span><span class="sxs-lookup"><span data-stu-id="3d239-140">To determine whether the **ComputerName** parameter of a particular cmdlet requires PowerShell remoting, see the parameter description.</span></span> <span data-ttu-id="3d239-141">Чтобы отобразить описание параметра, введите:</span><span class="sxs-lookup"><span data-stu-id="3d239-141">To display the parameter description, type:</span></span>

```powershell
Get-Help <cmdlet-name> -Parameter ComputerName
```

<span data-ttu-id="3d239-142">Пример:</span><span class="sxs-lookup"><span data-stu-id="3d239-142">For example:</span></span>

```powershell
Get-Help Get-Process -Parameter ComputerName
```

<span data-ttu-id="3d239-143">Для всех остальных команд используйте `Invoke-Command` командлет.</span><span class="sxs-lookup"><span data-stu-id="3d239-143">For all other commands, use the `Invoke-Command` cmdlet.</span></span>

### <a name="how-do-i-run-a-command-on-a-remote-computer"></a><span data-ttu-id="3d239-144">Разделы справки выполнить команду на удаленном компьютере?</span><span class="sxs-lookup"><span data-stu-id="3d239-144">How do I run a command on a remote computer?</span></span>

<span data-ttu-id="3d239-145">Чтобы выполнить команду на удаленном компьютере, используйте `Invoke-Command` командлет.</span><span class="sxs-lookup"><span data-stu-id="3d239-145">To run a command on a remote computer, use the `Invoke-Command` cmdlet.</span></span>

<span data-ttu-id="3d239-146">Заключите команду в фигурные скобки ( `{}` ), чтобы сделать ее блоком сценария.</span><span class="sxs-lookup"><span data-stu-id="3d239-146">Enclose your command in braces (`{}`) to make it a script block.</span></span> <span data-ttu-id="3d239-147">Используйте параметр **ScriptBlock** аргумента `Invoke-Command` для указания команды.</span><span class="sxs-lookup"><span data-stu-id="3d239-147">Use the **ScriptBlock** parameter of `Invoke-Command` to specify the command.</span></span>

<span data-ttu-id="3d239-148">Параметр **ComputerName** параметра можно использовать `Invoke-Command` для указания удаленного компьютера.</span><span class="sxs-lookup"><span data-stu-id="3d239-148">You can use the **ComputerName** parameter of `Invoke-Command` to specify a remote computer.</span></span> <span data-ttu-id="3d239-149">Или можно создать постоянное подключение к удаленному компьютеру (сеанс), а затем использовать параметр **Session** из `Invoke-Command` для выполнения команды в сеансе.</span><span class="sxs-lookup"><span data-stu-id="3d239-149">Or, you can create a persistent connection to a remote computer (a session) and then use the **Session** parameter of `Invoke-Command` to run the command in the session.</span></span>

<span data-ttu-id="3d239-150">Например, следующие команды выполняют `Get-Process` команду удаленно.</span><span class="sxs-lookup"><span data-stu-id="3d239-150">For example, the following commands run a `Get-Process` command remotely.</span></span>

```powershell
Invoke-Command -ComputerName Server01, Server02 -ScriptBlock {Get-Process}

#  - OR -

Invoke-Command -Session $s -ScriptBlock {Get-Process}
```

<span data-ttu-id="3d239-151">Чтобы прервать удаленную команду, введите <kbd>CTRL</kbd> + <kbd>C</kbd>.</span><span class="sxs-lookup"><span data-stu-id="3d239-151">To interrupt a remote command, type <kbd>CTRL</kbd>+<kbd>C</kbd>.</span></span> <span data-ttu-id="3d239-152">Запрос на прерывание передается на удаленный компьютер, где он завершает удаленную команду.</span><span class="sxs-lookup"><span data-stu-id="3d239-152">The interruption request is passed to the remote computer, where it terminates the remote command.</span></span>

<span data-ttu-id="3d239-153">Дополнительные сведения об удаленных командах см. в разделе about_Remote и разделы справки по командлетам, поддерживающим удаленное взаимодействие.</span><span class="sxs-lookup"><span data-stu-id="3d239-153">For more information about remote commands, see about_Remote and the Help topics for the cmdlets that support remoting.</span></span>

### <a name="can-i-just-telnet-into-a-remote-computer"></a><span data-ttu-id="3d239-154">Могу ли я только Telnet на удаленном компьютере?</span><span class="sxs-lookup"><span data-stu-id="3d239-154">Can I just telnet into a remote computer?</span></span>

<span data-ttu-id="3d239-155">`Enter-PSSession`С помощью командлета можно запустить интерактивный сеанс с удаленным компьютером.</span><span class="sxs-lookup"><span data-stu-id="3d239-155">You can use the `Enter-PSSession` cmdlet to start an interactive session with a remote computer.</span></span>

<span data-ttu-id="3d239-156">В командной строке PowerShell введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="3d239-156">At the PowerShell prompt, type:</span></span>

```powershell
Enter-PSSession <ComputerName>
```

<span data-ttu-id="3d239-157">Командная строка изменится, чтобы отображалось подключение к удаленному компьютеру.</span><span class="sxs-lookup"><span data-stu-id="3d239-157">The command prompt changes to show that you are connected to the remote computer.</span></span>

```
<ComputerName>\C:>
```

<span data-ttu-id="3d239-158">Теперь команды, которые вы вводите, выполняются на удаленном компьютере так же, как и при их вводе непосредственно на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="3d239-158">Now, the commands that you type run on the remote computer just as though you typed them directly on the remote computer.</span></span>

<span data-ttu-id="3d239-159">Чтобы завершить интерактивный сеанс, введите:</span><span class="sxs-lookup"><span data-stu-id="3d239-159">To end the interactive session, type:</span></span>

```powershell
Exit-PSSession
```

<span data-ttu-id="3d239-160">Интерактивный сеанс — это постоянный сеанс, использующий протокол WS-Management.</span><span class="sxs-lookup"><span data-stu-id="3d239-160">An interactive session is a persistent session that uses the WS-Management protocol.</span></span> <span data-ttu-id="3d239-161">Это не то же самое, что и Telnet, но обеспечивает аналогичную работу.</span><span class="sxs-lookup"><span data-stu-id="3d239-161">It is not the same as using Telnet, but it provides a similar experience.</span></span>

<span data-ttu-id="3d239-162">Для получения дополнительной информации см. `Enter-PSSession`.</span><span class="sxs-lookup"><span data-stu-id="3d239-162">For more information, see `Enter-PSSession`.</span></span>

### <a name="can-i-create-a-persistent-connection"></a><span data-ttu-id="3d239-163">Можно ли создать постоянное подключение?</span><span class="sxs-lookup"><span data-stu-id="3d239-163">Can I create a persistent connection?</span></span>

<span data-ttu-id="3d239-164">Да.</span><span class="sxs-lookup"><span data-stu-id="3d239-164">Yes.</span></span> <span data-ttu-id="3d239-165">Для выполнения удаленных команд можно указать имя удаленного компьютера, имя NetBIOS или его IP-адрес.</span><span class="sxs-lookup"><span data-stu-id="3d239-165">You can run remote commands by specifying the name of the remote computer, its NetBIOS name, or its IP address.</span></span> <span data-ttu-id="3d239-166">Также можно выполнить удаленные команды, указав сеанс PowerShell (PSSession), подключенный к удаленному компьютеру.</span><span class="sxs-lookup"><span data-stu-id="3d239-166">Or, you can run remote commands by specifying a PowerShell session (PSSession) that is connected to the remote computer.</span></span>

<span data-ttu-id="3d239-167">При использовании параметра **ComputerName** в `Invoke-Command` или `Enter-PSSession` PowerShell устанавливает временное подключение.</span><span class="sxs-lookup"><span data-stu-id="3d239-167">When you use the **ComputerName** parameter of `Invoke-Command` or `Enter-PSSession`, PowerShell establishes a temporary connection.</span></span> <span data-ttu-id="3d239-168">PowerShell использует соединение для выполнения только текущей команды, а затем закрывает соединение.</span><span class="sxs-lookup"><span data-stu-id="3d239-168">PowerShell uses the connection to run only the current command, and then it closes the connection.</span></span> <span data-ttu-id="3d239-169">Это очень эффективный метод выполнения одной команды или нескольких несвязанных команд, даже на многих удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="3d239-169">This is a very efficient method for running a single command or several unrelated commands, even on many remote computers.</span></span>

<span data-ttu-id="3d239-170">При использовании `New-PSSession` командлета для создания сеанса PSSession PowerShell устанавливает постоянное подключение к сеансу PSSession.</span><span class="sxs-lookup"><span data-stu-id="3d239-170">When you use the `New-PSSession` cmdlet to create a PSSession, PowerShell establishes a persistent connection for the PSSession.</span></span> <span data-ttu-id="3d239-171">Затем можно выполнить несколько команд в сеансе PSSession, включая команды, которые совместно используют данные.</span><span class="sxs-lookup"><span data-stu-id="3d239-171">Then, you can run multiple commands in the PSSession, including commands that share data.</span></span>

<span data-ttu-id="3d239-172">Как правило, сеанс PSSession создается для выполнения ряда связанных команд, которые совместно используют данные.</span><span class="sxs-lookup"><span data-stu-id="3d239-172">Typically, you create a PSSession to run a series of related commands that share data.</span></span> <span data-ttu-id="3d239-173">В противном случае для большинства команд достаточно временное соединение, созданное параметром **ComputerName** .</span><span class="sxs-lookup"><span data-stu-id="3d239-173">Otherwise, the temporary connection created by the **ComputerName** parameter is sufficient for most commands.</span></span>

<span data-ttu-id="3d239-174">Дополнительные сведения о сеансах см. в разделе about_PSSessions.</span><span class="sxs-lookup"><span data-stu-id="3d239-174">For more information about sessions, see about_PSSessions.</span></span>

### <a name="can-i-run-commands-on-more-than-one-computer-at-a-time"></a><span data-ttu-id="3d239-175">Можно ли выполнять команды более чем на одном компьютере за раз?</span><span class="sxs-lookup"><span data-stu-id="3d239-175">Can I run commands on more than one computer at a time?</span></span>

<span data-ttu-id="3d239-176">Да.</span><span class="sxs-lookup"><span data-stu-id="3d239-176">Yes.</span></span> <span data-ttu-id="3d239-177">Параметр **ComputerName** `Invoke-Command` командлета принимает несколько имен компьютеров, а параметр **Session** принимает несколько PSSession.</span><span class="sxs-lookup"><span data-stu-id="3d239-177">The **ComputerName** parameter of the `Invoke-Command` cmdlet accepts multiple computer names, and the **Session** parameter accepts multiple PSSessions.</span></span>

<span data-ttu-id="3d239-178">При выполнении `Invoke-Command` команды PowerShell выполняет команды на всех указанных компьютерах или во всех указанных PSSession.</span><span class="sxs-lookup"><span data-stu-id="3d239-178">When you run an `Invoke-Command` command, PowerShell runs the commands on all of the specified computers or in all of the specified PSSessions.</span></span>

<span data-ttu-id="3d239-179">PowerShell может управлять сотнями одновременных удаленных подключений.</span><span class="sxs-lookup"><span data-stu-id="3d239-179">PowerShell can manage hundreds of concurrent remote connections.</span></span> <span data-ttu-id="3d239-180">Однако количество удаленных команд, которые можно отправить, может быть ограничено ресурсами компьютера и его емкостью для установки и обслуживания нескольких сетевых подключений.</span><span class="sxs-lookup"><span data-stu-id="3d239-180">However, the number of remote commands that you can send might be limited by the resources of your computer and its capacity to establish and maintain multiple network connections.</span></span>

<span data-ttu-id="3d239-181">Дополнительные сведения см. в примере в `Invoke-Command` разделе справки.</span><span class="sxs-lookup"><span data-stu-id="3d239-181">For more information, see the example in the `Invoke-Command` Help topic.</span></span>

### <a name="where-are-my-profiles"></a><span data-ttu-id="3d239-182">Где находятся мои профили?</span><span class="sxs-lookup"><span data-stu-id="3d239-182">Where are my profiles?</span></span>

<span data-ttu-id="3d239-183">Профили PowerShell не запускаются автоматически в удаленных сеансах, поэтому команды, добавляемые в профиль, отсутствуют в сеансе.</span><span class="sxs-lookup"><span data-stu-id="3d239-183">PowerShell profiles are not run automatically in remote sessions, so the commands that the profile adds are not present in the session.</span></span> <span data-ttu-id="3d239-184">Кроме того, `$profile` Автоматическая переменная не заполняется в удаленных сеансах.</span><span class="sxs-lookup"><span data-stu-id="3d239-184">In addition, the `$profile` automatic variable is not populated in remote sessions.</span></span>

<span data-ttu-id="3d239-185">Чтобы запустить профиль в сеансе, используйте `Invoke-Command` командлет.</span><span class="sxs-lookup"><span data-stu-id="3d239-185">To run a profile in a session, use the `Invoke-Command` cmdlet.</span></span>

<span data-ttu-id="3d239-186">Например, следующая команда запускает профиль CurrentUserCurrentHost с локального компьютера в сеансе `$s` .</span><span class="sxs-lookup"><span data-stu-id="3d239-186">For example, the following command runs the CurrentUserCurrentHost profile from the local computer in the session in `$s`.</span></span>

```
Invoke-Command -Session $s -FilePath $profile
```

<span data-ttu-id="3d239-187">Следующая команда запускает профиль CurrentUserCurrentHost с удаленного компьютера в сеансе в `$s` .</span><span class="sxs-lookup"><span data-stu-id="3d239-187">The following command runs the CurrentUserCurrentHost profile from the remote computer in the session in `$s`.</span></span> <span data-ttu-id="3d239-188">Так как `$profile` переменная не заполнена, команда использует явный путь к профилю.</span><span class="sxs-lookup"><span data-stu-id="3d239-188">Because the `$profile` variable is not populated, the command uses the explicit path to the profile.</span></span>

```powershell
Invoke-Command -Session $s {
  . "$home\Documents\WindowsPowerShell\Microsoft.PowerShell_profile.ps1"
}
```

<span data-ttu-id="3d239-189">После выполнения этой команды команды, которые профиль добавляет в сеанс, будут доступны в `$s` .</span><span class="sxs-lookup"><span data-stu-id="3d239-189">After running this command, the commands that the profile adds to the session are available in `$s`.</span></span>

<span data-ttu-id="3d239-190">Сценарий запуска можно также использовать в конфигурации сеанса для запуска профиля в каждом удаленном сеансе, использующем конфигурацию сеанса.</span><span class="sxs-lookup"><span data-stu-id="3d239-190">You can also use a startup script in a session configuration to run a profile in every remote session that uses the session configuration.</span></span>

<span data-ttu-id="3d239-191">Дополнительные сведения о профилях PowerShell см. в разделе about_Profiles.</span><span class="sxs-lookup"><span data-stu-id="3d239-191">For more information about PowerShell profiles, see about_Profiles.</span></span>
<span data-ttu-id="3d239-192">Дополнительные сведения о конфигурациях сеансов см. в разделе `Register-PSSessionConfiguration` .</span><span class="sxs-lookup"><span data-stu-id="3d239-192">For more information about session configurations, see `Register-PSSessionConfiguration`.</span></span>

### <a name="how-does-throttling-work-on-remote-commands"></a><span data-ttu-id="3d239-193">Как работает регулирование для удаленных команд?</span><span class="sxs-lookup"><span data-stu-id="3d239-193">How does throttling work on remote commands?</span></span>

<span data-ttu-id="3d239-194">Чтобы упростить управление ресурсами на локальном компьютере, в PowerShell имеется функция регулирования для отдельных команд, которая позволяет ограничить количество одновременных удаленных подключений, установленных для каждой команды.</span><span class="sxs-lookup"><span data-stu-id="3d239-194">To help you manage the resources on your local computer, PowerShell includes a per-command throttling feature that lets you limit the number of concurrent remote connections that are established for each command.</span></span>

<span data-ttu-id="3d239-195">Значение по умолчанию — 32 одновременных подключений, но можно использовать параметр **ThrottleLimit** командлетов, чтобы установить настраиваемое ограничение регулирования для определенных команд.</span><span class="sxs-lookup"><span data-stu-id="3d239-195">The default is 32 concurrent connections, but you can use the **ThrottleLimit** parameter of the cmdlets to set a custom throttle limit for particular commands.</span></span>

<span data-ttu-id="3d239-196">При использовании функции регулирования Помните, что она применяется к каждой команде, а не ко всему сеансу или к компьютеру.</span><span class="sxs-lookup"><span data-stu-id="3d239-196">When you use the throttling feature, remember that it is applied to each command, not to the entire session or to the computer.</span></span> <span data-ttu-id="3d239-197">При одновременном выполнении команд в нескольких сеансах или PSSession число одновременных подключений равно сумме одновременных подключений во всех сеансах.</span><span class="sxs-lookup"><span data-stu-id="3d239-197">If you are running commands concurrently in several sessions or PSSessions, the number of concurrent connections is the sum of the concurrent connections in all the sessions.</span></span>

<span data-ttu-id="3d239-198">Чтобы найти командлеты с параметром **ThrottleLimit** , введите:</span><span class="sxs-lookup"><span data-stu-id="3d239-198">To find cmdlets with a **ThrottleLimit** parameter, type:</span></span>

```
Get-Help * -Parameter ThrottleLimit
-or-
Get-Command -ParameterName ThrottleLimit
```

### <a name="is-the-output-of-remote-commands-different-from-local-output"></a><span data-ttu-id="3d239-199">Отличаются ли выходные данные удаленных команд от локального вывода?</span><span class="sxs-lookup"><span data-stu-id="3d239-199">Is the output of remote commands different from local output?</span></span>

<span data-ttu-id="3d239-200">При использовании PowerShell в локальной среде вы отправляете и получаете "динамические" .NET Framework объекты; "динамические" объекты — это объекты, связанные с фактическими программами или системными компонентами.</span><span class="sxs-lookup"><span data-stu-id="3d239-200">When you use PowerShell locally, you send and receive "live" .NET Framework objects; "live" objects are objects that are associated with actual programs or system components.</span></span> <span data-ttu-id="3d239-201">При вызове методов или изменении свойств активных объектов изменения влияют на фактическую программу или компонент.</span><span class="sxs-lookup"><span data-stu-id="3d239-201">When you invoke the methods or change the properties of live objects, the changes affect the actual program or component.</span></span> <span data-ttu-id="3d239-202">А при изменении свойств программы или компонента свойства объекта, которые их представляют, также изменяются.</span><span class="sxs-lookup"><span data-stu-id="3d239-202">And, when the properties of a program or component change, the properties of the object that represent them also change.</span></span>

<span data-ttu-id="3d239-203">Однако поскольку большинство активных объектов не могут передаваться по сети, PowerShell «сериализует» большинство объектов, отправленных в удаленных командах, то есть преобразует каждый объект в ряд элементов данных XML (язык ограничений в XML [CLiXML]) для передачи.</span><span class="sxs-lookup"><span data-stu-id="3d239-203">However, because most live objects cannot be transmitted over the network, PowerShell "serializes" most of the objects sent in remote commands, that is, it converts each object into a series of XML (Constraint Language in XML [CLiXML]) data elements for transmission.</span></span>

<span data-ttu-id="3d239-204">Когда PowerShell получает сериализованный объект, он преобразует XML в тип десериализованного объекта.</span><span class="sxs-lookup"><span data-stu-id="3d239-204">When PowerShell receives a serialized object, it converts the XML into a deserialized object type.</span></span> <span data-ttu-id="3d239-205">Десериализованный объект — это точная запись свойств программы или компонента в предыдущий раз, но она больше не является "динамической", то есть больше не связана напрямую с компонентом.</span><span class="sxs-lookup"><span data-stu-id="3d239-205">The deserialized object is an accurate record of the properties of the program or component at a previous time, but it is no longer "live", that is, it is no longer directly associated with the component.</span></span> <span data-ttu-id="3d239-206">Методы удаляются, так как они больше не действуют.</span><span class="sxs-lookup"><span data-stu-id="3d239-206">And, the methods are removed because they are no longer effective.</span></span>

<span data-ttu-id="3d239-207">Как правило, десериализуемые объекты можно использовать так же, как и активные объекты, но следует иметь в виду их ограничения.</span><span class="sxs-lookup"><span data-stu-id="3d239-207">Typically, you can use deserialized objects just as you would use live objects, but you must be aware of their limitations.</span></span> <span data-ttu-id="3d239-208">Кроме того, объекты, возвращаемые `Invoke-Command` командлетом, имеют дополнительные свойства, помогающие определить происхождение команды.</span><span class="sxs-lookup"><span data-stu-id="3d239-208">Also, the objects that are returned by the `Invoke-Command` cmdlet have additional properties that help you to determine the origin of the command.</span></span>

<span data-ttu-id="3d239-209">Некоторые типы объектов, например объекты DirectoryInfo и GUID, преобразуются обратно в динамические объекты при их получении.</span><span class="sxs-lookup"><span data-stu-id="3d239-209">Some object types, such as DirectoryInfo objects and GUIDs, are converted back into live objects when they are received.</span></span> <span data-ttu-id="3d239-210">Для этих объектов не требуется специальная обработка или форматирование.</span><span class="sxs-lookup"><span data-stu-id="3d239-210">These objects do not need any special handling or formatting.</span></span>

<span data-ttu-id="3d239-211">Дополнительные сведения об интерпретации и форматировании удаленных выходных данных см. в разделе [about_Remote_Output](about_Remote_Output.md).</span><span class="sxs-lookup"><span data-stu-id="3d239-211">For information about interpreting and formatting remote output, see [about_Remote_Output](about_Remote_Output.md).</span></span>

### <a name="can-i-run-background-jobs-remotely"></a><span data-ttu-id="3d239-212">Можно ли выполнять фоновые задания удаленно?</span><span class="sxs-lookup"><span data-stu-id="3d239-212">Can I run background jobs remotely?</span></span>

<span data-ttu-id="3d239-213">Да.</span><span class="sxs-lookup"><span data-stu-id="3d239-213">Yes.</span></span> <span data-ttu-id="3d239-214">Фоновое задание PowerShell — это команда PowerShell, которая выполняется асинхронно без взаимодействия с сеансом.</span><span class="sxs-lookup"><span data-stu-id="3d239-214">A PowerShell background job is a PowerShell command that runs asynchronously without interacting with the session.</span></span> <span data-ttu-id="3d239-215">При запуске фонового задания командная строка возвращается немедленно, и вы можете продолжать работу в сеансе, пока задание выполняется, даже если оно выполняется в течение продолжительного периода времени.</span><span class="sxs-lookup"><span data-stu-id="3d239-215">When you start a background job, the command prompt returns immediately, and you can continue to work in the session while the job runs even if it runs for an extended period of time.</span></span>

<span data-ttu-id="3d239-216">Фоновое задание можно запустить даже во время выполнения других команд, так как фоновые задания всегда выполняются асинхронно во временном сеансе.</span><span class="sxs-lookup"><span data-stu-id="3d239-216">You can start a background job even while other commands are running because background jobs always run asynchronously in a temporary session.</span></span>

<span data-ttu-id="3d239-217">Фоновые задания можно выполнять на локальном или удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="3d239-217">You can run background jobs on a local or remote computer.</span></span> <span data-ttu-id="3d239-218">По умолчанию фоновое задание выполняется на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="3d239-218">By default, a background job runs on the local computer.</span></span> <span data-ttu-id="3d239-219">Однако можно использовать параметр **AsJob** `Invoke-Command` командлета для выполнения любой удаленной команды в качестве фонового задания.</span><span class="sxs-lookup"><span data-stu-id="3d239-219">However, you can use the **AsJob** parameter of the `Invoke-Command` cmdlet to run any remote command as a background job.</span></span> <span data-ttu-id="3d239-220">И можно использовать `Invoke-Command` для `Start-Job` удаленного выполнения команды.</span><span class="sxs-lookup"><span data-stu-id="3d239-220">And, you can use `Invoke-Command` to run a `Start-Job` command remotely.</span></span>

<span data-ttu-id="3d239-221">Дополнительные сведения о фоновых заданиях в PowerShell см. в разделе [about_Jobs (about_Jobs. md)] и [about_Remote_Jobs (about_Remote_Jobs. md)].</span><span class="sxs-lookup"><span data-stu-id="3d239-221">For more information about background jobs in PowerShell , see [about_Jobs(about_Jobs.md)] and [about_Remote_Jobs(about_Remote_Jobs.md)].</span></span>

### <a name="can-i-run-windows-programs-on-a-remote-computer"></a><span data-ttu-id="3d239-222">Можно ли запускать программы Windows на удаленном компьютере?</span><span class="sxs-lookup"><span data-stu-id="3d239-222">Can I run windows programs on a remote computer?</span></span>

<span data-ttu-id="3d239-223">Для запуска программ на основе Windows на удаленных компьютерах можно использовать удаленные команды PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3d239-223">You can use PowerShell remote commands to run Windows-based programs on remote computers.</span></span> <span data-ttu-id="3d239-224">Например, можно запустить `Shutdown.exe` или `Ipconfig.exe` на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="3d239-224">For example, you can run `Shutdown.exe` or `Ipconfig.exe` on a remote computer.</span></span>

<span data-ttu-id="3d239-225">Однако нельзя использовать команды PowerShell для открытия пользовательского интерфейса для любой программы на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="3d239-225">However, you cannot use PowerShell commands to open the user interface for any program on a remote computer.</span></span>

<span data-ttu-id="3d239-226">При запуске программы Windows на удаленном компьютере команда не завершается, и Командная строка PowerShell не возвращается, пока программа не будет завершена или пока не будет нажата клавиша <kbd>CTRL</kbd> + <kbd>C</kbd> для прерывания команды.</span><span class="sxs-lookup"><span data-stu-id="3d239-226">When you start a Windows program on a remote computer, the command is not completed, and the PowerShell command prompt does not return, until the program is finished or until you press <kbd>CTRL</kbd>+<kbd>C</kbd> to interrupt the command.</span></span> <span data-ttu-id="3d239-227">Например, если запустить `Ipconfig.exe` программу на удаленном компьютере, Командная строка не вернется, пока не `Ipconfig.exe` завершится.</span><span class="sxs-lookup"><span data-stu-id="3d239-227">For example, if you run the `Ipconfig.exe` program on a remote computer, the command prompt does not return until `Ipconfig.exe` is completed.</span></span>

<span data-ttu-id="3d239-228">При использовании удаленных команд для запуска программы с пользовательским интерфейсом запускается процесс, но пользовательский интерфейс не отображается.</span><span class="sxs-lookup"><span data-stu-id="3d239-228">If you use remote commands to start a program that has a user interface, the program process starts, but the user interface does not appear.</span></span> <span data-ttu-id="3d239-229">Команда PowerShell не завершена, и Командная строка не будет возвращаться до тех пор, пока не будет остановлен процесс программы или пока не нажата клавиша <kbd>CTRL</kbd> + <kbd>C</kbd>, которая прерывает выполнение команды и останавливает процесс.</span><span class="sxs-lookup"><span data-stu-id="3d239-229">The PowerShell command is not completed, and the command prompt does not return until you stop the program process or until you press <kbd>CTRL</kbd>+<kbd>C</kbd>, which interrupts the command and stops the process.</span></span>

<span data-ttu-id="3d239-230">Например, если для запуска `Notepad` на удаленном компьютере используется команда PowerShell, процесс «Блокнот» запускается на удаленном компьютере, но пользовательский интерфейс блокнота не отображается.</span><span class="sxs-lookup"><span data-stu-id="3d239-230">For example, if you use a PowerShell command to run `Notepad` on a remote computer, the Notepad process starts on the remote computer, but the Notepad user interface does not appear.</span></span> <span data-ttu-id="3d239-231">Чтобы прервать выполнение команды и восстановить командную строку, нажмите клавиши <kbd>CTRL</kbd> + <kbd>C</kbd>.</span><span class="sxs-lookup"><span data-stu-id="3d239-231">To interrupt the command and restore the command prompt, press <kbd>CTRL</kbd>+<kbd>C</kbd>.</span></span>

### <a name="can-i-limit-the-commands-that-users-can-run-remotely-on-my-computer"></a><span data-ttu-id="3d239-232">Можно ли ограничить команды, которые пользователи могут запускать удаленно на моем компьютере?</span><span class="sxs-lookup"><span data-stu-id="3d239-232">Can I limit the commands that users can run remotely on my computer?</span></span>

<span data-ttu-id="3d239-233">Да.</span><span class="sxs-lookup"><span data-stu-id="3d239-233">Yes.</span></span> <span data-ttu-id="3d239-234">Каждый удаленный сеанс должен использовать одну из конфигураций сеанса на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="3d239-234">Every remote session must use one of the session configurations on the remote computer.</span></span> <span data-ttu-id="3d239-235">Вы можете управлять конфигурациями сеансов на компьютере (и разрешениями для этих конфигураций сеанса), чтобы определить, кто может выполнять команды удаленно на компьютере и какие команды они могут выполняться.</span><span class="sxs-lookup"><span data-stu-id="3d239-235">You can manage the session configurations on your computer (and the permissions to those session configurations) to determine who can run commands remotely on your computer and which commands they can run.</span></span>

<span data-ttu-id="3d239-236">Конфигурация сеанса настраивает среду для сеанса.</span><span class="sxs-lookup"><span data-stu-id="3d239-236">A session configuration configures the environment for the session.</span></span> <span data-ttu-id="3d239-237">Конфигурацию можно определить с помощью сборки, реализующей новый класс конфигурации, или с помощью скрипта, выполняемого в сеансе.</span><span class="sxs-lookup"><span data-stu-id="3d239-237">You can define the configuration by using an assembly that implements a new configuration class or by using a script that runs in the session.</span></span> <span data-ttu-id="3d239-238">Конфигурация может определять команды, доступные в сеансе.</span><span class="sxs-lookup"><span data-stu-id="3d239-238">The configuration can determine the commands that are available in the session.</span></span>
<span data-ttu-id="3d239-239">Кроме того, конфигурация может включать параметры, защищающие компьютер, такие как параметры, ограничивающие объем данных, которые сеанс может получить удаленно, в одном объекте или команде.</span><span class="sxs-lookup"><span data-stu-id="3d239-239">And, the configuration can include settings that protect the computer, such as settings that limit the amount of data that the session can receive remotely in a single object or command.</span></span> <span data-ttu-id="3d239-240">Можно также указать дескриптор безопасности, который определяет разрешения, необходимые для использования конфигурации.</span><span class="sxs-lookup"><span data-stu-id="3d239-240">You can also specify a security descriptor that determines the permissions that are required to use the configuration.</span></span>

<span data-ttu-id="3d239-241">`Enable-PSRemoting`Командлет создает конфигурации сеансов по умолчанию на компьютере: Microsoft. PowerShell, Microsoft. PowerShell. Workflow и Microsoft. PowerShell32 (только 64-разрядные операционные системы).</span><span class="sxs-lookup"><span data-stu-id="3d239-241">The `Enable-PSRemoting` cmdlet creates the default session configurations on your computer: Microsoft.PowerShell, Microsoft.PowerShell.Workflow, and Microsoft.PowerShell32 (64-bit operating systems only).</span></span> <span data-ttu-id="3d239-242">`Enable-PSRemoting` Задает дескриптор безопасности для конфигурации, чтобы разрешить использовать их только членам группы "Администраторы" на компьютере.</span><span class="sxs-lookup"><span data-stu-id="3d239-242">`Enable-PSRemoting` sets the security descriptor for the configuration to allow only members of the Administrators group on your computer to use them.</span></span>

<span data-ttu-id="3d239-243">Командлеты конфигурации сеанса можно использовать для изменения конфигураций сеансов по умолчанию, создания новых конфигураций сеансов и изменения дескрипторов безопасности всех конфигураций сеансов.</span><span class="sxs-lookup"><span data-stu-id="3d239-243">You can use the session configuration cmdlets to edit the default session configurations, to create new session configurations, and to change the security descriptors of all the session configurations.</span></span>

<span data-ttu-id="3d239-244">Начиная с Windows PowerShell 3,0, `New-PSSessionConfigurationFile` командлет позволяет создавать пользовательские конфигурации сеансов с помощью текстового файла.</span><span class="sxs-lookup"><span data-stu-id="3d239-244">Beginning in Windows PowerShell 3.0, the `New-PSSessionConfigurationFile` cmdlet lets you create custom session configurations by using a text file.</span></span> <span data-ttu-id="3d239-245">Файл содержит параметры для настройки языкового режима и для указания командлетов и модулей, доступных в сеансах, использующих конфигурацию сеанса.</span><span class="sxs-lookup"><span data-stu-id="3d239-245">The file includes options for setting the language mode and for specifying the cmdlets and modules that are available in sessions that use the session configuration.</span></span>

<span data-ttu-id="3d239-246">Когда пользователи используют `Invoke-Command` `New-PSSession` командлеты,, или `Enter-PSSession` , они могут использовать параметр **configurationName** для указания конфигурации сеанса, используемой для сеанса.</span><span class="sxs-lookup"><span data-stu-id="3d239-246">When users use the `Invoke-Command`, `New-PSSession`, or `Enter-PSSession` cmdlets, they can use the **ConfigurationName** parameter to indicate the session configuration that is used for the session.</span></span> <span data-ttu-id="3d239-247">Кроме того, они могут изменить конфигурацию по умолчанию, которую используют сеансы, изменив значение `$PSSessionConfigurationName` переменной предпочтений в сеансе.</span><span class="sxs-lookup"><span data-stu-id="3d239-247">And, they can change the default configuration that their sessions use by changing the value of the `$PSSessionConfigurationName` preference variable in the session.</span></span>

<span data-ttu-id="3d239-248">Дополнительные сведения о конфигурациях сеансов см. в справке по командлетам конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="3d239-248">For more information about session configurations, see the Help for the session configuration cmdlets.</span></span> <span data-ttu-id="3d239-249">Чтобы найти командлеты конфигурации сеанса, введите:</span><span class="sxs-lookup"><span data-stu-id="3d239-249">To find the session configuration cmdlets, type:</span></span>

```powershell
Get-Command *PSSessionConfiguration
```

### <a name="what-are-fan-in-and-fan-out-configurations"></a><span data-ttu-id="3d239-250">Что такое конфигурации вентиляторов и наружных вентиляторов?</span><span class="sxs-lookup"><span data-stu-id="3d239-250">What are fan in and fan out configurations?</span></span>

<span data-ttu-id="3d239-251">Наиболее распространенным сценарием удаленного взаимодействия PowerShell, включающим несколько компьютеров, является конфигурация "один ко многим", в которой один локальный компьютер (компьютер администратора) выполняет команды PowerShell на многочисленных удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="3d239-251">The most common PowerShell remoting scenario involving multiple computers is the one-to-many configuration, in which one local computer (the administrator's computer) runs PowerShell commands on numerous remote computers.</span></span> <span data-ttu-id="3d239-252">Этот сценарий называется "выходом из".</span><span class="sxs-lookup"><span data-stu-id="3d239-252">This is known as the "fan-out" scenario.</span></span>

<span data-ttu-id="3d239-253">Однако на некоторых предприятиях конфигурация имеет значение «многие к одному», где многие клиентские компьютеры подключаются к одному удаленному компьютеру, работающему под управлением PowerShell, например файловый сервер или киоск.</span><span class="sxs-lookup"><span data-stu-id="3d239-253">However, in some enterprises, the configuration is many-to-one, where many client computers connect to a single remote computer that is running PowerShell, such as a file server or a kiosk.</span></span> <span data-ttu-id="3d239-254">Это называется конфигурацией с вентилятором.</span><span class="sxs-lookup"><span data-stu-id="3d239-254">This is known as the "fan-in" configuration.</span></span>

<span data-ttu-id="3d239-255">Удаленное взаимодействие PowerShell поддерживает конфигурации как развертывания, так и вентилятора.</span><span class="sxs-lookup"><span data-stu-id="3d239-255">PowerShell remoting supports both fan-out and fan-in configurations.</span></span>

<span data-ttu-id="3d239-256">Для конфигурации с выходом из развертывания PowerShell использует протокол веб-служб для управления (WS-Management) и службу WinRM, поддерживающую реализацию WS-Management Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="3d239-256">For the fan-out configuration, PowerShell uses the Web Services for Management (WS-Management) protocol and the WinRM service that supports the Microsoft implementation of WS-Management.</span></span> <span data-ttu-id="3d239-257">При подключении локального компьютера к удаленному компьютеру WS-Management устанавливает подключение и использует подключаемый модуль для PowerShell, чтобы запустить хост-процесс PowerShell (Wsmprovhost.exe) на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="3d239-257">When a local computer connects to a remote computer, WS-Management establishes a connection and uses a plug-in for PowerShell to start the PowerShell host process (Wsmprovhost.exe) on the remote computer.</span></span> <span data-ttu-id="3d239-258">Пользователь может указать альтернативный порт, конфигурацию дополнительного сеанса и другие функции для настройки удаленного подключения.</span><span class="sxs-lookup"><span data-stu-id="3d239-258">The user can specify an alternate port, an alternate session configuration, and other features to customize the remote connection.</span></span>

<span data-ttu-id="3d239-259">Для поддержки конфигурации "с вентиляторами" в PowerShell используются службы IIS для размещения WS-Management, загрузки подключаемого модуля PowerShell и запуска PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3d239-259">To support the "fan-in" configuration, PowerShell uses internet Information Services (IIS) to host WS-Management, to load the PowerShell plug-in, and to start PowerShell.</span></span> <span data-ttu-id="3d239-260">В этом сценарии вместо того, чтобы запускать каждый сеанс PowerShell в отдельном процессе, все сеансы PowerShell выполняются в одном и том же хост-процессе.</span><span class="sxs-lookup"><span data-stu-id="3d239-260">In this scenario, instead of starting each PowerShell session in a separate process, all PowerShell sessions run in the same host process.</span></span>

<span data-ttu-id="3d239-261">Размещение и удаленное управление в IIS не поддерживается в Windows XP и Windows Server 2003.</span><span class="sxs-lookup"><span data-stu-id="3d239-261">IIS hosting and fan-in remote management is not supported in Windows XP or in Windows Server 2003.</span></span>

<span data-ttu-id="3d239-262">В конфигурации с вентилятором пользователь может указать универсальный код ресурса (URI) подключения и конечную точку HTTP, включая транспорт, имя компьютера, порт и имя приложения.</span><span class="sxs-lookup"><span data-stu-id="3d239-262">In a fan-in configuration, the user can specify a connection URI and an HTTP endpoint, including the transport, computer name, port, and application name.</span></span>
<span data-ttu-id="3d239-263">Службы IIS пересылают в приложение все запросы с указанным именем приложения.</span><span class="sxs-lookup"><span data-stu-id="3d239-263">IIS forwards all the requests with a specified application name to the application.</span></span> <span data-ttu-id="3d239-264">Значение по умолчанию — WS-Management, в котором может размещаться PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3d239-264">The default is WS-Management, which can host PowerShell.</span></span>

<span data-ttu-id="3d239-265">Можно также указать механизм проверки подлинности и запретить или разрешить перенаправление из конечных точек HTTP и HTTPS.</span><span class="sxs-lookup"><span data-stu-id="3d239-265">You can also specify an authentication mechanism and prohibit or allow redirection from HTTP and HTTPS endpoints.</span></span>

### <a name="can-i-test-remoting-on-a-single-computer-not-in-a-domain"></a><span data-ttu-id="3d239-266">Можно ли протестировать удаленное взаимодействие на одном компьютере, а не в домене?</span><span class="sxs-lookup"><span data-stu-id="3d239-266">Can I test remoting on a single computer not in a domain?</span></span>

<span data-ttu-id="3d239-267">Да.</span><span class="sxs-lookup"><span data-stu-id="3d239-267">Yes.</span></span> <span data-ttu-id="3d239-268">Удаленное взаимодействие PowerShell доступно даже в том случае, если локальный компьютер не входит в домен.</span><span class="sxs-lookup"><span data-stu-id="3d239-268">PowerShell remoting is available even when the local computer is not in a domain.</span></span> <span data-ttu-id="3d239-269">Функции удаленного взаимодействия можно использовать для подключения к сеансам и создания сеансов на одном компьютере.</span><span class="sxs-lookup"><span data-stu-id="3d239-269">You can use the remoting features to connect to sessions and to create sessions on the same computer.</span></span> <span data-ttu-id="3d239-270">Функции работают так же, как и при подключении к удаленному компьютеру.</span><span class="sxs-lookup"><span data-stu-id="3d239-270">The features work the same as they do when you connect to a remote computer.</span></span>

<span data-ttu-id="3d239-271">Для выполнения удаленных команд на компьютере в Рабочей группе Измените следующие параметры Windows на компьютере.</span><span class="sxs-lookup"><span data-stu-id="3d239-271">To run remote commands on a computer in a workgroup, change the following Windows settings on the computer.</span></span>

<span data-ttu-id="3d239-272">Внимание! эти параметры влияют на всех пользователей системы и могут сделать систему более уязвимой для атак злоумышленников.</span><span class="sxs-lookup"><span data-stu-id="3d239-272">Caution: These settings affect all users on the system and they can make the system more vulnerable to a malicious attack.</span></span> <span data-ttu-id="3d239-273">Будьте внимательны при внесении этих изменений.</span><span class="sxs-lookup"><span data-stu-id="3d239-273">Use caution when making these changes.</span></span>

- <span data-ttu-id="3d239-274">Windows Vista, Windows 7, Windows 8:</span><span class="sxs-lookup"><span data-stu-id="3d239-274">Windows Vista, Windows 7, Windows 8:</span></span>

  <span data-ttu-id="3d239-275">Создайте следующую запись реестра и присвойте ей значение 1: LocalAccountTokenFilterPolicy в ` HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System`</span><span class="sxs-lookup"><span data-stu-id="3d239-275">Create the following registry entry, and then set its value to 1: LocalAccountTokenFilterPolicy in ` HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System`</span></span>

  <span data-ttu-id="3d239-276">Для добавления этой записи можно использовать следующую команду PowerShell:</span><span class="sxs-lookup"><span data-stu-id="3d239-276">You can use the following PowerShell command to add this entry:</span></span>

    ```powershell
    $parameters = @{
      Path='HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System'
      Name='LocalAccountTokenFilterPolicy'
      propertyType='DWord'
      Value=1
    }
    New-ItemProperty @parameters
    ```

- <span data-ttu-id="3d239-277">Windows Server 2003, Windows Server 2008, Windows Server 2012, Windows Server 2012 R2:</span><span class="sxs-lookup"><span data-stu-id="3d239-277">Windows Server 2003, Windows Server 2008, Windows Server 2012, Windows Server 2012 R2:</span></span>

  <span data-ttu-id="3d239-278">Изменения не требуются, так как параметр по умолчанию политики "сетевой доступ: модель общего доступа и безопасность для локальных учетных записей" имеет значение "Классическая".</span><span class="sxs-lookup"><span data-stu-id="3d239-278">No changes are needed because the default setting of the "Network Access: Sharing and security model for local accounts" policy is "Classic".</span></span> <span data-ttu-id="3d239-279">Проверьте значение параметра, если оно изменилось.</span><span class="sxs-lookup"><span data-stu-id="3d239-279">Verify the setting in case it has changed.</span></span>

### <a name="can-i-run-remote-commands-on-a-computer-in-another-domain"></a><span data-ttu-id="3d239-280">Можно ли выполнять удаленные команды на компьютере в другом домене?</span><span class="sxs-lookup"><span data-stu-id="3d239-280">Can I run remote commands on a computer in another domain?</span></span>

<span data-ttu-id="3d239-281">Да.</span><span class="sxs-lookup"><span data-stu-id="3d239-281">Yes.</span></span> <span data-ttu-id="3d239-282">Как правило, команды выполняются без ошибок, хотя может потребоваться использовать параметр **Credential** `Invoke-Command` `New-PSSession` командлета, или, `Enter-PSSession` чтобы предоставить учетные данные члена группы администраторов на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="3d239-282">Typically, the commands run without error, although you might need to use the **Credential** parameter of the `Invoke-Command`, `New-PSSession`, or `Enter-PSSession` cmdlets to provide the credentials of a member of the Administrators group on the remote computer.</span></span> <span data-ttu-id="3d239-283">Это иногда требуется, даже если текущий пользователь является членом группы "Администраторы" на локальном и удаленном компьютерах.</span><span class="sxs-lookup"><span data-stu-id="3d239-283">This is sometimes required even when the current user is a member of the Administrators group on the local and remote computers.</span></span>

<span data-ttu-id="3d239-284">Однако если удаленный компьютер не входит в домен, которому доверяет локальный компьютер, удаленный компьютер не сможет проверить подлинность учетных данных пользователя.</span><span class="sxs-lookup"><span data-stu-id="3d239-284">However, if the remote computer is not in a domain that the local computer trusts, the remote computer might not be able to authenticate the user's credentials.</span></span>

<span data-ttu-id="3d239-285">Чтобы включить проверку подлинности, используйте следующую команду, чтобы добавить удаленный компьютер в список доверенных узлов для локального компьютера в WinRM.</span><span class="sxs-lookup"><span data-stu-id="3d239-285">To enable authentication, use the following command to add the remote computer to the list of trusted hosts for the local computer in WinRM.</span></span> <span data-ttu-id="3d239-286">Введите команду в командной строке PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3d239-286">Type the command at the PowerShell prompt.</span></span>

```powershell
Set-Item WSMan:\localhost\Client\TrustedHosts -Value <Remote-computer-name>
```

<span data-ttu-id="3d239-287">Например, чтобы добавить компьютер Server01 в список доверенных узлов на локальном компьютере, введите следующую команду в командной строке PowerShell:</span><span class="sxs-lookup"><span data-stu-id="3d239-287">For example, to add the Server01 computer to the list of trusted hosts on the local computer, type the following command at the PowerShell prompt:</span></span>

```powershell
Set-Item WSMan:\localhost\Client\TrustedHosts -Value Server01
```

### <a name="does-powershell-support-remoting-over-ssh"></a><span data-ttu-id="3d239-288">Поддерживает ли PowerShell удаленное взаимодействие через SSH?</span><span class="sxs-lookup"><span data-stu-id="3d239-288">Does PowerShell support remoting over SSH?</span></span>

<span data-ttu-id="3d239-289">Да.</span><span class="sxs-lookup"><span data-stu-id="3d239-289">Yes.</span></span> <span data-ttu-id="3d239-290">Дополнительные сведения см. в статье [удаленное взаимодействие PowerShell через SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).</span><span class="sxs-lookup"><span data-stu-id="3d239-290">For more information, see [PowerShell remoting over SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).</span></span>

## <a name="see-also"></a><span data-ttu-id="3d239-291">См. также статью</span><span class="sxs-lookup"><span data-stu-id="3d239-291">See also</span></span>

[<span data-ttu-id="3d239-292">about_Remote</span><span class="sxs-lookup"><span data-stu-id="3d239-292">about_Remote</span></span>](about_Remote.md)

[<span data-ttu-id="3d239-293">about_Profiles</span><span class="sxs-lookup"><span data-stu-id="3d239-293">about_Profiles</span></span>](about_Profiles.md)

[<span data-ttu-id="3d239-294">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="3d239-294">about_PSSessions</span></span>](about_PSSessions.md)

[<span data-ttu-id="3d239-295">about_Remote_Jobs</span><span class="sxs-lookup"><span data-stu-id="3d239-295">about_Remote_Jobs</span></span>](about_Remote_Jobs.md)

[<span data-ttu-id="3d239-296">about_Remote_Variables</span><span class="sxs-lookup"><span data-stu-id="3d239-296">about_Remote_Variables</span></span>](about_Remote_Variables.md)

[<span data-ttu-id="3d239-297">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="3d239-297">Invoke-Command</span></span>](xref:Microsoft.PowerShell.Core.Invoke-Command)

[<span data-ttu-id="3d239-298">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="3d239-298">New-PSSession</span></span>](xref:Microsoft.PowerShell.Core.New-PSSession)
