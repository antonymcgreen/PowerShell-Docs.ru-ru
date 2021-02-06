---
description: Объясняет, как отключиться и повторно подключиться к сеансу PowerShell (PSSession).
Locale: en-US
ms.date: 12/01/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_disconnected_sessions?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Remote_Disconnected_Sessions
ms.openlocfilehash: 0756e110b1058915f6280e2ea59ee915bedb2c75
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599372"
---
# <a name="about-remote-disconnected-sessions"></a><span data-ttu-id="3b2a5-103">Об удаленных отключенных сеансах</span><span class="sxs-lookup"><span data-stu-id="3b2a5-103">About Remote Disconnected Sessions</span></span>

## <a name="short-description"></a><span data-ttu-id="3b2a5-104">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="3b2a5-104">Short description</span></span>

<span data-ttu-id="3b2a5-105">Объясняет, как отключиться и повторно подключиться к сеансу PowerShell (PSSession).</span><span class="sxs-lookup"><span data-stu-id="3b2a5-105">Explains how to disconnect and reconnect to a PowerShell Session (PSSession).</span></span>

## <a name="long-description"></a><span data-ttu-id="3b2a5-106">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="3b2a5-106">Long description</span></span>

<span data-ttu-id="3b2a5-107">Начиная с PowerShell 3,0 можно отключиться от PSSession и повторно подключиться к сеансу PSSession на том же или другом компьютере.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-107">Beginning in PowerShell 3.0, you can disconnect from a PSSession and reconnect to the PSSession on the same computer or a different computer.</span></span> <span data-ttu-id="3b2a5-108">Состояние сеанса сохраняется, а команды в PSSession продолжают выполняться, пока сеанс отключен.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-108">The session state is maintained and commands in the PSSession continue to run while the session is disconnected.</span></span>

<span data-ttu-id="3b2a5-109">Функция отключенных сеансов доступна только в том случае, если на удаленном компьютере работает PowerShell 3,0 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-109">The Disconnected Sessions feature is only available when the remote computer is running PowerShell 3.0 or a later version.</span></span>

<span data-ttu-id="3b2a5-110">Функция отключенных сеансов позволяет закрыть сеанс, в котором был создан сеанс PSSession, и даже закрыть PowerShell и завершить работу компьютера без прерывания выполнения команд в сеансе PSSession.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-110">The Disconnected Sessions feature allows you to close the session in which a PSSession was created, and even close PowerShell, and shut down the computer, without disrupting commands running in the PSSession.</span></span> <span data-ttu-id="3b2a5-111">Отключенные сеансы полезны для выполнения команд, которые занимают длительное время и предоставляют ИТ-специалистам необходимое время и гибкость устройств.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-111">Disconnected sessions are useful for running commands that take an extended time to complete, and provides the time and device flexibility that IT professionals require.</span></span>

<span data-ttu-id="3b2a5-112">Невозможно отключиться от интерактивного сеанса, запущенного с помощью `Enter-PSSession` командлета.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-112">You can't disconnect from an interactive session that is started by using the `Enter-PSSession` cmdlet.</span></span>

<span data-ttu-id="3b2a5-113">Можно использовать отключенные сеансы для управления PSSession, которые были отключены непреднамеренно в результате сбоя компьютера или сети.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-113">You can use disconnected sessions to manage PSSessions that were disconnected unintentionally as the result of a computer or network outage.</span></span>

<span data-ttu-id="3b2a5-114">В реальном использовании функция отключенных сеансов позволяет приступить к решению проблемы, подать особое внимание на проблему с более высоким приоритетом, а затем возобновить работу решения даже на другом компьютере в другом расположении.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-114">In real-world use, the Disconnected Sessions feature allows you to begin solving a problem, turn your attention to a higher priority issue, and then resume work on the solution, even on a different computer in a different location.</span></span>

## <a name="disconnected-session-cmdlets"></a><span data-ttu-id="3b2a5-115">Командлеты отключенных сеансов</span><span class="sxs-lookup"><span data-stu-id="3b2a5-115">Disconnected session cmdlets</span></span>

<span data-ttu-id="3b2a5-116">Следующие командлеты поддерживают функцию отключенных сеансов:</span><span class="sxs-lookup"><span data-stu-id="3b2a5-116">The following cmdlets support the Disconnected Sessions feature:</span></span>

- <span data-ttu-id="3b2a5-117">`Connect-PSSession`: Подключается к отключенному сеансу PSSession.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-117">`Connect-PSSession`: Connects to a disconnected PSSession.</span></span>
- <span data-ttu-id="3b2a5-118">`Disconnect-PSSession`: Отключает сеанс PSSession.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-118">`Disconnect-PSSession`: Disconnects a PSSession.</span></span>
- <span data-ttu-id="3b2a5-119">`Get-PSSession`: Получает PSSession на локальном компьютере или на удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-119">`Get-PSSession`: Gets PSSessions on the local computer or on remote computers.</span></span>
- <span data-ttu-id="3b2a5-120">`Receive-PSSession`: Возвращает результаты команд, которые выполнялись в отключенных сеансах.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-120">`Receive-PSSession`: Gets the results of commands that ran in disconnected sessions.</span></span>
- <span data-ttu-id="3b2a5-121">`Invoke-Command`: Параметр **InDisconnectedSession** создает сеанс PSSession и немедленно отключается.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-121">`Invoke-Command`: **InDisconnectedSession** parameter creates a PSSession and disconnects immediately.</span></span>

## <a name="how-the-disconnected-sessions-feature-works"></a><span data-ttu-id="3b2a5-122">Как работает функция отключенных сеансов</span><span class="sxs-lookup"><span data-stu-id="3b2a5-122">How the Disconnected Sessions feature works</span></span>

<span data-ttu-id="3b2a5-123">Начиная с PowerShell 3,0, PSSession не зависят от сеансов, в которых они созданы.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-123">Beginning in PowerShell 3.0, PSSessions are independent of the sessions in which they're created.</span></span> <span data-ttu-id="3b2a5-124">Активные PSSession хранятся на удаленном компьютере или на **стороне сервера** соединения, даже если сеанс, в котором был создан PSSession, закрыт, а исходный компьютер выключен или отключен от сети.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-124">Active PSSessions are maintained on the remote computer or **server-side** of the connection, even if the session in which the PSSession was created is closed and the originating computer is shut down or disconnected from the network.</span></span>

<span data-ttu-id="3b2a5-125">В PowerShell 2,0 сеанс PSSession удаляется с удаленного компьютера, когда он отключается от исходного сеанса или после завершения сеанса, в котором он был создан.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-125">In PowerShell 2.0, the PSSession is deleted from the remote computer when it's disconnected from the originating session or the session in which it was created ends.</span></span>

<span data-ttu-id="3b2a5-126">При отключении сеанса PSSession сеанс PSSession остается активным и сохраняется на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-126">When you disconnect a PSSession, the PSSession remains active and is maintained on the remote computer.</span></span> <span data-ttu-id="3b2a5-127">Состояние сеанса меняется с " **работает** " на " **отключено**".</span><span class="sxs-lookup"><span data-stu-id="3b2a5-127">The session state changes from **Running** to **Disconnected**.</span></span> <span data-ttu-id="3b2a5-128">Можно повторно подключиться к отключенному сеансу PSSession из текущего сеанса или из другого сеанса на том же компьютере или на другом компьютере.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-128">You can reconnect to a disconnected PSSession from the current session or from a different session on the same computer, or from a different computer.</span></span> <span data-ttu-id="3b2a5-129">Удаленный компьютер, поддерживающий сеанс, должен быть установлен и подключен к сети.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-129">The remote computer that maintains the session must be running and be connected to the network.</span></span>

<span data-ttu-id="3b2a5-130">Команды в отключенном сеансе PSSession продолжают выполняться на удаленном компьютере до завершения выполнения команды или заполнения буфера вывода.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-130">Commands in a disconnected PSSession continue to run uninterrupted on the remote computer until the command completes or the output buffer fills.</span></span> <span data-ttu-id="3b2a5-131">Чтобы предотвратить приостановку выполнения команды в полном буфере вывода, используйте параметр **аутпутбуфферингмоде** `Disconnect-PSSession` `New-PSSessionOption` `New-PSTransportOption` командлетов, или.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-131">To prevent a full output buffer from suspending a command, use the **OutputBufferingMode** parameter of the `Disconnect-PSSession`, `New-PSSessionOption`, or `New-PSTransportOption` cmdlets.</span></span>

<span data-ttu-id="3b2a5-132">Отключенные сеансы хранятся в отключенном состоянии на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-132">Disconnected sessions are maintained in the disconnected state on the remote computer.</span></span> <span data-ttu-id="3b2a5-133">Они доступны для повторного подключения до тех пор, пока не будет удален сеанс PSSession, например с помощью `Remove-PSSession` командлета или до истечения времени ожидания сеанса PSSession.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-133">They're available for you to reconnect, until you delete the PSSession, such as by using the `Remove-PSSession` cmdlet, or until the idle timeout of the PSSession expires.</span></span> <span data-ttu-id="3b2a5-134">Можно настроить время ожидания простоя сеанса PSSession с помощью параметров **идлетимеаутсек** или **IdleTimeout** `Disconnect-PSSession` `New-PSSessionOption` `New-PSTransportOption` командлетов, или.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-134">You can adjust the idle timeout of a PSSession by using the **IdleTimeoutSec** or **IdleTimeout** parameters of the `Disconnect-PSSession`, `New-PSSessionOption`, or `New-PSTransportOption` cmdlets.</span></span>

<span data-ttu-id="3b2a5-135">Другой пользователь может подключиться к PSSession, который вы создали, но только в том случае, если они смогут предоставить учетные данные, которые использовались для создания сеанса, или использовать `RunAs` учетные данные конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-135">Another user can connect to PSSessions that you created, but only if they can provide the credentials that were used to create the session, or use the `RunAs` credentials of the session configuration.</span></span>

## <a name="how-to-get-pssessions"></a><span data-ttu-id="3b2a5-136">Как получить PSSession</span><span class="sxs-lookup"><span data-stu-id="3b2a5-136">How to get PSSessions</span></span>

<span data-ttu-id="3b2a5-137">Начиная с PowerShell 3,0 `Get-PSSession` командлет получает PSSession на локальном компьютере и на удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-137">Beginning in PowerShell 3.0, the `Get-PSSession` cmdlet gets PSSessions on the local computer and remote computers.</span></span> <span data-ttu-id="3b2a5-138">Он также может получить PSSession, созданные в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-138">It can also get PSSessions that were created in the current session.</span></span>

<span data-ttu-id="3b2a5-139">Чтобы получить PSSession на локальном компьютере или на удаленных компьютерах, используйте параметры **ComputerName** или **ConnectionURI** .</span><span class="sxs-lookup"><span data-stu-id="3b2a5-139">To get PSSessions on the local computer or remote computers, use the **ComputerName** or **ConnectionUri** parameters.</span></span> <span data-ttu-id="3b2a5-140">Без параметров `Get-PSSession` получает значение PSSession, созданное в локальном сеансе, независимо от того, где они завершаются.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-140">Without parameters, `Get-PSSession` gets PSSession that were created in the local session, regardless of where they terminate.</span></span>

<span data-ttu-id="3b2a5-141">При получении PSSession не забудьте найти их на компьютере, где они поддерживаются, то есть на удаленном или **серверном** компьютере.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-141">When getting PSSessions, remember to look for them on the computer on which they're maintained, that is, the remote or **server-side** computer.</span></span>

<span data-ttu-id="3b2a5-142">Например, если вы создадите сеанс PSSession на компьютере Server01, получите его с компьютера Server01.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-142">For example, if you create a PSSession to the Server01 computer, get the session from the Server01 computer.</span></span> <span data-ttu-id="3b2a5-143">При создании сеанса PSSession с другого компьютера на локальный компьютер получает сеанс с локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-143">If you create a PSSession from another computer to the local computer, get the session from the local computer.</span></span>

<span data-ttu-id="3b2a5-144">В следующей последовательности команд показано, как `Get-PSSession` работает.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-144">The following command sequence shows how `Get-PSSession` works.</span></span>

<span data-ttu-id="3b2a5-145">Первая команда создает сеанс на компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-145">The first command creates a session to the Server01 computer.</span></span> <span data-ttu-id="3b2a5-146">Сеанс находится на компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-146">The session resides on the Server01 computer.</span></span>

```powershell
New-PSSession -ComputerName Server01
```

```Output
Id Name      ComputerName  State    ConfigurationName     Availability
-- ----      ------------  -----    -----------------     ------------
 2 Session2  Server01      Opened   Microsoft.PowerShell     Available
```

<span data-ttu-id="3b2a5-147">Чтобы получить сеанс, используйте параметр **ComputerName** параметра `Get-PSSession` со значением Server01.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-147">To get the session, use the **ComputerName** parameter of `Get-PSSession` with a value of Server01.</span></span>

```powershell
Get-PSSession -ComputerName Server01
```

```Output
Id Name      ComputerName  State    ConfigurationName     Availability
-- ----      ------------  -----    -----------------     ------------
 2 Session2  Server01      Opened   Microsoft.PowerShell     Available
```

<span data-ttu-id="3b2a5-148">Если параметр **ComputerName** параметра `Get-PSSession` имеет значение localhost, `Get-PSSession` получает PSSession, которые завершаются в и сохраняются на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-148">If the value of the **ComputerName** parameter of `Get-PSSession` is localhost, `Get-PSSession` gets PSSessions that terminate at and are maintained on the local computer.</span></span> <span data-ttu-id="3b2a5-149">Он не получает PSSession на компьютере Server01, даже если они были запущены на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-149">It doesn't get PSSessions on the Server01 computer, even if they were started on the local computer.</span></span>

```powershell
Get-PSSession -ComputerName localhost
```

<span data-ttu-id="3b2a5-150">Чтобы получить сеансы, созданные в текущем сеансе, используйте `Get-PSSession` командлет без параметров.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-150">To get sessions that were created in the current session, use the `Get-PSSession` cmdlet without parameters.</span></span> <span data-ttu-id="3b2a5-151">В этом примере `Get-PSSession` получает сеанс PSSession, который был создан в текущем сеансе, и подключается к компьютеру Server01.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-151">In this example, `Get-PSSession` gets the PSSession that was created in the current session and connects to the Server01 computer.</span></span>

```powershell
Get-PSSession
```

```Output
Id Name      ComputerName  State    ConfigurationName     Availability
-- ----      ------------  -----    -----------------     ------------
 2 Session2  Server01      Opened   Microsoft.PowerShell     Available
```

## <a name="how-to-disconnect-sessions"></a><span data-ttu-id="3b2a5-152">Отключение сеансов</span><span class="sxs-lookup"><span data-stu-id="3b2a5-152">How to disconnect sessions</span></span>

<span data-ttu-id="3b2a5-153">Чтобы отключить сеанс PSSession, используйте `Disconnect-PSSession` командлет.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-153">To disconnect a PSSession, use the `Disconnect-PSSession` cmdlet.</span></span> <span data-ttu-id="3b2a5-154">Чтобы указать PSSession, используйте параметр **Session** или конвейер a PSSession из `New-PSSession` `Get-PSSession` командлетов или в `Disconnect-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="3b2a5-154">To identify the PSSession, use the **Session** parameter, or pipeline a PSSession from the `New-PSSession` or `Get-PSSession` cmdlets to `Disconnect-PSSession`.</span></span>

<span data-ttu-id="3b2a5-155">Следующая команда отключает сеанс PSSession на компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-155">The following command disconnects the PSSession to the Server01 computer.</span></span>
<span data-ttu-id="3b2a5-156">Обратите внимание, что значение свойства **State** — **disconnected** , а **доступность** — **нет**.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-156">Notice that the value of the **State** property is **Disconnected** and the **Availability** is **None**.</span></span>

```powershell
Get-PSSession -ComputerName Server01 | Disconnect-PSSession
```

```Output
Id Name      ComputerName  State         ConfigurationName     Availability
-- ----      ------------  -----         -----------------     ------------
 2 Session2  Server01      Disconnected  Microsoft.PowerShell          None
```

<span data-ttu-id="3b2a5-157">Чтобы создать отключенный сеанс, используйте параметр **InDisconnectedSession** `Invoke-Command` командлета.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-157">To create a disconnected session, use the **InDisconnectedSession** parameter of the `Invoke-Command` cmdlet.</span></span> <span data-ttu-id="3b2a5-158">Он создает сеанс, запускает команду и немедленно отключается, прежде чем команда сможет вернуть выходные данные.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-158">It creates a session, starts the command, and disconnects immediately, before the command can return any output.</span></span>

<span data-ttu-id="3b2a5-159">Следующая команда выполняет `Get-WinEvent` команду в отключенном сеансе на удаленном компьютере Server02.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-159">The following command runs a `Get-WinEvent` command in a disconnected session on the Server02 remote computer.</span></span>

```powershell
Invoke-Command -ComputerName Server02 -InDisconnectedSession -ScriptBlock {
   Get-WinEvent -LogName "*PowerShell*" }
```

```Output
Id Name      ComputerName  State         ConfigurationName     Availability
-- ----      ------------  -----         -----------------     ------------
 4 Session3  Server02      Disconnected  Microsoft.PowerShell          None
```

## <a name="how-to-connect-to-disconnected-sessions"></a><span data-ttu-id="3b2a5-160">Подключение к отключенным сеансам</span><span class="sxs-lookup"><span data-stu-id="3b2a5-160">How to connect to disconnected sessions</span></span>

<span data-ttu-id="3b2a5-161">Можно подключиться к любому доступному отключенному сеансу PSSession из сеанса, в котором был создан сеанс PSSession, или из других сеансов на локальном компьютере или на других компьютерах.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-161">You can connect to any available disconnected PSSession from the session in which you created the PSSession or from other sessions on the local computer or other computers.</span></span>

<span data-ttu-id="3b2a5-162">Можно создать сеанс PSSession, выполнить команды в сеансе PSSession, отключиться от сеанса PSSession, закрыть PowerShell и завершить работу компьютера.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-162">You can create a PSSession, run commands in the PSSession, disconnect from the PSSession, close PowerShell, and shut down the computer.</span></span> <span data-ttu-id="3b2a5-163">Часы позже можно будет открыть другой компьютер, получить сеанс PSSession, подключиться к нему и получить результаты команд, которые выполнялись в сеансе PSSession, пока он был отключен.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-163">Hours later, you can open a different computer, get the PSSession, connect to it, and get the results of commands that ran in the PSSession while it was disconnected.</span></span> <span data-ttu-id="3b2a5-164">Затем в сеансе можно выполнить дополнительные команды.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-164">Then you can run more commands in the session.</span></span>

<span data-ttu-id="3b2a5-165">Чтобы подключить отключенный сеанс PSSession, используйте `Connect-PSSession` командлет.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-165">To connect a disconnected PSSession, use the `Connect-PSSession` cmdlet.</span></span> <span data-ttu-id="3b2a5-166">Используйте параметры **ComputerName** или **ConnectionURI** , чтобы указать PSSession или конвейер a PSSession от `Get-PSSession` до `Connect-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="3b2a5-166">Use the **ComputerName** or **ConnectionUri** parameters to identify the PSSession, or pipeline a PSSession from `Get-PSSession` to `Connect-PSSession`.</span></span>

<span data-ttu-id="3b2a5-167">Следующая команда получает сеансы на компьютере Server02.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-167">The following command gets the sessions on the Server02 computer.</span></span> <span data-ttu-id="3b2a5-168">Выходные данные включают два отключенных сеанса, оба из которых доступны.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-168">The output includes two disconnected sessions, both of which are available.</span></span>

```powershell
Get-PSSession -ComputerName Server02
```

```Output
Id Name      ComputerName   State         ConfigurationName     Availability
-- ----      ------------   -----         -----------------     ------------
 2 Session2  juneb-srv8320  Disconnected  Microsoft.PowerShell          None
 4 Session3  juneb-srv8320  Disconnected  Microsoft.PowerShell          None
```

<span data-ttu-id="3b2a5-169">Следующая команда подключается к Session2.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-169">The following command connects to Session2.</span></span> <span data-ttu-id="3b2a5-170">Сеанс PSSession теперь открыт и доступен.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-170">The PSSession is now open and available.</span></span>

```powershell
Connect-PSSession -ComputerName Server02 -Name Session2
```

```Output
Id Name      ComputerName    State    ConfigurationName     Availability
-- ----      ------------    -----    -----------------     ------------
 2 Session2  juneb-srv8320   Opened   Microsoft.PowerShell     Available
```

## <a name="how-to-get-the-results"></a><span data-ttu-id="3b2a5-171">Как получить результаты</span><span class="sxs-lookup"><span data-stu-id="3b2a5-171">How to get the results</span></span>

<span data-ttu-id="3b2a5-172">Чтобы получить результаты команд, которые выполнялись в отключенном сеансе PSSession, используйте `Receive-PSSession` командлет.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-172">To get the results of commands that ran in a disconnected PSSession, use the `Receive-PSSession` cmdlet.</span></span>

<span data-ttu-id="3b2a5-173">`Receive-PSSession`Вместо использования `Connect-PSSession` командлета можно использовать.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-173">You can use `Receive-PSSession` rather than using the `Connect-PSSession` cmdlet.</span></span> <span data-ttu-id="3b2a5-174">Если сеанс уже подключен повторно, `Receive-PSSession` получает результаты команд, которые выполнялись в момент отключения сеанса.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-174">If the session is already reconnected, `Receive-PSSession` gets the results of commands that ran when the session was disconnected.</span></span> <span data-ttu-id="3b2a5-175">Если сеанс PSSession по-прежнему отключен, `Receive-PSSession` подключается к нему и получает результаты команд, которые выполнялись в момент отключения.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-175">If the PSSession is still disconnected, `Receive-PSSession` connects to it and then gets the results of commands that ran while it was disconnected.</span></span>

<span data-ttu-id="3b2a5-176">`Receive-PSSession` может возвращать результаты в задании (асинхронно) или в ведущем приложении (синхронно).</span><span class="sxs-lookup"><span data-stu-id="3b2a5-176">`Receive-PSSession` can return the results in a job (asynchronously) or to the host program (synchronously).</span></span> <span data-ttu-id="3b2a5-177">Используйте параметр **Target** для выбора **задания** или **узла**.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-177">Use the **OutTarget** parameter to select **Job** or **Host**.</span></span> <span data-ttu-id="3b2a5-178">Значение по умолчанию — **Host**.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-178">The default value is **Host**.</span></span> <span data-ttu-id="3b2a5-179">Однако если полученная команда была запущена в текущем сеансе как **Задание**, по умолчанию она возвращается как **Задание** .</span><span class="sxs-lookup"><span data-stu-id="3b2a5-179">However, if the command that's being received was started in the current session as a **Job**, it's returned as a **Job** by default.</span></span>

<span data-ttu-id="3b2a5-180">Следующая команда использует `Receive-PSSession` командлет для подключения к сеансу PSSession на компьютере Server02 и получения результатов `Get-WinEvent` команды, которая выполнялась в сеансе Session3.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-180">The following command uses the `Receive-PSSession` cmdlet to connect to the PSSession on the Server02 computer and get the results of the `Get-WinEvent` command that ran in the Session3 session.</span></span> <span data-ttu-id="3b2a5-181">Команда использует параметр **Target** для получения результатов в **задании**.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-181">The command uses the **OutTarget** parameter to get the results in a **Job**.</span></span>

```powershell
Receive-PSSession -ComputerName Server02 -Name Session3 -OutTarget Job
```

```Output
Id   Name   PSJobTypeName   State         HasMoreData     Location
--   ----   -------------   -----         -----------     --------
 3   Job3   RemoteJob       Running       True            Server02
```

<span data-ttu-id="3b2a5-182">Чтобы получить результаты задания, используйте `Receive-Job` командлет.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-182">To get the job's results, use the `Receive-Job` cmdlet.</span></span>

```powershell
Get-Job | Receive-Job -Keep
```

```Output
ProviderName: PowerShell

TimeCreated             Id LevelDisplayName Message     PSComputerName
-----------             -- ---------------- -------     --------------
5/14/2012 7:26:04 PM   400 Information      Engine stat Server02
5/14/2012 7:26:03 PM   600 Information      Provider "W Server02
5/14/2012 7:26:03 PM   600 Information      Provider "C Server02
5/14/2012 7:26:03 PM   600 Information      Provider "V Server02
```

## <a name="state-and-availability-properties"></a><span data-ttu-id="3b2a5-183">Свойства состояния и доступности</span><span class="sxs-lookup"><span data-stu-id="3b2a5-183">State and Availability properties</span></span>

<span data-ttu-id="3b2a5-184">Свойства **состояние** и **доступность** отключенного сеанса PSSession сообщают о том, доступен ли сеанс для повторного подключения.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-184">The **State** and **Availability** properties of a disconnected PSSession tell you whether the session is available for you to reconnect to it.</span></span>

<span data-ttu-id="3b2a5-185">Когда сеанс PSSession подключен к текущему сеансу, его состояние **открывается** , а доступность становится **доступной**.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-185">When a PSSession is connected to the current session, its state is **Opened** and its availability is **Available**.</span></span> <span data-ttu-id="3b2a5-186">При отключении от PSSession состояние PSSession **отключается** , а его доступность — **нет**.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-186">When you disconnect from the PSSession, the PSSession state is **Disconnected** and its availability is **None**.</span></span>

<span data-ttu-id="3b2a5-187">Значение свойства **State** определяется текущим сеансом.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-187">The value of the **State** property is relative to the current session.</span></span> <span data-ttu-id="3b2a5-188">Значение **disconnected** означает, что сеанс PSSession не подключен к текущему сеансу.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-188">A value of **Disconnected** means that the PSSession isn't connected to the current session.</span></span> <span data-ttu-id="3b2a5-189">Но это не значит, что сеанс PSSession отключен от всех сеансов.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-189">But, it doesn't mean that the PSSession is disconnected from all sessions.</span></span> <span data-ttu-id="3b2a5-190">Он может быть подключен к другому сеансу.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-190">It might be connected to a different session.</span></span>

<span data-ttu-id="3b2a5-191">Чтобы определить, можно ли подключиться к сеансу PSSession или повторно подключиться к нему, используйте свойство **Availability** .</span><span class="sxs-lookup"><span data-stu-id="3b2a5-191">To determine whether you can connect or reconnect to the PSSession, use the **Availability** property.</span></span> <span data-ttu-id="3b2a5-192">Значение **None** означает, что можно подключиться к сеансу.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-192">A value of **None** indicates that you can connect to the session.</span></span> <span data-ttu-id="3b2a5-193">Значение **занято** указывает, что невозможно подключиться к сеансу PSSession, так как он подключен к другому сеансу.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-193">A value of **Busy** indicates that you can't connect to the PSSession because it's connected to another session.</span></span>

<span data-ttu-id="3b2a5-194">Следующий пример выполняется в двух сеансах PowerShell на одном компьютере.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-194">The following example is run in two PowerShell sessions on the same computer.</span></span>
<span data-ttu-id="3b2a5-195">Обратите внимание на изменение значений свойств **State** и **Availability** в каждом сеансе, так как сеанс PSSession отключен и повторно подключен.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-195">Note the changing values of the **State** and **Availability** properties in each session as the PSSession is disconnected and reconnected.</span></span>

```powershell
# Session 1
New-PSSession -ComputerName Server30 -Name Test
```

```Output
Id Name   ComputerName    State         ConfigurationName     Availability
-- ----   ------------    -----         -----------------     ------------
1  Test   Server30        Opened        Microsoft.PowerShell     Available
```

```powershell
# Session 2
Get-PSSession -ComputerName Server30 -Name Test
```

```Output
Id Name   ComputerName    State         ConfigurationName     Availability
-- ----   ------------    -----         -----------------     ------------
1 Test    Server30        Disconnected  Microsoft.PowerShell          Busy
```

```powershell
# Session 1
Get-PSSession -ComputerName Server30 -Name Test | Disconnect-PSSession
```

```Output
Id Name   ComputerName    State         ConfigurationName     Availability
-- ----   ------------    -----         -----------------     ------------
1 Test    Server30        Disconnected  Microsoft.PowerShell          None
```

```powershell
# Session 2
Get-PSSession -ComputerName Server30
```

```Output
Id Name   ComputerName    State         ConfigurationName     Availability
-- ----   ------------    -----         -----------------     ------------
1 Test    Server30        Disconnected  Microsoft.PowerShell          None
```

```powershell
# Session 2
Connect-PSSession -ComputerName Server30 -Name Test
```

```Output
Id Name   ComputerName    State         ConfigurationName     Availability
-- ----   ------------    -----         -----------------     ------------
3 Test    Server30        Opened        Microsoft.PowerShell     Available
```

```powershell
# Session 1
Get-PSSession -ComputerName Server30
```

```Output
Id Name   ComputerName    State         ConfigurationName     Availability
-- ----   ------------    -----         -----------------     ------------
1 Test    Server30        Disconnected  Microsoft.PowerShell          Busy
```

```Output
# Idle Timeout
```

<span data-ttu-id="3b2a5-196">Отключенные сеансы сохраняются на удаленном компьютере, пока вы не удалите их, например с помощью `Remove-PSSession` командлета, или истечет время ожидания. Свойство **IdleTimeout** параметра PSSession определяет время, в течение которого отключенный сеанс сохраняется до его удаления.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-196">Disconnected sessions are maintained on the remote computer until you delete them, such as by using the `Remove-PSSession` cmdlet, or they time out. The **IdleTimeout** property of a PSSession determines how long a disconnected session is maintained before it's deleted.</span></span>

<span data-ttu-id="3b2a5-197">PSSession бездействует, когда **поток пульса** не получает ответа.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-197">PSSessions are idle when the **heartbeat thread** receives no response.</span></span>
<span data-ttu-id="3b2a5-198">Отключение сеанса делает его неактивным и запускает часы **IdleTimeout** , даже если команды по-прежнему выполняются в отключенном сеансе.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-198">Disconnecting a session makes it idle and starts the **IdleTimeout** clock, even if commands are still running in the disconnected session.</span></span> <span data-ttu-id="3b2a5-199">PowerShell считает, что отключенные сеансы активны, но в режиме простоя.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-199">PowerShell considers disconnected sessions to be active, but idle.</span></span>

<span data-ttu-id="3b2a5-200">При создании и отключении сеансов убедитесь, что время ожидания простоя в PSSession достаточно велико для поддержания сеанса в соответствии с вашими потребностями, но не настолько долго, что он потребляет ненужные ресурсы на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-200">When creating and disconnecting sessions, verify that the idle timeout in the PSSession is long enough to maintain the session for your needs, but not so long that it consumes unnecessary resources on the remote computer.</span></span>

<span data-ttu-id="3b2a5-201">Свойство **идлетимеаутмс** конфигурации сеанса определяет время ожидания простоя по умолчанию для сеансов, использующих конфигурацию сеанса.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-201">The **IdleTimeoutMs** property of the session configuration determines the default idle timeout of sessions that use the session configuration.</span></span> <span data-ttu-id="3b2a5-202">Можно переопределить значение по умолчанию, но используемое значение не может превышать свойство **максидлетимеаутмс** конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-202">You can override the default value, but the value that you use can't exceed the **MaxIdleTimeoutMs** property of the session configuration.</span></span>

<span data-ttu-id="3b2a5-203">Чтобы найти значения **идлетимеаутмс** и **максидлетимеаутмс** для конфигурации сеанса, используйте следующий формат команды:</span><span class="sxs-lookup"><span data-stu-id="3b2a5-203">To find the value of the **IdleTimeoutMs** and **MaxIdleTimeoutMs** values of a session configuration, use the following command format.</span></span>

```powershell
Get-PSSessionConfiguration |
  Format-Table Name, IdleTimeoutMs, MaxIdleTimeoutMs
```

<span data-ttu-id="3b2a5-204">Можно переопределить значение по умолчанию в конфигурации сеанса и установить время ожидания сеанса PSSession в режиме простоя при создании сеанса PSSession и при отключении.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-204">You can override the default value in the session configuration and set the idle timeout of a PSSession when you create a PSSession and when you disconnect.</span></span>

<span data-ttu-id="3b2a5-205">Если вы являетесь членом группы администраторов на удаленном компьютере, вы можете создавать и изменять свойства **идлетимеаутмс** и **максидлетимеаутмс** конфигураций сеансов.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-205">If you're a member of the Administrators group on the remote computer, you can create and change the **IdleTimeoutMs** and **MaxIdleTimeoutMs** properties of session configurations.</span></span>

## <a name="idle-timeout-values"></a><span data-ttu-id="3b2a5-206">Значения времени ожидания простоя</span><span class="sxs-lookup"><span data-stu-id="3b2a5-206">Idle timeout values</span></span>

<span data-ttu-id="3b2a5-207">Значение времени ожидания простоя конфигураций сеанса и параметров сеанса указано в миллисекундах.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-207">The idle timeout value of session configurations and session options is in milliseconds.</span></span> <span data-ttu-id="3b2a5-208">Значение времени ожидания простоя сеанса и параметры конфигурации сеанса находятся в секундах.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-208">The idle timeout value of sessions and session configuration options is in seconds.</span></span>

<span data-ttu-id="3b2a5-209">Можно задать время ожидания простоя сеанса PSSession при создании сеанса PSSession ( `New-PSSession` , `Invoke-Command` ) и при отключении от него ( `Disconnect-PSSession` ).</span><span class="sxs-lookup"><span data-stu-id="3b2a5-209">You can set the idle timeout of a PSSession when you create the PSSession (`New-PSSession`, `Invoke-Command`) and when you disconnect from it (`Disconnect-PSSession`).</span></span> <span data-ttu-id="3b2a5-210">Однако значение **IdleTimeout** нельзя изменить при соединении с PSSession ( `Connect-PSSession` ) или Get Results ( `Receive-PSSession` ).</span><span class="sxs-lookup"><span data-stu-id="3b2a5-210">However, you can't change the **IdleTimeout** value when you connect to the PSSession (`Connect-PSSession`) or get results (`Receive-PSSession`).</span></span>

<span data-ttu-id="3b2a5-211">`Connect-PSSession` `Receive-PSSession` Командлеты и имеют параметр **SessionOption** , принимающий объект **SessionOption** , например, возвращаемый `New-PSSessionOption` командлетом.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-211">The `Connect-PSSession` and `Receive-PSSession` cmdlets have a **SessionOption** parameter that takes a **SessionOption** object, such as one returned by the `New-PSSessionOption` cmdlet.</span></span> <span data-ttu-id="3b2a5-212">Значение **IdleTimeout** в объекте **SessionOption** и значение **IdleTimeout** в `$PSSessionOption` привилегированной переменной не изменяют значение параметра **IdleTimeout** для PSSession в `Connect-PSSession` `Receive-PSSession` команде или.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-212">The **IdleTimeout** value in **SessionOption** object and the **IdleTimeout** value in the `$PSSessionOption` preference variable don't change the value of the **IdleTimeout** of the PSSession in a `Connect-PSSession` or `Receive-PSSession` command.</span></span>

<span data-ttu-id="3b2a5-213">Чтобы создать сеанс PSSession с определенным значением времени ожидания простоя, создайте `$PSSessionOption` переменную предпочтение.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-213">To create a PSSession with a particular idle timeout value, create a `$PSSessionOption` preference variable.</span></span> <span data-ttu-id="3b2a5-214">Задайте в качестве значения свойства **IdleTimeout** нужное значение (в миллисекундах).</span><span class="sxs-lookup"><span data-stu-id="3b2a5-214">Set the value of the **IdleTimeout** property to the desired value (in milliseconds).</span></span>

<span data-ttu-id="3b2a5-215">При создании PSSession значения в `$PSSessionOption` переменной имеют приоритет над значениями в конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-215">When you create PSSessions, the values in `$PSSessionOption` variable take precedence over the values in the session configuration.</span></span>

<span data-ttu-id="3b2a5-216">Например, следующая команда устанавливает время ожидания простоя в 48 ч.:</span><span class="sxs-lookup"><span data-stu-id="3b2a5-216">For example, the following command sets an idle timeout of 48 hours:</span></span>

```powershell
$PSSessionOption = New-PSSessionOption -IdleTimeoutMSec 172800000
```

<span data-ttu-id="3b2a5-217">Чтобы создать сеанс PSSession с определенным значением времени ожидания простоя, используйте параметр **идлетимеаутмсек** `New-PSSessionOption` командлета.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-217">To create a PSSession with a particular idle timeout value, use the **IdleTimeoutMSec** parameter of the `New-PSSessionOption` cmdlet.</span></span> <span data-ttu-id="3b2a5-218">Затем используйте параметр Session в значении параметра **SessionOption** `New-PSSession` `Invoke-Command` командлетов или.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-218">Then, use the session option in the value of the **SessionOption** parameter of the `New-PSSession` or `Invoke-Command` cmdlets.</span></span>

<span data-ttu-id="3b2a5-219">Значения, заданные при создании сеанса, имеют приоритет над значениями, заданными в `$PSSessionOption` привилегированной переменной и конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-219">The values set when creating the session take precedence over the values set in the `$PSSessionOption` preference variable and the session configuration.</span></span>

<span data-ttu-id="3b2a5-220">Пример:</span><span class="sxs-lookup"><span data-stu-id="3b2a5-220">For example:</span></span>

```powershell
$o = New-PSSessionOption -IdleTimeoutMSec 172800000
New-PSSession -SessionOption $o
```

<span data-ttu-id="3b2a5-221">Чтобы изменить время ожидания простоя сеанса PSSession при отключении, используйте параметр **идлетимеаутсек** `Disconnect-PSSession` командлета.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-221">To change the idle timeout of a PSSession when disconnecting, use the **IdleTimeoutSec** parameter of the `Disconnect-PSSession` cmdlet.</span></span>

<span data-ttu-id="3b2a5-222">Пример:</span><span class="sxs-lookup"><span data-stu-id="3b2a5-222">For example:</span></span>

```powershell
Disconnect-PSSession -IdleTimeoutSec 172800
```

<span data-ttu-id="3b2a5-223">Чтобы создать конфигурацию сеанса с определенным временем ожидания простоя и максимальным временем ожидания простоя, используйте параметры **идлетимеаутсек** и **максидлетимеаутсек** `New-PSTransportOption` командлета.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-223">To create a session configuration with a particular idle timeout and maximum idle timeout, use the **IdleTimeoutSec** and **MaxIdleTimeoutSec** parameters of the `New-PSTransportOption` cmdlet.</span></span> <span data-ttu-id="3b2a5-224">Затем используйте параметр Transport в значении параметра **транспортоптион** в параметре `Register-PSSessionConfiguration` .</span><span class="sxs-lookup"><span data-stu-id="3b2a5-224">Then, use the transport option in the value of the **TransportOption** parameter of `Register-PSSessionConfiguration`.</span></span>

<span data-ttu-id="3b2a5-225">Пример:</span><span class="sxs-lookup"><span data-stu-id="3b2a5-225">For example:</span></span>

```powershell
$o = New-PSTransportOption -IdleTimeoutSec 172800 -MaxIdleTimeoutSec 259200
Register-PSSessionConfiguration -Name Test -TransportOption $o
```

<span data-ttu-id="3b2a5-226">Чтобы изменить время ожидания простоя по умолчанию и максимальное время ожидания простоя для конфигурации сеанса, используйте параметры **идлетимеаутсек** и **максидлетимеаутсек** `New-PSTransportOption` командлета.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-226">To change the default idle timeout and maximum idle timeout of a session configuration, use the **IdleTimeoutSec** and **MaxIdleTimeoutSec** parameters of the `New-PSTransportOption` cmdlet.</span></span> <span data-ttu-id="3b2a5-227">Затем используйте параметр Transport в значении параметра **транспортоптион** в параметре `Set-PSSessionConfiguration` .</span><span class="sxs-lookup"><span data-stu-id="3b2a5-227">Then, use the transport option in the value of the **TransportOption** parameter of `Set-PSSessionConfiguration`.</span></span>

<span data-ttu-id="3b2a5-228">Пример:</span><span class="sxs-lookup"><span data-stu-id="3b2a5-228">For example:</span></span>

```powershell
$o = New-PSTransportOption -IdleTimeoutSec 172800 -MaxIdleTimeoutSec 259200
Set-PSSessionConfiguration -Name Test -TransportOption $o
```

## <a name="output-buffering-mode"></a><span data-ttu-id="3b2a5-229">Режим буферизации вывода</span><span class="sxs-lookup"><span data-stu-id="3b2a5-229">Output buffering mode</span></span>

<span data-ttu-id="3b2a5-230">Режим буферизации вывода сеанса PSSession определяет управление выводом команд, когда выходной буфер сеанса PSSession заполнен.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-230">The output buffering mode of a PSSession determines how command output is managed when the output buffer of the PSSession is full.</span></span>

<span data-ttu-id="3b2a5-231">В отключенном сеансе режим буферизации вывода фактически определяет, будет ли команда продолжать выполняться, пока сеанс отключен.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-231">In a disconnected session, the output buffering mode effectively determines whether the command continues to run while the session is disconnected.</span></span>

<span data-ttu-id="3b2a5-232">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="3b2a5-232">The valid values as follows:</span></span>

- <span data-ttu-id="3b2a5-233">**Заблокировать**.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-233">**Block**.</span></span> <span data-ttu-id="3b2a5-234">при заполнении выходного буфера выполнение команды приостанавливается до тех пор, пока буфер не будет очищен.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-234">When the output buffer is full, execution is suspended until the buffer is clear.</span></span> <span data-ttu-id="3b2a5-235">Значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-235">The default value.</span></span>
- <span data-ttu-id="3b2a5-236">**Удалить**.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-236">**Drop**.</span></span> <span data-ttu-id="3b2a5-237">при заполнении выходного буфера выполнение команды продолжается.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-237">When the output buffer is full, execution continues.</span></span> <span data-ttu-id="3b2a5-238">При формировании новых выходных данных самые старые выходные данные удаляются.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-238">As new output is generated, the oldest output is discarded.</span></span>

<span data-ttu-id="3b2a5-239">**Блок** сохраняет данные, но может прерывать выполнение команды.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-239">**Block** preserves data, but might interrupt the command.</span></span> <span data-ttu-id="3b2a5-240">Значение **Drop** позволяет завершить выполнение команды, несмотря на возможную потерю данных.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-240">A value of **Drop** allows the command to complete, although data might be lost.</span></span> <span data-ttu-id="3b2a5-241">При использовании значения **Drop** выходные данные команды необходимо перенаправить в какой-либо файл на диске.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-241">When using the **Drop** value, redirect the command output to a file on disk.</span></span> <span data-ttu-id="3b2a5-242">Это значение рекомендуется для отключенных сеансов.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-242">This value is recommended for disconnected sessions.</span></span>

<span data-ttu-id="3b2a5-243">Свойство **аутпутбуфферингмоде** конфигурации сеанса определяет режим буферизации вывода по умолчанию для сеансов, использующих конфигурацию сеанса.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-243">The **OutputBufferingMode** property of the session configuration determines the default output buffering mode of sessions that use the session configuration.</span></span>

<span data-ttu-id="3b2a5-244">Чтобы найти значение конфигурации сеанса **аутпутбуфферингмоде**, можно использовать любой из следующих форматов команд:</span><span class="sxs-lookup"><span data-stu-id="3b2a5-244">To find a session configuration's value of the **OutputBufferingMode**, you can use either of the following command formats:</span></span>

```powershell
(Get-PSSessionConfiguration <ConfigurationName>).OutputBufferingMode
```

```powershell
Get-PSSessionConfiguration | Format-Table Name, OutputBufferingMode
```

<span data-ttu-id="3b2a5-245">Можно переопределить значение по умолчанию в конфигурации сеанса и установить режим буферизации вывода сеанса PSSession при создании PSSession, при отключении и при повторном подключении.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-245">You can override the default value in the session configuration and set the output buffering mode of a PSSession when you create a PSSession, when you disconnect, and when you reconnect.</span></span>

<span data-ttu-id="3b2a5-246">Если вы являетесь членом группы "Администраторы" на удаленном компьютере, вы можете создать и изменить режим буферизации вывода конфигураций сеанса.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-246">If you're a member of the Administrators group on the remote computer, you can create and change the output buffering mode of session configurations.</span></span>

<span data-ttu-id="3b2a5-247">Чтобы создать сеанс PSSession с режимом буферизации **вывода, создайте** `$PSSessionOption` переменную предпочтение, в которой значение свойства **аутпутбуфферингмоде** равно **Drop**.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-247">To create a PSSession with an output buffering mode of **Drop**, create a `$PSSessionOption` preference variable in which the value of the **OutputBufferingMode** property is **Drop**.</span></span>

<span data-ttu-id="3b2a5-248">При создании PSSession значения в `$PSSessionOption` переменной имеют приоритет над значениями в конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-248">When you create PSSessions, the values in `$PSSessionOption` variable take precedence over the values in the session configuration.</span></span>

<span data-ttu-id="3b2a5-249">Пример:</span><span class="sxs-lookup"><span data-stu-id="3b2a5-249">For example:</span></span>

```powershell
$PSSessionOption = New-PSSessionOption -OutputBufferingMode Drop
```

<span data-ttu-id="3b2a5-250">Чтобы создать сеанс PSSession с режимом буферизации **вывода, используйте** параметр **аутпутбуфферингмоде** `New-PSSessionOption` командлета, чтобы создать параметр сеанса со значением **Drop**.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-250">To create a PSSession with an output buffering mode of **Drop**, use the **OutputBufferingMode** parameter of the `New-PSSessionOption` cmdlet to create a session option with a value of **Drop**.</span></span> <span data-ttu-id="3b2a5-251">Затем используйте параметр Session в значении параметра **SessionOption** `New-PSSession` `Invoke-Command` командлетов или.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-251">Then, use the session option in the value of the **SessionOption** parameter of the `New-PSSession` or `Invoke-Command` cmdlets.</span></span>

<span data-ttu-id="3b2a5-252">Значения, заданные при создании сеанса, имеют приоритет над значениями, заданными в `$PSSessionOption` привилегированной переменной и конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-252">The values set when creating the session take precedence over the values set in the `$PSSessionOption` preference variable and the session configuration.</span></span>

<span data-ttu-id="3b2a5-253">Пример:</span><span class="sxs-lookup"><span data-stu-id="3b2a5-253">For example:</span></span>

```powershell
$o = New-PSSessionOption -OutputBufferingMode Drop
New-PSSession -SessionOption $o
```

<span data-ttu-id="3b2a5-254">Чтобы изменить режим буферизации вывода сеанса PSSession при отключении, используйте параметр **аутпутбуфферингмоде** `Disconnect-PSSession` командлета.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-254">To change the output buffering mode of a PSSession when disconnecting, use the **OutputBufferingMode** parameter of the `Disconnect-PSSession` cmdlet.</span></span>

<span data-ttu-id="3b2a5-255">Пример:</span><span class="sxs-lookup"><span data-stu-id="3b2a5-255">For example:</span></span>

```powershell
Disconnect-PSSession -OutputBufferingMode Drop
```

<span data-ttu-id="3b2a5-256">Чтобы изменить режим буферизации вывода PSSession при повторном подключении, используйте параметр **аутпутбуфферингмоде** `New-PSSessionOption` командлета, чтобы создать параметр сеанса со значением **Drop**.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-256">To change the output buffering mode of a PSSession when reconnecting, use the **OutputBufferingMode** parameter of the `New-PSSessionOption` cmdlet to create a session option with a value of **Drop**.</span></span> <span data-ttu-id="3b2a5-257">Затем используйте параметр Session в значении параметра **SessionOption** в параметре `Connect-PSSession` или `Receive-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="3b2a5-257">Then, use the session option in the value of the **SessionOption** parameter of `Connect-PSSession` or `Receive-PSSession`.</span></span>

<span data-ttu-id="3b2a5-258">Пример:</span><span class="sxs-lookup"><span data-stu-id="3b2a5-258">For example:</span></span>

```powershell
$o = New-PSSessionOption -OutputBufferingMode Drop
Connect-PSSession -ComputerName Server01 -Name Test -SessionOption $o
```

<span data-ttu-id="3b2a5-259">Чтобы создать конфигурацию сеанса с режимом буферизации вывода по умолчанию **, используйте** параметр **аутпутбуфферингмоде** `New-PSTransportOption` командлета, чтобы создать объект параметра транспорта со значением **Drop**.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-259">To create a session configuration with a default output buffering mode of **Drop**, use the **OutputBufferingMode** parameter of the `New-PSTransportOption` cmdlet to create a transport option object with a value of **Drop**.</span></span> <span data-ttu-id="3b2a5-260">Затем используйте параметр Transport в значении параметра **транспортоптион** в параметре `Register-PSSessionConfiguration` .</span><span class="sxs-lookup"><span data-stu-id="3b2a5-260">Then, use the transport option in the value of the **TransportOption** parameter of `Register-PSSessionConfiguration`.</span></span>

<span data-ttu-id="3b2a5-261">Пример:</span><span class="sxs-lookup"><span data-stu-id="3b2a5-261">For example:</span></span>

```powershell
$o = New-PSTransportOption -OutputBufferingMode Drop
Register-PSSessionConfiguration -Name Test -TransportOption $o
```

<span data-ttu-id="3b2a5-262">Чтобы изменить режим буферизации вывода по умолчанию в конфигурации сеанса, используйте параметр **аутпутбуфферингмоде** `New-PSTransportOption` командлета, чтобы создать параметр транспорта со значением **Drop**.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-262">To change the default output buffering mode of a session configuration, use the **OutputBufferingMode** parameter of the `New-PSTransportOption` cmdlet to create a transport option with a value of **Drop**.</span></span> <span data-ttu-id="3b2a5-263">Затем используйте параметр Transport в значении параметра **SessionOption** в параметре `Set-PSSessionConfiguration` .</span><span class="sxs-lookup"><span data-stu-id="3b2a5-263">Then, use the Transport option in the value of the **SessionOption** parameter of `Set-PSSessionConfiguration`.</span></span>

<span data-ttu-id="3b2a5-264">Пример:</span><span class="sxs-lookup"><span data-stu-id="3b2a5-264">For example:</span></span>

```powershell
$o = New-PSTransportOption -OutputBufferingMode Drop
Set-PSSessionConfiguration -Name Test -TransportOption $o
```

## <a name="disconnecting-loopback-sessions"></a><span data-ttu-id="3b2a5-265">Отключение замыканий на себя сеансов</span><span class="sxs-lookup"><span data-stu-id="3b2a5-265">Disconnecting loopback sessions</span></span>

<span data-ttu-id="3b2a5-266">Сеансы замыкания на себя или локальные сеансы являются PSSession, которые происходят и завершаются на одном и том же компьютере.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-266">Loopback sessions, or local sessions, are PSSessions that originate and terminate on the same computer.</span></span> <span data-ttu-id="3b2a5-267">Как и другие PSSession, активные сеансы замыкания на себя сохраняются на компьютере на удаленном конце подключения (локальный компьютер), поэтому можно отключиться от и повторно подключиться к сеансам замыкания на себя.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-267">Like other PSSessions, active loopback sessions are maintained on the computer on the remote end of the connection (the local computer), so you can disconnect from and reconnect to loopback sessions.</span></span>

<span data-ttu-id="3b2a5-268">По умолчанию, сеансы замыкания на себя создаются с маркером безопасности сети, который не позволяет выполнять команды в сеансе для доступа к другим компьютерам.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-268">By default, loopback sessions are created with a network security token that doesn't permit commands run in the session to access other computers.</span></span> <span data-ttu-id="3b2a5-269">Вы можете повторно подключиться к сеансам замыкания на себя с маркером безопасности сети из любого сеанса на локальном или удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-269">You can reconnect to loopback sessions that have a network security token from any session on the local computer or a remote computer.</span></span>

<span data-ttu-id="3b2a5-270">Однако если используется параметр **EnableNetworkAccess** `New-PSSession` `Enter-PSSession` `Invoke-Command` командлета, или, то сеанс замыкания на себя создается с помощью интерактивного маркера безопасности.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-270">However, if you use the **EnableNetworkAccess** parameter of the `New-PSSession`, `Enter-PSSession`, or `Invoke-Command` cmdlet, the loopback session is created with an interactive security token.</span></span> <span data-ttu-id="3b2a5-271">Интерактивный токен позволяет командам, выполняемым в сеансе замыкания на себя, получать данные с других компьютеров.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-271">The interactive token enables commands that run in the loopback session to get data from other computers.</span></span>

<span data-ttu-id="3b2a5-272">Вы можете отключить сеансы замыкания на себя с помощью интерактивных маркеров, а затем повторно подключиться к ним из того же сеанса или другого сеанса на том же компьютере.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-272">You can disconnect loopback sessions with interactive tokens and then reconnect to them from the same session or a different session on the same computer.</span></span>
<span data-ttu-id="3b2a5-273">Однако, чтобы предотвратить вредоносный доступ, можно повторно подключиться к сеансам замыкания на себя с помощью интерактивных маркеров только с того компьютера, на котором они были созданы.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-273">However, to prevent malicious access, you can reconnect to loopback sessions with interactive tokens only from the computer on which they were created.</span></span>

## <a name="waiting-for-jobs-in-disconnected-sessions"></a><span data-ttu-id="3b2a5-274">Ожидание заданий в отключенных сеансах</span><span class="sxs-lookup"><span data-stu-id="3b2a5-274">Waiting for jobs in disconnected sessions</span></span>

<span data-ttu-id="3b2a5-275">`Wait-Job`Командлет ожидает завершения задания, а затем возвращает его в командную строку или следующую команду.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-275">The `Wait-Job` cmdlet waits until a job completes and then returns to the command prompt or the next command.</span></span> <span data-ttu-id="3b2a5-276">По умолчанию `Wait-Job` возвращает значение, если сеанс, в котором выполняется задание, отключен.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-276">By default, `Wait-Job` returns if the session in which a job is running is disconnected.</span></span> <span data-ttu-id="3b2a5-277">Чтобы направить `Wait-Job` командлет в ожидание повторного подключения сеанса, в **открытом** состоянии используйте параметр **Force** .</span><span class="sxs-lookup"><span data-stu-id="3b2a5-277">To direct the `Wait-Job` cmdlet to wait until the session is reconnected, in the **Opened** state, use the **Force** parameter.</span></span> <span data-ttu-id="3b2a5-278">Дополнительные сведения см. в разделе [Wait-Job](xref:Microsoft.PowerShell.Core.Wait-Job).</span><span class="sxs-lookup"><span data-stu-id="3b2a5-278">For more information, see [Wait-Job](xref:Microsoft.PowerShell.Core.Wait-Job).</span></span>

## <a name="robust-sessions-and-unintentional-disconnection"></a><span data-ttu-id="3b2a5-279">Устойчивые сеансы и непреднамеренное отключение</span><span class="sxs-lookup"><span data-stu-id="3b2a5-279">Robust sessions and unintentional disconnection</span></span>

<span data-ttu-id="3b2a5-280">Сеанс PSSession может быть непреднамеренно отключен из-за сбоя компьютера или отключения сети.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-280">A PSSession might be unintentionally disconnected because of a computer failure or network outage.</span></span> <span data-ttu-id="3b2a5-281">PowerShell пытается восстановить PSSession, но его успешность зависит от серьезности и длительности причины.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-281">PowerShell attempts to recover the PSSession, but its success depends upon the severity and duration of the cause.</span></span>

<span data-ttu-id="3b2a5-282">Состояние непреднамеренного разъединения PSSession может быть **разорвано** или **закрыто**, но оно также может быть **отключено**.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-282">The state of an unintentionally disconnected PSSession might be **Broken** or **Closed**, but it might also be **Disconnected**.</span></span> <span data-ttu-id="3b2a5-283">Если значение **State** равно **disconnected**, то для управления сеансом PSSession можно использовать те же методы, что и при намеренном отключении сеанса.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-283">If the value of **State** is **Disconnected**, you can use the same techniques to manage the PSSession as you would if the session were disconnected intentionally.</span></span> <span data-ttu-id="3b2a5-284">Например, можно использовать `Connect-PSSession` командлет для повторного подключения к сеансу и `Receive-PSSession` командлет для получения результатов команд, которые выполнялись во время отключения сеанса.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-284">For example, you can use the `Connect-PSSession` cmdlet to reconnect to the session and the `Receive-PSSession` cmdlet to get results of commands that ran while the session was disconnected.</span></span>

<span data-ttu-id="3b2a5-285">При закрытии (выходе) сеанса, в котором был создан PSSession во время выполнения команд в сеансе PSSession, PowerShell обслуживает сеанс PSSession в состоянии **disconnected (отключено** ) на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-285">If you close (exit) the session in which a PSSession was created while commands are running in the PSSession, PowerShell maintains the PSSession in the **Disconnected** state on the remote computer.</span></span> <span data-ttu-id="3b2a5-286">При закрытии (выходе) сеанса, в котором был создан PSSession, но в сеансе PSSession не выполняется ни одной команды, PowerShell не пытается сохранить PSSession.</span><span class="sxs-lookup"><span data-stu-id="3b2a5-286">If you close (exit) the session in which a PSSession was created, but no commands are running in the PSSession, PowerShell doesn't attempt to maintain the PSSession.</span></span>

## <a name="see-also"></a><span data-ttu-id="3b2a5-287">См. также</span><span class="sxs-lookup"><span data-stu-id="3b2a5-287">See also</span></span>

[<span data-ttu-id="3b2a5-288">about_Jobs</span><span class="sxs-lookup"><span data-stu-id="3b2a5-288">about_Jobs</span></span>](about_Jobs.md)

[<span data-ttu-id="3b2a5-289">about_Remote</span><span class="sxs-lookup"><span data-stu-id="3b2a5-289">about_Remote</span></span>](about_Remote.md)

[<span data-ttu-id="3b2a5-290">about_Remote_Variables</span><span class="sxs-lookup"><span data-stu-id="3b2a5-290">about_Remote_Variables</span></span>](about_Remote_Variables.md)

[<span data-ttu-id="3b2a5-291">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="3b2a5-291">about_PSSessions</span></span>](about_PSSessions.md)

[<span data-ttu-id="3b2a5-292">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="3b2a5-292">about_Session_Configurations</span></span>](about_Session_Configurations.md)

[<span data-ttu-id="3b2a5-293">Connect-PSSession</span><span class="sxs-lookup"><span data-stu-id="3b2a5-293">Connect-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Connect-PSSession)

[<span data-ttu-id="3b2a5-294">Disconnect-PSSession</span><span class="sxs-lookup"><span data-stu-id="3b2a5-294">Disconnect-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Disconnect-PSSession)

[<span data-ttu-id="3b2a5-295">Get-PSSession</span><span class="sxs-lookup"><span data-stu-id="3b2a5-295">Get-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Get-PSSession)

[<span data-ttu-id="3b2a5-296">Receive-PSSession</span><span class="sxs-lookup"><span data-stu-id="3b2a5-296">Receive-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Receive-PSSession)

[<span data-ttu-id="3b2a5-297">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="3b2a5-297">Invoke-Command</span></span>](xref:Microsoft.PowerShell.Core.Invoke-Command)

